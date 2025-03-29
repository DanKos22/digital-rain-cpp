---
layout: post
title: C++ Programming Project Digital Rain
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
- DigitalTest.h declares the unit test cases used in DigitalTest.cpp. The purpose of these unit tests is to test correctness and functionality of the DigitalRain class.

## Algorithm

The DigitalRain program simulates a digital rain effect, where characters fall from the top of the screen to the bottom. 
- In this step, the program initializes the necessary data structures to manage the falling characters. It defines a set number of characters and creates several vectors to store important properties for each character.
  ![image](https://github.com/user-attachments/assets/ea9c7292-5bd9-4b01-8ed2-0810645a98c3)



- To move the cursor to the correct position, the program uses the GotoXY() function, which uses Windows API functions to move the cursor to the specified coordinates.
  
  ![image](https://github.com/user-attachments/assets/d4e5e9c0-edb2-485f-b2cb-8b322ab5c58a)


- This loop iterates over all the characters, printing each one at its current position only if it has not yet reached the bottom. The allCharsAtBottom counter keeps track of how many characters have reached the bottom.
  
  ![image](https://github.com/user-attachments/assets/99e3d752-7c8b-422d-9dc3-5b8227ddad6a)

- Here, the program initializes the starting positions and attributes for the falling characters. It seeds the random number generator to ensure different outputs on each run, each character will be five spaces apart horizontally, and all characters will start falling at the top. The rand() function is used to generate random characters and random falling speeds for each character.
  ![image](https://github.com/user-attachments/assets/c4a9ebb0-f46c-48b1-a419-7576204f6094)


- To control the speed at which the characters are falling, a delay is added using std::this_thread::sleep_for() function. The program uses this delay to make the DigitalRain effect more visually appealing, creating a smoother animation rather than having characters falling too fast or instantly. The delay duration is expressed in milliseconds (1 second = 1000 milliseconds):

  ![image](https://github.com/user-attachments/assets/33eb4ad1-59c2-4dbb-911e-b8ed6137303c)

- Each character moves down at its own speed. This loop first checks if a character has reached the bottom. If not, it increments the time counter to control movement speed. When the counter reaches the character's speed threshold, the character moves down by one position. If a character reaches the bottom (y = 30), it is marked as "at the bottom" and locked in place.
- While working on this section of the code, I wanted each character to fall at a different speed, but I wasn't sure at first on how to implement it. To solve this, I used ChatGPT to help me to structure the logic. The solution involves using a timeCounters array to track when each character should move down based on its assigned speed.
- Every frame, timeCounters[i] increases, and once it reaches the character's assigned speed (speeds[i]), the character moves down by one position. Then the timer resets, and the process repeats. This ensures that some characters fall faster than others, creating a more dynamic visual effect.

  ![image](https://github.com/user-attachments/assets/8067a722-8cd7-435f-b038-cc382686bfc4)

- When the charIsAtBottom is set, this for loop will then count how many characters have reached the bottom.

  ![image](https://github.com/user-attachments/assets/72e66b17-65d6-4ee7-b8ae-075152662eaa)

- If all characters have reached the bottom, the screen is cleared (system("cls")), and their positions and attributes are reset.

  ![image](https://github.com/user-attachments/assets/99422150-d555-4dca-8896-53498f0cc163)




 





## Problem-Solving


## Modern C++ Insight & Reflection

Font can be *Italic* or **Bold**.

Code can be highlighted with 'backticks'.

Hyperlinks look like this: [GitHub Help](https://help.github.com/).

A bullet list:

- vectors
- algorithms
- iterators

You can add an image that has been uploaded to the repository in a /docs/assets/images folder.

<img src="https://raw.githubusercontent.com/DanKos22/digital-rain-cpp/main/docs/assets/images/Project.png" width="400" height="300">
