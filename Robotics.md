## Robotics Problems

Note: a lot of these problems require writing "dummy functions" to act as a simulation environment.  You may not even be able to fully test your code.  This is a valuable skill for robotics programming, as you often have limited access to the robot for testing and need to write code off board.  More advanced dummy functions can help get around this by creating a more accurate simulation environment.

### Odometry

You are given dummy functions `void setLeftMotor(int power)` and `void setRightMotor(int power)`, where power is -100 to 100 with 0 being brake.  Write a program that drives in a circle.

Now write a program that drives in a square, assuming that while turning at full power the robot takes 0.4 seconds to turn 90 degrees.

Now here comes the tricky part: write a program that drives the robot in a sine wave.  To be more clear, the robot follows an arbitrarily scaled version of the parametric equation `y = sin(t)`, `x = 0`.  This can be seen in the below gif, where the robot position is represented by the circle.  Write a program that makes the robot move in this manner.

![siny robot](http://i.giphy.com/sajxSgoRSfh60.gif)


### Gyroscope

Imagine you have a sensor that gives you your current rotational velocity.   Write a `while (true)` that turns a specific angle by getting rotational velocity in degrees/sec from a dummy function `float getGyro()`.  You can adjust your robot turning velocity with the dummy function `void turn(int power)`, power being an integer from -100 to 100 (0 being brake).

Now try using this sensor to keep track of robot orientation from 0-360, starting at an orientation of 0.

### Sensor Mapping

Imagine you have a constantly rotating distance sensor strapped to the top of your robot.  The sensor can read a distance value (like an ultrasonic sensor), in addition to the angle that it is currently at (0-360, clockwise where 0 is pointing forwards).  Your task is to form a 2d image of nearby obstacles using this sensor.  You are operating in a `while (true)` loop, and can call dummy functions `float getDistance()` and `float getAngle()`.  Over time build a 2D boolean array representing your image.

The previous paragraph assumes that the sensor reads in a direct line.  However, most real distance sensors have something called a "beam width."  For example, imagine you have an ultrasonic sensor with a pencil directly in front of it.  If you rotate it a little bit so that the sensor is not pointing directly at the pencil, it might still read a short distance as if the pencil weren't there.  Alternatively if the sensor were pointing directly at the pencil it might not see it at all.  Basically, the concept of a beam angle introduces error into the equation: the bane of a robotics programmer.  All sensor readings will have associated error, something we'll have to deal with extensively.  For now, define an arbitrary beam angle variable and try to compensate for it in your program.

If you're really insane, there's yet another degree of complexity we can add to this fun problem.  Currently you are mapping discrete points rather than lines.  If the robot is trapped in a circular room but has only taken 4 sensor readings, it only knows that there are 4 single-pixel obstacles around itself.   To compensate for this we must maintain yet another 2D image, where a predicted image is formed by connecting the dots on the first image.   Try different methods of isolating discrete obstacles, for example defining a threshold pixel distance where dots should or should not be connected.

### Kinematics and Control

Kiwi drive is a drivetrain with three omniwheels arranged at the edges of a robot in an equilateral triangle, as such:

![Kiwi drive diagram](http://i.stack.imgur.com/x6u31.png)

Write a function that maps a 3D joystick input of X velocity, Y veloctity, and rotational velocity scaled from -100 to 100 to three motor values scaled -100 to 100.   This question requires physics background, in particular vectors and torque.

If you were succesful, try it the other way around; from given motor inputs A, B, and C update the position (x,y,theta) of a simulated robot.
