---
layout: post
title: C++ Programming Project - Digital Rain
tags: cpp coding project
categories: demo
---
## Introduction

This project ia a modern C++ console application that simulates the digital rain effect similar to one that is seen in the Matrix movies. 
The program generates a visually dynamic stream of falling characters. It utilizes windows console API functions for cursor manipulations and text coloring.
The code in the project is structured using Object-Oriented Programming.

About the author: My name is Dan Koskiranta and I am final-year BEng (Honours) student in Software & Electronic Engineering with an interest in developing my skills in lower-level languages like C++.

## Design & Test

The program is structured using a class-based design. I made a class called DigitalRain and the project is built around this class. This class contains the functions responsible for handling the movement of the characters (falling effect), controlling cursor positions, and changing text colors in the console. The program uses vectors to store data such as the current positions (xPositions and yPositions) of characters and also for the number of characters. Each character has a random speed and a random character assigned to it. The random speeds range between 2 and 6, ensuring that each character falls at a different rate which creates the dynamic visual effect. the characters are randomly selected from a range of ASCII codes, so each "raindrop" can be a different symbol. The program uses the rand() function to generate random speeds and characters.

The project is split between five files, each with a specific responsibility. This is done to enhance readability, maintainability, and testing. The five files are: main.cpp, DigitalRain.cpp, DigitalTest.cpp, Digitaltest.h, and DigitalRain.h. 
- main.cpp is the entry point for the program, where the main() function is located. It initializes the DigitalRain object and calls the necessary functions to begin the character fall.
- DigitalRain.cpp is responsible for implementing the core functionality of the digital rain effect. It defines the constructors for the DigitalRain class and the file contains the implementation of the key functions like moving the console cursor and printing the falling characters.
- DigitalTest.cpp is responsible for implementing test functions that ensures that the DigitalRain class behaves as expected. It contains unit tests that verify the correctness of functions like GotoXY() and DrawCharacters().
- DigitalRain.h file defines the interface for the DigitalRain class. The DigitalRain class is declared here, serving as a blueprint for the implementation in DigitalRain.cpp. It declares the constructors that are responsible for initializing the class and the file declares the public functions that the class will expose to the rest of the program like GotoXY() and DrawCharacters().
- DigitalTest.h declares the unit test cases used in DigitalTest.cpp. The purpose of these unit tests is to test correctness and functionality of the DigitalRain class.

## Algorithm

