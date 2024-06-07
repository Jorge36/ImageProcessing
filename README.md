# ImageProcessing
Program to recolor the flowers of a image.

Several threads are created to recolor the image faster. Also there is an option to recolor the image with one thread. Then, In the program times are taken to compare both solutions. 

I create a thread by implementing the Runnable interface using lamda expression. While using the lambda expressions, we can skip the new Runnable() and run() method because the compiler knows that Thread object takes a Runnable object and that contains only one method run() that takes no argument.

```
Thread thread = new Thread(() -> {
  int xOrigin = 0 ;
  int yOrigin = height * threadMultiplier;

  recolorImage(originalImage, resultImage, xOrigin, yOrigin, width, height);
});

```
