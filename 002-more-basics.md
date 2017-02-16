# More basics

## Operators

### Numbers

    is_integer(2)
    
    1 + 2
    5 * 5
    10 / 5 # always returns a float
    
    is_float(2.0)
    
    div(10,5) # integer division
    rem(10,3) # reminder
    rem(10,3) == rem 10, 3 # Elixir allows you to drop the parentheses when invoking named functions
    rem 10, 3 == rem(10,3) # ...?
    rem(10,3) == rem 10, 3 

    is_number(1)
    
    1 == 1.0
    1 === 1.0
    
    h ==/2
    h ===/2 # :)

### Lists

    [1, 2, 3] ++ [4, 5, 6]
    [1, 2, 3] -- [2]
    [1, 2, true, 3]

    length [1, 2, 3]
    
    list = [1, 2, 3]
    hd(list) # Lisp car
    tl(list) # Lisp cdr
    
### Strings
    
    "foo" <> "bar"
    "hellö #{:world}"
    
    IO.puts "hello\nworld"
    
    String.length("hellö")
    String.upcase("hellö")
    
    'hello' == "hello" # Single quotes are char lists, double quotes are strings
    
    i 'hello'
    i "hello"
    
### Atoms

Atoms are constants where their name is their own value. Some other languages (e.g. Lisp) call these symbols:
    
    :hello
    :hello == :world
    
### Booleans

Elixir provides three boolean operators:

- or
- and
- not

These operators are strict in the sense that they expect a boolean (true or false) as their first argument. `or` and `and` are short-circuit operators. They only execute the right side if the left side is not enough to determine the result:

    is_boolean(1)
    true and true
    true and 1 # err
    false or is_atom(:example)
    false and raise("This error will never be raised")

    is_atom(false) # OMG
    is_boolean(:false) # OMG 2
    true == :true # OMG 3
    
> Now it's clear that `true` and `false` are atoms :)
    
Besides these boolean operators, Elixir also provides `||`, `&&` and `!` which **accept arguments of any type**. For these operators, all values except `false` and `nil` will evaluate to true:

    1 || true
    nil && 13
    !1

> As a rule of thumb, use and, or and not when you are expecting booleans. If any of the arguments are non-boolean, use &&, || and !.

Elixir also provides `==`, `!=`, `===`, `!==`, `<=`, `>=`, `<`, and `>` as comparison operators.

In Elixir, we can compare two different data types (sorting):

    1 < :atom

#### A sacred order

    number < atom < reference < function < port < pid < tuple < map < list < bitstring

## Learning resources

- [Elixir operators](https://hexdocs.pm/elixir/master/operators.html)
- `h i/1`
