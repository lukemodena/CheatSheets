# Modules & Packages

`Package: a` `Module: b` `Function: c()`

We want to invoke function ```c()```:

### Method 1:
```
import a.b

a.b.c()
```

### Method 2:
```
from a import b

b.c()
```

### Method 3:
```
from a.b import c

c()
```

### Method 4:
```
from a.b import *

c()
```

### Method 5:
```
from a.b import c() as func

func()
```

## Modules:

•	```dir```: Command showing the contents of a disk directory/folder

•	```dir()```: Show list of entities contained within an imported module

•	```math```

•	```random```

  -	```random()```: Float number within range (0.0, 1.0)
  -	```seed()```: Set random generators seed with current time
  -	```seed(int_value)```: Set random generators seed with integer value
  -	```randrange()```: Random integer from range (end), (beg, end), (beg, end, step)
  -	```randint(l, r)```: Generates random integer from left to right, no right exclusion
  -	```choice(sequence)```: Generates random value from input sequence
  -	```sample(seq, noEle)```: Generates set no. of random values from input sequence
  -	
•	```platform```

  -	```platform()```: Returns string describing the underlying platform’s data (hardware, operating system and interpreter version information)
  -	```uname()```: Returns object containing information about operating system
  -	```machine()```: Returns string of generic name of processor running your OS with Python
  -	```processor()```: Returns string with the real processor name
  -	```system()```: Returns the generic OS name as a string
  -	```version()```: Returns the OS version as a string
  -	```python_implementation()```: Returns the Python implementation as a string (CPython)
  -	```python_version_tuple()```: Returns a 3-element tuple containing the Python Version: major part, minor part, patch level number

•	```os```

  -	```uname()```: Returns object containing information about operating system
  -	```name()```: Allows you to quickly distinguish the operating system
    -	Unix: **posix**
    -	Windows: **nt**
    -	Jython: **java**
  -	```mkdir()```: Create a directory (allows for recursive on Windows)
  -	```makedirs()```: Allows for recursive directory creation ("1st_directory/2nd_directory")
  -	```rmdir()```: Delete a single directory
  -	```removedirs()```: Remove a directory and its subdirectories
  -	```listdir()```: Returns list of file and directory names in the path passed as its argument
  -	```chdir()```: Changes the current working directory to the specified path
  -	```getcwd()```: Returns information about the current working directory
  -	```system()```: Executes a command (seen above) passed to it as a string
  -	```strerror()```: simplifies error handling code
  
•	```path```: List of strings that specifies all directories scanned to find the specific modules

•	```sys```: Contains facilities allowing diagnosis of certain features of the OS environment

  -	Allows the program to access the 3 pre-opened streams
    -	```stdin```: Standard input (keyboard), input() function reads data by default
    -	```stdout```: Standard output (screen), print() function outputs stream data
    -	```stderr```: Standard error output (screen)

•	```datetime```

  -	```date```
    -	```date()```: YEAR, MONTH, DAY
    -	```today()```:
    -	```fromtimestamp()```:
    -	```fromisoformat()```:
    -	```replace()```:
    -	```weekday()```:
    -	```isoweekday()```:
    -	```isodayweek()```:
    -	```time()```:
  -	```datetime```
    -	```today()```:
    -	```now()```:
    -	```utcnow()```:
    -	```timestamp()```:
    -	```strftime()```:
      -	%Y
      -	%m
      -	%d
    -	```timedelta()```
   
•	```time```

  -	```time()```:
  -	```sleep()```:
  -	```ctime()```:
  -	```gmtime()```:
  -	```localtime()```
  -	```asctime()```:
  -	```mktime()```:
  -	```strftime()```:
  
•	```calendar```

  -	```calendar()```
  -	```prcal()```
  -	```month()```
  -	```setfirstweekday()```
  -	```prmonth()```
  -	```weekday()```
  -	```weekheader()```
  -	```isleap()```
  -	```leapdays()```
  -	```Calendar```
    -	```Parameter```: firstweekday
    -	```Method```: iterweekdays
    -	```Itermonthdates()```
    -	```monthdays2calendar()```
  -	```TextCalendar```
    -	```LocalTextCalendar```
  -	```HTMLCalendar```
    -	```LocalHTMLCalendar```
