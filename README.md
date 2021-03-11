This is a demo for Ruby 3 type checking.

## Run main

```
ruby main.rb
```

## Type checking

* Use [Steep](https://github.com/soutaro/steep)

### Command

```
steep check
```

### Setup

#### Install

```
gem install steep
steep init
```

#### Steepfile

Update `Steepfile`.

```rb:Steepfile
target :lib do
  check "lib"
  check "main.rb"
  signature "sig"
end
```

#### typeprof

`typeprof` is a Built-in library of Ruby 3 in order to autoamtically generate type definitions from `.rb` files.

```
typeprof main.rb
```

```
# Classes
class Person
  def greet: (String name) -> nil
end
```

#### rbs

And, create `sig` directory and `person.rbs` with the result of the `typeprof` command:

```rb:sig/person.rbs
class Person
  def greet: (String name) -> nil
end
```