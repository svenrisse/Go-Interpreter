# Monkey Programming Language

**Monkey interpreter & compiler implementation in Go, based on Thorsten Ball's [Writing An Interpreter In Go](https://interpreterbook.com/) and [Writing A Compiler In Go](https://compilerbook.com/) books.**

## Features
* AST
* Tokenizer
* Parser
* Lexer
* Evaluator
* Compiler
* SymbolTable
* VirtualMachine
* Builtin Functions
* Functions & Closures
* Read–Eval–Print Loop

## Usage

### 1. Install


### 2. Test

```sh
$ 
```

### 3. Run

```sh
$ 
```

```bash
Monkey Compiler v0.2.0
>>> "Hello, " + "World!"
Hello, World!
>>>
```

## Examples

### Functions

```rust
[1, 2 * 2, 3 + 3]
```


### Function Call

```rust
let identity = fn(x) { x; }; identity(7); //7
```

```rust
let add = fn(a, b) { a + b }; 
let sub = fn(a, b) { a - b }; 
let applyFunc = fn(a, b, func) { 
    func(a, b) 
}; 
applyFunc(10, 2, sub); //8
```

### If


```rust
if (x < y) { z } else { w }
```

### Nested If

```rust
if (2 > 1) { if (3 > 1) { return 7; } return 0; }
```

### HashMap

```rust
{"one": 0 + 1, "two": 10 - 8, "ten": 50 / 5}
```

### Arrays

```rust
let arr = [1, 2 * 2, 3 + 3] //arr[1 + 1] => returns 6
```

### Operator Precedence

```rust
3 + 4 * 5 == 3 * 1 + 4 * 5 //((3 + (4 * 5)) == ((3 * 1) + (4 * 5)))
```

### Error Handlers

```rust
if (10 > 1) { if (10 > 1) { return true + false; } return 1; } //unknown operator: BOOLEAN + BOOLEAN
```

```rust
let newAdder = fn(x) { fn(y) { x + y } }; let addTwo = newAdder(2); x //identifier not found: x
```

## Complete Example

### Builtin

```rust
let map = fn(arr, f) {
	let iter = fn(arr, accumulated) {
		if (len(arr) == 0) {
			accumulated
		} else {
			iter(rest(arr), push(accumulated, f(first(arr))));
		}
	};
	iter(arr, []);
};
let a = [1, 2, 3, 4];
let double = fn(x) { x * 2 };
map(a, double);
```

### HashMap

```rust
let people = [{"name": "Alice", "age": 24}, {"name": "Anna", "age": 28}];
let getAge = fn(person) { person["name"]; };
return getAge(people[0]) + getAge(people[1]);
```

## Benchmark

```sh
$ 
$ 
```
 
## License

MIT License ([LICENSE](LICENSE)).
