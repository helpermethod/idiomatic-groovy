# idiomatic-groovy

## Functional Programming

### Bad

```groovy
def result = []

for (c in ['a', 'b', 'c']) {
    result << c.toUpperCase()
}
```

### Better

```groovy
['a', 'b', 'c'].collect { it.toUpperCase() }
```

### Best

```groovy
['a', 'b', 'c']*.toUpperCase()
```
