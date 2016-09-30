# Idiomatic Groovy

## Functional Programming

### Filtering a list

* Bad

```groovy
def result = []

for (c in [1, 2, 3, 4]) {
    if (c % 2 == 0) {
        result << c
    }
}
```

* Good 

```groovy
[1, 2, 3, 4].findAll {
   it % 2 == 0
}
```

```groovy
def result = []
```

Applying a function to every element of a list

* Bad

```groovy
def result = []

for (c in ['a', 'b', 'c']) {
    result << c.toUpperCase()
}
```

* Better

```groovy
['a', 'b', 'c'].collect { it.toUpperCase() }
```

* Good

```groovy
['a', 'b', 'c']*.toUpperCase()
```
