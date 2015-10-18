# PracticeProblems

## General Problems

### Decimal to Binary

Write a program that accepts a base ten (non-fractional) number at the command line and outputs the binary representation of that number

### Integer to English

Write a program that takes an integer and displays the English name of that value.

You should support both positive and negative numbers, in the range supported by a 32-bit integer (approximately -2 billion to 2 billion).

### Recursive Factorial

Write a function that correctly computes the factorial of a number recursively. 

## Object Oriented Problems

### Shape

Define a Shape object, where the object is any two dimensional figure, and has the following characteristics: a name, a perimeter, and a surface area.

### Circle

Define a subclass of your Shape class and call it Circle. It should retain and accurately output the values of the aforementioned characteristics of a Shape.

### Triangle

Define a subclass of your Shape class and call it Triangle. This time, the name of the triangle should take into account if it is equilateral (all 3 sides are the same length), isoceles (only 2 sides are the same length), or scalene (no 2 sides are the same).

## C++ Problems

### Reverse linked list

Write a function that takes in a `forward_list` and prints its contents from back to front.

### Sorting a linked list

Write a function that sorts a `list` of doubles and returns it.

### Overloading <<

Given the following class:

```cpp
class CatTank {
public:
    // Initializes a CatTank from guns and feelings.
    CatTank(int guns, std::string feelings);

    // Kills another CatTank, decrements morality.
    void kill(CatTank other);
private:
    // Doesn't exist.
    int morality;
    std::string feelings;
};
```

Overload the operator << so that one can directly std::cout a CatTank.

## Robotics Problems

### PID Introduction

Write a proportional-integral-derivative control loop that regulates a motor value to a target speed from the current speed.  You can use the WPILib built in PID functionality.

### Sensor Mapping

Imagine you are operating in a `while (true)` loop where you can get two values from a sensor, a distance reading `getDistance()` and an angle reading `getAngle()`.  From these readings compile a 2D boolean image.

### Kinematics and Control

Kiwi drive is a drivetrain with three omniwheels arranged at the edges of a robot in an equilateral triangle, as such:

![Kiwi drive diagram](http://i.stack.imgur.com/x6u31.png)

Write a function that maps a 3d joystick input of X velocity, Y veloctity, and $\theta$ velocity scaled from -100 to 100 to three motor values scaled -100 to 100.   This question requires physics background, in particular vectors and torque.  We recommend working in groups.  

## Computer Vision Problems

### Tracking a ball

Write a program using openCV that tracks the position of a ball in 2D space.  If you're feeling adventurous, try doing it in 3D space.  If you're feeling super duper adventurous, try tracking two identical balls at the same time while keeping track of which is which.

### Shape identification

Write a program that can identify the shape and color of regular polygons from a webcam feed, and track them in 2D space.

### Object Learning

Write a program that can take a picture of an object, have a user select the object from the picture and track the object in 2D space from a continuous webcam input.
