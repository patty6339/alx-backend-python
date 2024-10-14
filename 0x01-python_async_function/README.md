### **Async and Await Syntax**  
- `async` defines an asynchronous function, allowing it to run asynchronously.  
- `await` pauses execution of the function until the awaited asynchronous operation completes.  
- Example:
  ```python
  async def example():
      await some_async_function()
  ```

### **How to Execute an Async Program with asyncio**  
- Use `asyncio.run()` to execute the entry point of an async program.  
- Example:
  ```python
  import asyncio

  async def main():
      print("Running async program")

  asyncio.run(main())
  ```

### **How to Run Concurrent Coroutines**  
- Use `asyncio.gather()` to run multiple coroutines concurrently.  
- Example:
  ```python
  async def task1():
      print("Task 1")

  async def task2():
      print("Task 2")

  asyncio.run(asyncio.gather(task1(), task2()))
  ```

### **How to Create asyncio Tasks**  
- Use `asyncio.create_task()` to schedule coroutines to run concurrently as tasks.  
- Example:
  ```python
  async def some_task():
      print("Executing task")

  task = asyncio.create_task(some_task())
  await task
  ```

### **How to Use the Random Module**  
- Import the `random` module to generate random values.  
- Example:
  ```python
  import random

  print(random.randint(1, 10))  # Random integer between 1 and 10
  print(random.choice(['apple', 'banana', 'cherry']))  # Random choice from a list
  ```