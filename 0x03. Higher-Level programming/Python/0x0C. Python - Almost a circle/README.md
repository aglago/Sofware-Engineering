# Python - Almost a circle

This repository contains detailed notes on python classes, testing, JSON, `*args`, `**kwargs` serving as a comprehensive resource for software engineering enthusiasts, students, and professionals.

## Table of Contents
+ [Requirements](#requirements)
+ [Resources](#resources)
+ [Learning Objectives](#learning-objectives)
+ [Notes](#Notes)
+ [Exercises](#exercises)
+ [Project](#project)
+ [Summary](#summary)
+ [Next Lesson](#next-lesson)

## Requirements
### Python Scripts
- Allowed editors: vi, vim, emacs
- All your files will be interpreted/compiled on Ubuntu 20.04 LTS using python3 (version 3.8.5)
- All your files should end with a new line
- The first line of all your files should be exactly #!/usr/bin/python3
- A README.md file, at the root of the folder of the project, is mandatory
- Your code should use the pycodestyle (`version 2.8.*`)
- All your files must be executable
- The length of your files will be tested using wc
- All your modules should have a documentation (python3 -c 'print(__import__("my_module").__doc__)')
- All your classes should have a documentation (python3 -c 'print(__import__("my_module").MyClass.__doc__)')
- All your functions (inside and outside a class) should have a documentation `(python3 -c 'print(__import__("my_module").my_function.__doc__)'` and `python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)')`
- A documentation is not a simple word, it’s a real sentence explaining what’s the purpose of the module, class or method (the length of it will be verified)

### Python Unit Tests
- Allowed editors: `vi`, `vim`, `emacs`
- All your files should end with a new line
- All your test files should be inside a folder `tests`
- You have to use the [unittest module](https://docs.python.org/3.4/library/unittest.html#module-unittest)
- All your test files should be python files (extension: `.py`)
- All your test files and folders should start with `test_`
- Your file organization in the tests folder should be the same as your project: ex: for `models/base.py`, unit tests must be in: `tests/test_models/test_base.py`
- All your tests should be executed by using this command: `python3 -m unittest discover tests`
- You can also test file by file by using this command: `python3 -m unittest tests/test_models/test_base.py`
- We strongly encourage you to work together on test cases so that you don’t miss any edge case

## Resources
- [args/kwargs](https://yasoob.me/2013/08/04/args-and-kwargs-in-python-explained/)
- [JSON encoder and decoder](https://docs.python.org/3/library/json.html)
- [unittest module](https://docs.python.org/3.4/library/unittest.html#module-unittest)
- [Python test cheatsheet](https://www.pythonsheets.com/notes/python-tests.html)

## Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

## General
- What is Unit testing and how to implement it in a large project
- How to serialize and deserialize a Class
- How to write and read a JSON file
- What is `*args` and how to use it
- What is `**kwargs` and how to use it
- How to handle named arguments in a function

## Notes
+ [Go through notes here](./notes.md)

## Exercises
+ [Here are some exercises to try you hands on](./exercises.md)

## Project

## Summary
Today, we delved into various aspects of Python development, starting with the fundamentals of unit testing and the importance of test coverage for robust code validation. We explored the concepts of mocking and stubbing as techniques to isolate code during testing. Test-Driven Development (TDD) was introduced as a methodology where tests precede code implementation, promoting early bug detection and improved code design. Additionally, we covered practical aspects such as writing and reading JSON files using the `json` module. Lastly, we discussed the flexibility provided by `*args` and `**kwargs` in function parameters, allowing for the handling of variable numbers of positional and keyword arguments. This comprehensive overview provides a foundation for effective Python development, emphasizing testing practices and code organization.

## Next Lesson
[Command line for the win]()
