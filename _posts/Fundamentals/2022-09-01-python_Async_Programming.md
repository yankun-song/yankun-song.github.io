---
title: Python Async Programming
date: 2022-09-01 00:00:00 -500
categories: [Foundamentals]
tags: [Python, Async] # TAG names should always be lowercase
img_path: /assets/posts/
---

## Synchronous Programming

Each statement in your code is executed one after the other. This means each statement has to wait for the previous one to finish.

## Asynchronous Programming

Asynchrony, refers to the occurence of events indepentent of the main program flow.

## Coroutines

Coroutines are computer program components that generalize subroutines for non-preemptive multitasking, by allowing execution to be suspended and resumed.

## Async

When you add the `async` keyword in front of a function's definition, it's actually creating a wrapper around this function. It will return a coroutine object, which is just like an object, and can be executed.

## Async Event-Loop

The event loop is a programming construct or design pattern that waits for and dispatches events or messages in a program.

## example 1

```py
import asyncio

async def main():
   print("hello")
   await foo("text")
   print("finished")

async def foo(text):
   print(text)
   # put await in front of a coroutine to execute it
   await asyncio.sleep(1)

# adding the invocation of main to the event loop
asyncio.run(main())
```

In the example above, python would print out 'hello', then 'text', wait for 1s, then print 'finished'. The total time cost would be around 1.3s.

## example 2

```py
import asyncio

async def main():
   print("hello")
   task = asyncio.create_task(foo("text"))
   print("finished")

async def foo(text):
   print(text)
   await asyncio.sleep(1)

asyncio.run(main())
```

In the example above, python would print out 'hello', then 'finished', then 'text'. The total time cost would be around 0.3s.

## example 3

```py
import asyncio

async def main():
   print("hello")
   task = asyncio.create_task(foo("text"))
   await task
   print("finished")

async def foo(text):
   print(text)
   await asyncio.sleep(1)

asyncio.run(main())
```

In the example above, python would print out 'hello', then 'text', wait for 1s, then print 'finished'. The total time cost would be around 1.3s. Same as example 1.

## example 4

```py
import asyncio

async def main():
   print("hello")
   task = asyncio.create_task(foo("text"))
   await asyncio.sleep(1)
   print("finished")

async def foo(text):
   print(text)
   await asyncio.sleep(10)

asyncio.run(main())
```

In the example above, python would print out 'hello', then 'text', wait for 1s, then print 'finished'. The total time cost would be around 1.3s.

## example 5

```py
async def fetch_data():
    print('start fetching')
    await asyncio.sleep(2)
    print('done fetching')
    return {'data': 1}

async def print_numbers():
    for i in range(10):
        print(i)
        await asyncio.sleep(0.5)

async def main():
    task1 = asyncio.create_task(fetch_data())
    task2 = asyncio.create_task(print_numbers())
    value = await task1
    print(value)

asyncio.run(main())
```

The output would be "start fetching", "0--1--2--3", "done fetch" and {'data': 1}.

The reason is, first we execute `fetch_data`, then it will sleep for 2s. So the program will find something else to do, thus move to the creation and execution of `task2`. Inside `task2`, we are asked to sleep 0.5s, so the program will find something else to do, but `await task1` says, you can't go down any more, let's wait task1 to finish. Once task1 is done, we are able to go down and find some code to execute during each 0.5s sleep. So we print `value` and come to the end of the main function. The rest of `task2` will not be executed, because we are not told to wait for it.

## example 6

```py
async def fetch_data():
    print('start fetching')
    await asyncio.sleep(2)
    print('done fetching')
    return {'data': 1}

async def print_numbers():
    for i in range(10):
        print(i)
        await asyncio.sleep(0.5)

async def main():
    task1 = asyncio.create_task(fetch_data())
    value = await task1
    task2 = asyncio.create_task(print_numbers())
    print(value)

asyncio.run(main())
```

The output would be "start fetching", waiting 2s, "done fetch" and {'data': 1}, and "0".

The reason is, first we execute `fetch_data`, it prints out "start fetching", then it will sleep for 2s. So the program will find something else to do (go to next line). However, here we are told to wait `task1` to be finished. So we wait here, doing nothing else, until it is totally finished. Then we move to `task2`, print the first number, then sleep. During this sleep, we go down and print the value, and come to the end of main function, leading to the finish of this program.
