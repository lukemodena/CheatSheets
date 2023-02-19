# Object-Oriented Programming

Method of structuring a program by bundling related properties and behaviours into individual objects.

-	Class: A blueprint used to construct objects, a Class can exist without its Objects, but Objects cannot exist without their class.
    -	_Superclass_: A more general class
    -	_Subclass_: A more specialized class
    -	`__name__`: Stores the name of module or class (string)
    -	`__module__`: Stores the name of the module which contains the class definition, 
        -	`print(class.__module__)` outputs `__main__` if defined on the file currently being run.
    -	`__bases__```: A tuple, contains superclass data, only direct superclasses are included (only classes have this attribute)
    -	`getattr(x, y)`: Takes the object (x), and its property name (y) as a string, returning the attribute’s value
    -	`setattr(x, y, z)`: Takes the object (x), and its property name (y) as a string, the property’s new value (z).
-	**Objects**: A being belonging to a class (an instance of a class), defining the requirements, traits, and qualities assigned to a specific class. Three groups of attributes:
    -	**Name** to allow it to be distinguished from other objects
    -	Set of individual **variables** – can be empty
    -	Set of **methods** (abilities to perform specific activities) – can be empty
    -	`Object = Class() or Class(x)`
    -	`type(object).__name__`: To find the name of the objects class use the `type()` function with `__name__` (can’t use `__name__` on its own).
    -	`__module__`: Stores the name of the module which contains the class definition, 
        -	`print(object.__module__)` outputs `__main__` if defined on the file currently being run.
    -	`__str__()`: Defining this method, allows you to edit the objects returned string.
    -	`isinstance(obj, class)`: Detect whether an object is of a certain class or not.
    -	`is` **operator**: Check whether two variables refer to the same object
-	**Constructor**: Part of class used to build new objects (cannot return a result)
    -	`__init__(self)`: Constructor, if class has constructor, it is invoked automatically and implicitly when an object is instantiated
    -	Can be used to set up the object
    -	Must have the `self` parameter
    -	Default Constructor: `__init__(self)`
    -	Parameterized Constructor: `__init__(self, f, s)`
-	**Hierarchy**: Hierarchy grows from top to bottom, like tree roots, not branches
    -	**Superclass**: Topmost class, no inheritance
    -	**Subclass**: Inherits from the superclass or another subclass
    -	`issubclass(ClassOne, ClassTwo)`: Function to check whether a class is a subclass of another class, returns _True/False_ 
-	**Inheritance**: The relationship between a superclass and its subclass (the objects that are inherited, throughout hierarchy). Enables the constructing of adaptable classes through extending a class’s capabilities.

    -	**Inheritance Method 1**:
        ```
        class Super:
          def __init__(self, name):
            self.name = name

        class Sub(Super):
          def __init__(self, name):
            Super.__init__(self, name)
        ```
    -	**Inheritance Method 2**:
        ```
        class Super:
          def __init__(self, name):
            self.name = name

        class Sub(Super):
          def __init__(self, name):
            super().__init__( name)
        ```
    - `AttributeError`: This exception is raised when python fails to access any object’s entity in the following order:
        1. Find inside the object itself
        2. Find in all classes in inheritance line (bottom to top)
        3. If there is more than one class on a particular inheritance path, Python scans them from left to right.
    -	**Multiple Inheritance**: Class has more than one superclass
        -	Always risky as presents more opportunity to make mistakes
        -	Makes overriding tricky, super() function becomes ambiguous
        -	Single inheritance always simpler, safer, and easier
        -	Violates single responsibility principle (class made of 2 or more classes that know nothing about eachother)
        -	Composition is a better alternative to multiple inheritance
    -	**Overriding**: The entity defined later overrides the same entity defined earlier (Python looks from bottom to top). The subclass object overrides the superclass object. If multiple inheritance the left object entity overrides the right object
-	**Composition**: Composing an object using other different (external) objects. Enables the constructing of adaptable classes through projecting a class as a container (running objects within objects derived from different classes)
-	**Encapsulation**: Allows certain class variables to be hidden from the outer world (name starting with a double underscore __) 
    -	**Mangled Name**: Used to access private variable from outside `class _ClassName__PrivatePropertyOrMethodName`
-	**Polymorphism**: The subclass ability to modify its superclass behaviour. Allowing you to differentiate between the behaviour of different objects extending class flexibility.
-	**Variables**: The pre-defined attributes/properties of a class or object.
-	**Instance Variables**: Attributes/properties within the same class possessing different sets of properties across different objects, known as instance variables, declared inside a class method
    -	`__dict__`: Predefined property, containing dictionary of all the properties carried by the object
    -	`hasattr(ObjectORClass, ‘attributeName’)`: Function to check if an object/class contains a specific property (attribute), returns _True_ or _False_
-	**Method**: Function embedded inside a class (at least one parameter – `self`)
    -	**Virtual**: A defined method is known as a virtual method
    -	**Abstract**: A method that is declared but contains no implementation. Abstract classes may not be instantiated, and abstract methods must be implemented by its subclasses
    -	`self`: Used to obtain access to the object's instance and class variables and invoke other object/class methods from inside the class.
-	**Instance Method**: Functions (method) within the same class possessing different sets of properties across different objects.
-	**Introspection**: Programs ability to **_examine_** the type or properties of an object at runtime
-	**Reflection**: Programs ability to **_manipulate_** the values, properties and/or functions of an object at runtime 
-	**LIFO/Stack**: An object developed to store data using two elementary operations _push_ and _pop_. Last In - First Out (LIFO) 
    -	**Procedural Approach**:
      ```
      stack = []

      def push(val):
        stack.append(val)
      
      def pop():
        val = stack[-1]
        del stack[-1]
        return val
      ```
    - **Object-Oriented Approach**:
      ```
      class Stack:
        def __init__(self):
            self.__stack_list = []

        def push(self, val):
          self.__stack_list.append(val)

        def pop(self):
          val = self.__stack_list[-1]
          del self.__stack_list[-1]
	        return val
       ```
- **Method Resolution Order (MRO)**:
    - INPUT:
        ```
        class Top:
            def m_top(self):
                 print("top")


        class Middle(Top):
            def m_middle(self):
                print("middle")


        class Bottom(Middle, Top):
            def m_bottom(self):
                print("bottom")


        object = Bottom()
        object.m_bottom()
        object.m_middle()
        object.m_top()
        ```
    - OUTPUT
        ```
        bottom
        middle
        top
        ```
    - INPUT:
        ```
        class Top:
            def m_top(self):
                 print("top")


        class Middle(Top):
            def m_middle(self):
                print("middle")


        class Bottom(Top, Middle):
            def m_bottom(self):
                print("bottom")


        object = Bottom()
        object.m_bottom()
        object.m_middle()
        object.m_top()
        ```
    - OUTPUT
        ```
        Traceback (most recent call last):
          File "main.py", line 11, in <module>
            class Bottom(Top, Middle):
        TypeError: Cannot create a consistent method resolution order (MRO) for bases Top, Middle
        ```
- **The diamond problem**:
    - INPUT:
        ```
        class Top:
            def m_top(self):
                print("top")


        class Middle_Left(Top):
            def m_middle(self):
                print("middle_left")


        class Middle_Right(Top):
            def m_middle(self):
                print("middle_right")


        class Bottom(Middle_Left, Middle_Right):
            def m_bottom(self):
                print("bottom")
                
        object = Bottom()
        object.m_bottom()
        object.m_middle()
        object.m_top()
        ```
    - OUTPUT
        ```
        bottom
        middle_left
        top
        ```

        

