# Files

A file (object) comes from one of the following classes shown here:

-	```IOBase```
    -	```RawIOBase```
    -	```BufferedIOBase```
    -	```TextIOBase```
-	```open()```: Obtain file (object)

    ```
    stream = open(file, mode = 'r', encoding = None)
    ```
    -	file: Name of file
    -	mode: Open mode
    -	encoding: Encoding type (UTF-8 with text files)

-	```close()```: Get rid of file (object)

-	```read()```: Read whole file to memory (reading a terabyte-long file using this may corrupt OS)

-	```readline()```: Read a complete line of text from the file (treats file content as set of lines)

-	```write()```: Write text file (writing a file opened in read mode won't succeed)

-	```readlines()```: Read all the file contents, returning list of strings, one element per file line

-	```readinto()```: Allow reading from a binary file

-	```bytearray()```: Fills array with zeros

-	```hex()```: Converts elements to hexadecimal values

-	Opening stream modes:

     -	```r```: read
     -	```w```: write
     -	```a```: append
     -	```r+```: read and update
     -	```w+```: write and update
     -	```x```: open file for its exclusive creation
     -	Text:
        -	```rt```, ```wt```, ```at```, ```r+t```, ```w+t```
     -	Binary:
        -	```rb```, ```wb```, ```ab```, ```r+b```, ```w+b```
