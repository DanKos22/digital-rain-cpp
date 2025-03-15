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
- DigitalRain.cpp is responsible for implementing the core functionality of the digital rain effect. It defines the constructors for the DigitalRain class and the file contains the implementation of key the functions like moving the console cursor and printing the falling characters.

## Algorithm


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
