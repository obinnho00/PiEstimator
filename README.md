# PiEstimator
This is a Java program that estimates the value of pi using the Monte Carlo method and multithreading.
How it works

Dependencies
The program uses the ThreadLocalRandom class from the java.util.concurrent package. No additional dependencies are required.

The program first gets the number of available processors on the machine using Runtime.getRuntime().availableProcessors(). This value is then used to determine the number of threads that will be created.


The number of random points to be generated is set to 100000000, which is the default value.

pointsPerThread is calculated by dividing the total number of points by the number of threads.

An array of threads is created and initialized with a loop that creates a new thread for each element. The thread runs a code block that generates random (x, y) coordinates within the bounds of a square with a circle inscribed within it. If a point falls within the circle (i.e., if the distance between the point and the origin is less than or equal to the radius of the circle), then the localCount variable is incremented.

The localCount variable is synchronized using synchronized(PiEstimator.class) before it is added to the count variable.

The threads are then started using threads[i].start().

After all threads have completed their work, the program calculates the value of pi using the formula pi = 4.0 * count / numPoints.

Finally, the estimated value of pi is printed to the console using System.out.println("Estimated value of pi: " + pi);.

How to run the program
Copy the code to a file called PiEstimator.java.

Compile the code using javac PiEstimator.java.

Run the program using java PiEstimator.

