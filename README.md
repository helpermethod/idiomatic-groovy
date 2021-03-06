# Idiomatic Groovy

## General

* Omit semicolons

```groovy
// bad
def number = 1;

// good
def number = 1
```

* Omit parentheses for single method calls

```groovy
// bad
println('Hello World!')

// good
println 'Hello World!'
```

* Use parentheses for chained method calls

## Strings

* Use string interpolation for concatenation

```groovy
def lang = 'Groovy'

// bad
println lang + ' rocks!'

// good
println "$lang rocks!"
```

* Use triple-quotes for multiline strings

```groovy
```

## Collections

* Use the `-` operator for removing all instances of an element

```groovy
// bad
['a', null, 'b', null, 'c'].removeAll { it == null }

// better
['a', null, 'b', null, 'c'].findAll { it != null }

// good
['a', null, 'b', null, 'c'] - null
```

* Use the `+` operator for concatenation

```groovy
// bad
def l = ['a', 'b', 'c']
l.addAll ['d', 'e', 'f']

// good
l + ['d', 'e', 'f']
```

## Functional Programming

* Use `findAll` for filtering collections

```groovy
// bad
def result = []

for (c in [1, 2, 3, 4]) {
    if (c % 2 == 0) {
        result << c
    }
}

// good
[1, 2, 3, 4].findAll {
   it % 2 == 0
}
```

* Use `collect` to apply a function to every element of a collection

```groovy
// bad
def result = []

for (c in ['a', 'b', 'c']) {
    result << c.toUpperCase()
}

// better
['a', 'b', 'c'].collect { it.toUpperCase() }

// good
['a', 'b', 'c']*.toUpperCase()
```
