# Exceptions
### Keywords
- `try`: Defined before risky code
- `assert expression`: Evaluates expression
- `except ExceptionName`: Runs if defined exception is raised
- `raise ExceptionName`: Raise defined exception
- `except`: Runs if exception is raised, always at the end

Python 3 defines 63 built-in exceptions, forming a tree shaped hierarchy. The arrows in the hierarchy always point towards the more general exceptions. Examples of some exceptions are:

-	**BaseException**: Most general type of exception

	  -	**SystemExit**: Raised by sys.exit() function when program behaves undesirably
	  -	**GeneratorExit**: Raised when a generator or coroutine is closed
	  -	**KeyboardInterrupt**: Raised when user hits the interrupt key
	  -	**Exception**: All built in non-system exiting exceptions
	    -	**AttributeError**: Invalid attribute reference
	    -	**AssertionError**: Failed to assert instruction
	    -	**ArithmeticError**: **Mathematical** evaluation error
			-	**ZeroDivisionError**: Divided by zero
			-	**OverflowError**: Operation result is too large to be stored
	    -	**EOFError**: input() function hits end-of-file, without reading any data
	    -	**NameError**: Local or global name not found
	    -	**LookupError**: Improper use of data aggregates
			-	**IndexError**: Non-existent sequence element, e.g. if list is empty
			-	**KeyError**: Non-sequential dictionaries, e.g. if dictionary is empty
	    - **OSError**: System related error

			-	**FileNotFoundError**: Open non-existent file using “r” mode ENOENT

			-	**InterruptedError**: System call interrupted by incoming signal EINTR

			-	**PermissionError**: Insufficient access rights EACCES or EPERM

			-	**TimeOutError**: System function timed out system level ETIMEDOUT

	    -	**TypeError**: Misused argument types
	    -	**ValueError**: Recieves argument with right type, but inappropriate value
	    -	**ImportError**: Invalid import directive 
			-	**ModuleNotFoundError**: module cannot be located
       
    It is possible to define bespoke errors/exceptions and any of the built-in or user-defined exceptions can be raised manually using the raise instruction

**INPUT**:
```
	try:
		y = 1 / 0
	except ArithmeticError:
		print(“Arithmetic problem!”)
	except ZeroDivisionError:
		print(“Zero Division!”)

print(“THE END.”)
```
**OUTPUT**:
```
Arithmetic problem!
THE END.
```
and...

**INPUT**:
```
	try:
		y = 1 / 0
	except ZeroDivisionError:
		print(“Zero Division!”)
	except ArithmeticError:
		print(“Arithmetic problem!”)

print(“THE END.”)
```
**OUTPUT**:
```
Zero Division!
THE END.
```
