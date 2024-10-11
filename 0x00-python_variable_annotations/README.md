### Advanced Python 


### 1. **Type Annotations in Python 3**
Type annotations in Python 3 allow you to specify the types of variables, function parameters, and return values. This improves code readability, enables better tooling support (e.g., static type checkers), and reduces runtime errors.

**Example:**
```python
def greet(name: str) -> str:
    return f"Hello, {name}!"
```
In the example above, the `name` parameter is annotated as a `str`, and the function is expected to return a `str`. While Python is dynamically typed, these annotations are not enforced at runtime, but they are useful for type checkers like `mypy`.

### 2. **Specifying Function Signatures and Variable Types**
Type annotations can be used to clearly define what types are expected for inputs and outputs of functions. Variables can also have their types explicitly declared for clarity.

**Example:**
```python
age: int = 25  # Variable type is int

def add(a: int, b: int) -> int:
    return a + b  # Both inputs and return type are integers
```

By specifying the types, other developers (or static analyzers) know exactly how the function should be used, helping to catch potential errors before runtime.

### 3. **Duck Typing**
Duck typing is a concept in Python where the type or class of an object is less important than the methods or properties it supports. "If it looks like a duck and quacks like a duck, it's a duck." In other words, as long as an object behaves as expected, its type doesn't matter.

**Example:**
```python
class Duck:
    def quack(self):
        print("Quack!")

class Person:
    def quack(self):
        print("I can quack too!")

def make_it_quack(duck_like):
    duck_like.quack()

make_it_quack(Duck())    # Prints: Quack!
make_it_quack(Person())  # Prints: I can quack too!
```
Both `Duck` and `Person` objects can be passed to `make_it_quack()` because they both have a `quack()` method, despite being different types.

### 4. **Validating Code with `mypy`**
`mypy` is a static type checker for Python that ensures your code adheres to the type annotations you've provided. It doesn't change how the code runs but can catch type-related errors before runtime.

To validate your code:
1. Install `mypy` with:  
   ```bash
   pip install mypy
   ```
2. Run it against your script:
   ```bash
   mypy script.py
   ```

**Example:**
If you define a function like this:
```python
def double(x: int) -> int:
    return x * 2

double("10")  # Passes a string instead of an int
```
`mypy` will raise an error indicating that you passed a `str` when an `int` was expected:
```
error: Argument 1 to "double" has incompatible type "str"; expected "int"
```