## How to create a thread?
- Extending `Thread` class and override run method
    ```java
    class NewThread extends Thread{
        public void run(){
            System.out.print("new thread running");
        }
    }
    ```
- Implementing `Runnable` interface and override run method
    ```java
    class NewThread implements Runnable{
        public void run(){
            System.out.print("new thread running");
        }
    }
    ```
## How to run a thread?
- Depends on how we create a thread, we run it differently.
- If we extends `Thread` class then we instantiate the class and call `start()` method
  ```java
  NewThread newThread = new NewThread();
  newThread.start();
  ```
- If we implement `Runnable`, we instantiate the class first, then create a `Thread` object from it and call `start()` method
  ```java
  NewThread newThread = new NewThread();
  Thread thread = new Thread(newThread);
  thread.start();
  ```

## What are the different states of a thread?
- There are 5 states of a thread:
  - New: created but `start()` is not called
  - Runnable: `start()` is called but doesn't have CPU to run
  - Running: running
  - Blocked/Waiting: waiting for something or being blocked by I/O
  - Terminated/Dead

## What is Thread priority?
- The higher the priority, the more CPU the scheduler could allocate to run the thread.
- By default a thread's priority is 5 (1-10)
- To set priority, call `setPriority()`

## What is `ExecutorService`?
- It's a new service to execute tasks asynchronously in the background.
  ```java
  ExecutorService service = Executors.newSingleThreadExecutor();
  service.execute(new Runnable(){
    public void run(){
        System.out.print("new thread running");
    }
  });
  service.shutdown();
  ```
## How to create an `ExecutorService`?
- `Executors.newSingleThreadExecutor()`: create a new thread
- `Executors.newFixedThreadPool()`: create a thread pool that reuses a fixed number of threads, all tasks are stored in a thread safe blocking queue
- `Executors.newScheduledThreadPool()`: create thread pool that can be configured to run after a delay or periodically, it uses a delay queue
- `Executors.newCachedThreadPool()`: create a cached thread pool with a synchronous queue, this queue only holds 1 task at a time and looks for a thread to assign the task, if there is no idle thread, it will create a new thread. It also can kill threads ilding for more than 60 seconds

## How to check if an `ExecutorService` executes successfully?
- Use `Future` to check if an `ExecutorService` executes successfully
  ```java
  ExecutorService service = Executors.newSingleThreadPool();
  Future futureFromCallable = service.submit(() -> "Running");
  //return null if executed successfully
  //block until the thread is done
  futureFromCallable.get();

  //return if the thread is done
  //non-blocking
  futureFromCallable.isDone();
  ```

## `Callable` vs `Runnable`?
- `Callable` has a `run()` method that returns value
- `Runnable` has a void `run()` method
