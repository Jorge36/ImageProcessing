# ImageProcessing
Program to recolor the flowers of a image.

Several threads are created to recolor the image faster. Also there is an option to recolor the image with one thread. Then, in the program times are taken to compare both solutions. 

I create a thread by implementing the Runnable interface using lamda expression. While using the lambda expressions, we can skip the new Runnable() and run() method because the compiler knows that Thread object takes a Runnable object and that contains only one method run() that takes no argument.

```
Thread thread = new Thread(() -> {
  int xOrigin = 0 ;
  int yOrigin = height * threadMultiplier;

  recolorImage(originalImage, resultImage, xOrigin, yOrigin, width, height);
});

```
I use RGB (32/bit integer) to represent colors which each color component is allocated in 8 bits. The highest 8 bits are often used for the alpha channel (representing transparency), followed by red, green, and blue. The structure looks like this:

    Bits 24-31: Alpha (A)
    Bits 16-23: Red (R)
    Bits 8-15: Green (G)
    Bits 0-7: Blue (B)

&, |, << and >> are used to create RGB colors. 
1. & and | are bit-wise AND and OR operators
2. << and >> are the bit-wise left and right shift operators.

0x00FF0000 is the hexadecimal representation of red color, 0x0000FF00 is the hex of green and 0x000000FF the blue one.
They are used to get the red, greeen and blue colors of each RGB along with >> right shift operator. 

Then I have a function to check if a pixel is gray using the method abs from Math. 
Lastly, we use the class BufferedImage and WritableRaster to set the RGB of a single pixel.

* Image before processing:

![alt_text](https://github.com/Jorge36/ImageProcessing/blob/5c78107ddedcbe3cd10f820645cdcd0f00be916a/resources/many-flowers.jpg)

* Image after processing:

![alt_text](https://github.com/Jorge36/ImageProcessing/blob/5c78107ddedcbe3cd10f820645cdcd0f00be916a/out/many-flowers.jpg)



    
