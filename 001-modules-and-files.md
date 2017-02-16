# Modules and files

## Modules

`String` is a module.

String.length("hello"), `length` is a function exposed by the String module.

String module documentation: https://hexdocs.pm/elixir/String.html

Or..? See the 001 lesson.

### Define a module

This is a module definition:

```
defmodule Math do
  def sum(a, b) do
    a + b
  end
end
```
We can define a module directly in the REPL, but if we want to recall it without rewrite it, it's better
to write it inside a file called `math.ex`. Then we must compile ti using `elixirc math.ex`: this
will produce a file called `Elixir.Math.beam` (it's a bytecode file like a jvm .class file) in the current directory, that will be loaded
automatically the next time we invoke the iex REPL and we'll be able to execute `Math.sum(1, 2)`. TRY IT!

### Script!

In addition to the Elixir file extension .ex, Elixir also supports .exs files for scripting (like Groovy files).

Elixir treats both files exactly the same way, the only difference is in intention. .ex files are meant to be compiled while .exs files are used for scripting.

When executed, both extensions compile and load their modules into memory, although only .ex files write their bytecode to disk in the format of .beam files.

Save this to a file called `math.exs` and then execute `elixir math.exs`:

```
defmodule Math do
  def sum(a, b) do
    a + b
  end
end

IO.puts Math.sum(1, 2)
```

### Enigma

This title was a joke (?).

Try to call `do_sum` from iex or from a script:

```
defmodule Math do
  def sum(a, b) do
    do_sum(a, b)
  end

  defp do_sum(a, b) do
    a + b
  end
end
```

### Great software needs great tools
This is a partial quote from "Free software needs free tools", [Benjamin Mako Hill].

From iex: `:observer-start`.

#### NastyMath

Run in iex:

```
defmodule NastyMath do
  def sum(a, b) do
    sum(a, b)
  end
end

NastyMath.sum(1,2)
```

### 1,2,3 Elixir basic types

(grabbed from https://learnxinyminutes.com/docs/elixir/)

#### There are numbers

```
3    # integer
0x1F # integer
3.0  # float
```

#### Atoms, that are literals, a constant with name. They start with `:`.

```
:hello # atom
```

#### Tuples that are stored contiguously in memory.

```
{1,2,3} # tuple
```

#### We can access a tuple element with the `elem` function:

```
elem({1, 2, 3}, 0) #=> 1
```

#### Lists that are implemented as linked lists.

```
[1,2,3] # list
```

#### We can access the head and tail of a list as follows:

```
[head | tail] = [1,2,3]
head #=> 1
tail #=> [2,3]
```

### Random facts

Single line comments start with a number `#` symbol.

There's no multi-line comment, but you can stack multiple comments.


## Learning resources

- `h def`
- `h defp`

## Homework

- submodules
- modules hierachy flattening
