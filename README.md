# Idiomatic Groovy

## Collections

* Removing all instances of an element

```groovy
// bad
['a', null, 'b', null, 'c'].removeAll { it == null }

// better
['a', null, 'b', null, 'c'].findAll { it != null }

// good
['a', null, 'b', null, 'c'] - null
```

## Functional Programming

* Filtering a list

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

* Applying a function to every element in a list

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
