# Black and White Quad Trees

The goal is to convert black and white images to a corresponding quad tree representation.

If the entire square is a single color, then it's represented by a `0` followed by `0` if it's white, and `1` if it's black.
If the square is not uniform, it's represented by a `1` followed by four new squares, starting in the top left, then top right, bottom left, bottom right.

Alternative naming calls non-uniform square a `tree` and a uniform square a `leaf`.

#### Bonus:
Do the opposite: create an image from a binary representation.

### Input:
a single string that's the path to an image file.
    - image will aways be square
    - width will always be a power of 2
    - consequently, so will height
    - image will contain no colors other than black and white
#### bonus:
1. A binary representation of a quad tree.
2. The filename it should be saved to.

### Output:
A stream of 1 and 0 characters that represents the image.
#### bonus:
A file should be created with the input filename that is the image representing the input.

### Example:
```sh
> myprogram examples/example-1.bmp
00
> myprogram examples/example-5.bmp
1000010100000001
```
#### bonus:
```sh
> myprogram2 101000100 output.bmp
```
this should create a file named `output.bmp` that's 2 by 2 pixels big, where the left 2 pixels are black and the right 2 pixels are white.
# Pointers:

* Reading the commandline:
    * the path to the image will always be the first argument in the string args passed to your main method. For example:
    ```cs
    public static void Main(String[] argv)
	{
		Console.WriteLine(argv[0]);
	}
    ```
    will output whatever was passed in.
* Reading the image file
    * see [the microsoft api on bitmaps](https://docs.microsoft.com/en-us/dotnet/api/system.drawing.bitmap?view=dotnet-plat-ext-3.1)
* Mental representation:
    * The binary string `1001010001000000` can be represented as
    ```haskell
    1
        00
        1
            01
            00
            01
            00
        00
        00
    ```
    which makes it easy to see that it's 2 deep. meaning it represents a `2^2`x`2^2`=>`4`x`4` image.
    * So the final structure of this tree is `tree(leaf,tree(leaf,leaf,leaf,leaf),leaf,leaf)`
