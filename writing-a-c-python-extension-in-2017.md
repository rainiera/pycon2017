## Writing a C Python extension in 2017

speaker: Jean-Baptiste Aviat  
time: Saturday 4:30 pm - 5:00 pm  
[description](https://us.pycon.org/2017/schedule/presentation/135/)  

**Intro**

- needed to run v8 in Python

[pyminiracer](https://github.com/sqreen/PyMiniRacer)


**Choosing the thing**

- CPython
- ctypes
    - built into python
    - binary is Pythin independent
        - can be used on any version
        - can be used in other languages
    - but no tight integration to Python
        - not high throughout capable
        - less Pythonic
    - but complex syntax (C types wrapped in Python)
    - not for C++
- cffi
- SWIG

- C file -> binary object -> python interface (just `import ctypes` and provide path to object file)

```
`import ctypes`
    linked to
`# include <v8.h>`
    linked to (via linkers)
V8 library (libv8.a)
V8 headers(v8.h)
```

**Stack traces**

```
$ ulimit -c unlimited
$ python run_me.py
[1] 28653 abort (core dumped)
$ ls /cores

$ lldb -c core.28653 (or gdb -c core.28653)

# now you can examine C code and Python

```

in OSX

```
$ ls /Library/Application\ Support/CrashReporter/
```

**Memory leaks**

- use Valgrind or clang analyser (`$ clang --analyze file.c`)

**Other possible issues**

- Valgrind
    - use after free
    - non-aligned accesses
    - uninitialized accesses
- clang address sanitiser
    - `$ clang --asan file.c`

**Security** (once you've added clang analyzer to your build chain)

 - [American Fuzzy Lop](http://lcamtuf.coredump.cx/afl/)

**Use the Python unit tests heavily**

- (unit testing is painful in C)
- test multithreading capabilities
- test for memory leaks
- test for performance and performance regressions

**Python packaging history**

- sdist
- eggs
- (2012) wheels (good for anything but Linux - actually *built* the distribution)
- (2016) manylinux wheels

**manylinux wheels**

- Python standard: PEP 503
- Compatible on most (real world) Linux
- But only in pip >= 8.1
- But need to build on many platforms
- But binaries need to be built on CentOS 5...

**wheels or compiler?**

- wheels
- iso builds (crashed can be reproduced)
- you need to maintain many packages

- compiler
- one build per user
- only one package
- but harder to install

- preferred way:
    - publish the wheels
    - also publish the non-compiled version

**why centos 5?**

- a compiled program relies on 3rd party libraries:
    - libc
    - libstdc++
- a program compiled with libc 2.1 won't run with libc 2.20
- it's one of the oldest libc that can be found
- it's mandatory by PEP503

