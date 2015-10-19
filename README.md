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

Note: a lot of these problems require writing "dummy functions" to act as a simulation environent.  You may not necessarily know if your code works before you ask somebody to look it over.  If you're ambitious (like Caesar), try making accurate simulation dummy functions rather than just returning a random number.  This will help you test later on.

### Odometry

You are given dummy functions `void setLeftMotor(int power)` and `void setRightMotor(int power)`, where power is -100 to 100 with 0 being brake.  Write a program that drives in a circle.

Now write a program that drives in a square, assuming that while turning at full power the robot takes 0.4 seconds to turn 90 degrees.

Now here comes the tricky part: write a program that drives the robot in a sine wave.  To be more clear, the robot follows an arbitrarily scaled version of the the parametric equation `y = sin(t)` , `x = 0`.  This can be seen in the below gif, where the robot position is represented by the circle.  Write a program that makes the robot move in this manner.

![siny robot](http://i.giphy.com/sajxSgoRSfh60.gif)


### Gyroscope

Imagine you have a sensor that gives you your current rotational velocity.   Write a `while (true)` that turns a specific angle by getting rotational velocity in degrees/sec from a dummy function `float getGyro()`.  You can adjust your robot turning velocity with the dummy function `void turn(int power)`, power being an integer from -100 to 100 (0 being brake).

Now try using this sensor to keep track of robot orientation from 0-360, starting at an orientation of 0.

### Sensor Mapping

Imagine you have a constantly rotating distance sensor strapped to the top of your robot.  The sensor can read a distance value (like an ultrasonic sensor), in addition to the angle that it is currently at (0-360, clockwise where 0 is pointing forwards).  Your task is to form a 2d image of nearby obstacles using this sensor.  You are operating in a `while (true)` loop, and can call dummy functions `float getDistance()` and `float getAngle()`.  Over time build a 2D boolean array reprenting your image.

The previous paragraph assumes that the sensor reads in a direct line.  However, most real distance sensors have something called a "beam width."  For example, imagine you have an ultrasonic sensor with a pencil directly in front of it.  If you rotate it a little bit so that the sensor is not pointing directly at the pencil, it might still read a short distance reading as if the pencil isn't there.  Alternatively if the sensor were pointing directly at the pencil it might not see it at all.  Basically, the concept of a beam angle introduces error into the equation, the bane of a robotics programmer.  All sensor readings will have associated error, something we'll have to deal with.  For now, define an arbitrary beam angle variable and try to compensate in your program.

If you're really insane, there's yet another degree of complexity we can add to this fun problem.  Currently you are mapping discrete points rather than lines.  If the robot is trapped in a circular room but has only taken 4 sensor readings, it only knows that there are 4 single-pixel obstacles around itself.   To compensate for this we must maintain yet another 2D image, where a predicted image is formed by connecting the dots on the first image.   Try different methods of isolating discrete obstacles, for example defining a threshold pixel distance where dots should or should not be connected.

### Kinematics and Control

Kiwi drive is a drivetrain with three omniwheels arranged at the edges of a robot in an equilateral triangle, as such:

![Kiwi drive diagram](http://i.stack.imgur.com/x6u31.png)

Write a function that maps a 3d joystick input of X velocity, Y veloctity, and rotational velocity scaled from -100 to 100 to three motor values scaled -100 to 100.   This question requires physics background, in particular vectors and torque.  We recommend working in groups.  

If you were succesful, try it the other way around; from given motor inputs A, B, and C update the 3D position (x,y,theta) of a simulated robot.

## Computer Vision Problems

### Tracking a ball

Write a program using openCV that tracks the position of a ball in 2D space.  If you're feeling adventurous, try doing it in 3D space.  If you're feeling super duper adventurous, try tracking two identical balls at the same time while keeping track of which is which.

### Shape identification

Write a program that can identify the shape and color of regular polygons from a webcam feed, and track them in 2D space.

### Object Learning

Write a program that can take a picture of an object, have a user select the object from the picture and track the object in 2D space from a continuous webcam input.
