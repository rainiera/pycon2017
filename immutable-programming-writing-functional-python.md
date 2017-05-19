## Immutable Programming - Writing Functional Python

speaker: Calen Pennington
time: Friday 11:30 am - 12:00 pm
[description](https://us.pycon.org/2017/schedule/presentation/729/)
[code](https://github.com/cpennington/pycon-2017-immutable-programming)
[presentation](http://vengefulpickle.com/pycon-2017-immutable-programming/#/)

- edX

## Immutability allows local thinking

## Immutability in Python

**Mutability**
- Attribute assignment
- Item assignment
- Methods that modify state
- Modifying an object's own attributes
- Name assignment

**Immutability**
- primitives
- tuples
- fozenset

## Tools for local thinking
- @property
- tuple (and namedtuple)
- commands (command pattern)

## Setup

- tic-tac-toe example
- @property used on player
- [[Player.NA]\*3]\*3] different from [[Player.NA\*3] for _ in range(3)]
- ((Player.NA, )\*3]\*3] works
- tuples instead of lists
- `namedtuple` is great
```
nt.__new__.defaults__
```

## Command pattern

## Iteration

