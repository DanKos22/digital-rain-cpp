---
layout: post
title: A Project in Modern C++
tags: cpp coding project
categories: demo
---
## Introduction

This project ia a modern C++ console application that simulates the digital rain effect similar to one that is seen in the Matrix movies. 
The program generates a visually dynamic stream of falling characters. It utilizes windows console API functions for cursor manipulations and text coloring.
The code in the project is structured using Object-Oriented Programming.

## Design & Test

The program is structured using classes and objects. I made a class called DigitalRain and the project is built around this class. This class contains the functions responsible for handling the movement of the characters (falling effect), controlling cursor positions, and changing text colors in the console. The program uses vectors to store data such as the current positions (xPositions and yPositions) of characters and also for the number of characters.

The project is split between five files, each with a specific responsibility. This is done to enhance readability, maintainability, and testing. The five files are: main.cpp, DigitalRain.cpp, DigitalTest.cpp, Digitaltest.h, and DigitalRain.h. 
- main.cpp is the entry point for the program, where the main() function is located. It initializes the DigitalRain object and calls the necessary functions to begin the character fall.
- DigitalRain.cpp is responsible for implementing the core functionality of the digital rain effect. It defines the constructors for the DigitalRain class and the file contains the implementation of the key functions like moving the console cursor and printing the falling characters.
- DigitalTest.cpp is responsible for implementing test functions that ensures that the DigitalRain class behaves as expected. It contains unit tests that verify the correctness of functions like GotoXY() and DrawCharacters(). These tests help to ensure that the program functions correctly.
- DigitalRain.h file defines the interface for the DigitalRain class. The DigitalRain class is declared here, serving as a blueprint for the implementation in DigitalRain.cpp. It declares the constructors that are responsible for initializing the class and the file declares the public functions that the class will expose to the rest of the program like GotoXY() and DrawCharacters().
- DigitalTest.h declares the unit test cases used in DigitalTest.cpp. The purpose of these unit tests is to test correctness and functionality of the DigitalRain class

## Algorithm

The DigitalRain program simulates a digital rain effect, where characters fall from the top of the screen to the bottom. 
- In this step, the program initializes the necessary data structures for the falling characters.
  ![image](https://github.com/user-attachments/assets/61b7ee0c-e824-4153-9a4b-567600e62a25)

- To move the cursor to the correct position, the program uses the GotoXY() function, which uses Windows API functions to move the cursor to the specified coordinates.
  ![image](https://github.com/user-attachments/assets/bc583c1b-4458-4940-8fdb-ecd21762f4f8)

  




## Problem-Solving


## Modern C++ Insight & Refelction

Font can be *Italic* or **Bold**.

Code can be highlighted with 'backticks'.

Hyperlinks look like this: [GitHub Help](https://help.github.com/).

A bullet list:

- vectors
- algorithms
- iterators

You can add an image that has been uploaded to the repository in a /docs/assets/images folder.

<img src="https://raw.githubusercontent.com/DanKos22/digital-rain-cpp/main/docs/assets/images/Project.png" width="400" height="300">
