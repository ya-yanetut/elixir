# Hello Elixir

## Install

`docker run -it --rm elixir`

### Other ways

`brew install elixir`

More install options at http://elixir-lang.org/install.html

Note: erlang is required to run elixir. Why? Because Elixir is a language that runs on the Erlang VM. Think it like Scala/JVM. So you can call any Erlang function from Elixir.

## Run it

The docker run will show a prompt with the Elixir REPL: it's called [IEx](https://hexdocs.pm/iex/IEx.html).

`iex> 40 + 2`

### The help system

This will show the available documentation for a give module/function:

`iex> h String`

With TAB you can see all available functions for a given module:

`iex> String. TAB`

### Examples

```
iex> String.split(" a b    c ", " ", trim: true)
iex> String.split(" a b    c ", " ", trim: false)
```

See also: http://elixir-lang.org/getting-started/basic-types.html

### Quit the REPL
CRTL+C CTRL+C

## Learning resources

http://elixir-lang.org/learning.html
https://github.com/hemanth/functional-programming-jargon








