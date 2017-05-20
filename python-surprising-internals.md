## When the abyss gazes back: staring down Python's surprising internals

speaker: David Wolever  
time: Saturday 11:30 am - 12:00 pm  
[description](https://us.pycon.org/2017/schedule/presentation/309/)  
[question](http://stackoverflow.com/questions/28885132/why-is-x-in-x-faster-than-x-x/28885213#28885213)  

```
nan = float("nan")
nan is nan
True
nan == nan
False
nan in (nan, )
True
```

- `%timeit <expr>` in IPython
- `dis.disassemble`

- `dis.disassemble(function_name.func_code)` (Python 2)
- `dis.disassemble(function_name.__code__)` (Python 3)

- `dir(func_name)` - `func_globals`, `func_defaults)?

- `dir(func_name.func_code)`? 
- `dir(func_name.func_code.co_code)`? 

- `dir(func_name.func_closure)`  - tuple containing all the variables that it's closed over.
- `dir(func_name.func_closure[0].cell_contents)`

- Python VM is a stack machine
- Differs from register machine (Intel chip)
- 


- `dir(func_name.func_code.co_consts)`? 
- 


```
wget and tar xvf the python source code
ctags -R .
ack COMPARE_OP
```

not a in b -> a not in b
google "python peephole.c"

`ceval.c`

- figure out why "@property" doesn't work with old-style classes?

- PyObject_RichCompare

- String interning
```
>>> foo = "abc"
>>> bar = "abc"
>>> foo is bar
True
```

- Membership vs Equality