The DigitalRain program simulates a digital rain effect, where characters fall from the top of the screen to the bottom and reset once all characters have reached the bottom. 
- In this step, the program initializes the necessary data structures to manage the falling characters. It defines a set number of characters and creates several vectors to store important properties for each character. This approach was based on concepts covered in the lecture slides and our previous labs, which provided guidance on structuring data using vectors.
  ![image](https://github.com/user-attachments/assets/ea9c7292-5bd9-4b01-8ed2-0810645a98c3)



- This function, GotoXY was provided by my lecturer and it is used to move the console cursor to a specific position on the screen. The function utilizes Windows API functions to move the cursor to the specified coordinates.
  
  ![image](https://github.com/user-attachments/assets/d4e5e9c0-edb2-485f-b2cb-8b322ab5c58a)


- This loop iterates over all the characters, printing each one at its current position only if it has not yet reached the bottom. The allCharsAtBottom counter keeps track of how many characters have reached the bottom.
  
  ![image](https://github.com/user-attachments/assets/99e3d752-7c8b-422d-9dc3-5b8227ddad6a)

- Here, the program initializes the starting positions and attributes for the falling characters. It seeds the random number generator to ensure different outputs on each run, each character will be five spaces apart horizontally, and all characters will start falling at the top. The rand() function is used to generate random characters and random falling speeds for each character. To better understand how to implement both the random character selection and the varying falling speeds, I used ChatGPT for guidance and also referenced cppreference.com to understand the rand() function.
  
  ![image](https://github.com/user-attachments/assets/c4a9ebb0-f46c-48b1-a419-7576204f6094)


- To control the speed at which the characters are falling, a delay is added using std::this_thread::sleep_for() function. The program uses this delay to make the DigitalRain effect more visually appealing, creating a smoother animation rather than having characters falling too fast or instantly. The delay duration is expressed in milliseconds (1 second = 1000 milliseconds):

  ![image](https://github.com/user-attachments/assets/33eb4ad1-59c2-4dbb-911e-b8ed6137303c)

- Each character moves down at its own speed. This loop first checks if a character has reached the bottom. If not, it increments the time counter to control movement speed. When the counter reaches the character's speed threshold, the character moves down by one position. If a character reaches the bottom (y = 30), it is marked as "at the bottom" and locked in place.
- While working on this section of the code, I wanted each character to fall at a different speed, but I wasn't sure at first on how to implement it. To solve this, I used ChatGPT to help me to structure the logic. The solution involves using a timeCounters array to track when each character should move down based on its assigned speed.
- Every frame, timeCounters[i] increases, and once it reaches the character's assigned speed (speeds[i]), the character moves down by one position. Then the timer resets, and the process repeats. This ensures that some characters fall faster than others, creating a more dynamic visual effect.

  ![image](https://github.com/user-attachments/assets/8067a722-8cd7-435f-b038-cc382686bfc4)

- When the charIsAtBottom is set, this for loop will then count how many characters have reached the bottom.

  ![image](https://github.com/user-attachments/assets/72e66b17-65d6-4ee7-b8ae-075152662eaa)

- If all characters have reached the bottom, the screen is cleared (system("cls")), and their positions and attributes are reset. I found the system("cls") on StackOverflow https://stackoverflow.com/questions/74446197/c-how-does-if-systemcls-systemclear-work.
- During the project, I encountered some issues with the program not properly resetting when all characters reached the bottom of the screen. To solve this, I used ChatGPT to help me to figure out how to accurately track when each character had reached the bottom. ChatGPT provided me with a for loop to count the number of characters at the bottom and suggested using a flag (charIsAtBottom[i] = true;) to indicate when a character had reached the bottom. With this solution, I was able to ensure the program properly resets once all the characters have fallen.

  ![image](https://github.com/user-attachments/assets/99422150-d555-4dca-8896-53498f0cc163)

- Here is the output of the program, showing the falling characters with different speeds and creating the dynamic visual effect.

  ![Digital Rain in action](https://raw.githubusercontent.com/DanKos22/digital-rain-cpp/main/docs/assets/images/Recording%20%2353.gif)




## Reflection

Working on this Digital Rain project allowed me to deepen my understanding of how to structure C++ code properly and how to divide the code between files for better organization and maintainability. I learned how to implement constructors effectively and gained a deeper appreciation for the importance of header guards in preventing multiple inclusions of the same header file. Overall, this project provided a great opportunity to enhance my knowledge of object-oriented programming in C++.

Throughout this project, I became more comfortable working with vectors in C++. I learned how to use them to store and manage dynamic data, such as tracking the positions, speeds, and states of falling characters. Before this project, I didn't quite understand their advantages, but I realized that they function similarly to arrays while offering greater flexibility and ease of management. 

Challenges faced during this project included figuring out how to print different characters falling at different speeds. To achieve the random speeds and characters, I utilized the rand() function. Another significant challenge was ensuring the characters reset correctly after reaching the bottom of the screen, which I solved using a flag.  For problem-solving, I relied on ChatGPT, lecture slides, and previous labs, all of which helped me throughout the project.

I was particularly excited to build this Digital Rain project because I have always been fascinated by the iconic look of the falling code in the Matrix movies. As a fan of the first movie, recreating the digital rain effect in C++ made the project especially engaging. Seeing the characters cascade down the screen was a rewarding experience. 


## References

- https://en.cppreference.com/w/
- https://chatgpt.com/
- https://www.w3schools.com/cpp/cpp_oop.asp



You can add an image that has been uploaded to the repository in a /docs/assets/images folder.

<img src="https://raw.githubusercontent.com/DanKos22/digital-rain-cpp/main/docs/assets/images/Project.png" width="400" height="300">
