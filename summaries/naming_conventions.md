# C++ Naming Conventions

File Names:

Variable Names:

Class Names:

Function Names



**Classes**	- PascalCase	
First letter of each word capitalized 
```
MyClass
BankAccount()
```

**Common Variables** - Lowercase with underscores (snake_case)	
```
customer_name
total_amount
```
**Struct Data Members** - same as for common variables

**Class Data Members** - similar to common variable =s with a trailing underscore
```
customer_name_
value1_
total_amount_
```
**Member functions** - CamelCase (First letter lowercase, subsequent words start with uppercase)
```
calculateArea()
getCustomerDetails()
```

**Constants**


ALL_CAPS_WITH_UNDERSCORES	All uppercase separated by underscores (e.g., PI, MAX_VALUE)
Enums	PascalCase for enum itself, UPPERCASE_WITH_UNDERSCORES for enum values	Similar to classes, uppercase for individual values (e.g., Color, Color::RED, Color::GREEN)
Preprocessor macros	ALL_CAPS	All uppercase (e.g., DEBUG_MODE, STD_OUT)


## Reserved Keywords in C++

The following keywords have special meanings and **CANNOT** be use for variable names, function names or other identifiers.


**asm**: To declare that a block of code is to be passed to the assembler.

**auto**: A storage class specifier that is used to define objects in a block.

**break**: Terminates a switch statement or a loop.

**case**: Used specifically within a switch statement to specify a match for the statement’s expression.

**catch**: Specifies actions taken when an exception occurs.

**char**: Fundamental data type that defines character objects.

**class**: To declare a user-defined type that encapsulates data members and operations or member functions.

**const**: To define objects whose value will not alter throughout the lifetime of program execution.

**continue**:- Transfers control to the start of a loop.

**default**:- Handles expression values in a switch statement that are not handled by case.

**delete**: Memory deallocation operator.

**do**: indicate the start of a do-while statement in which the sub-statement is executed repeatedly until the value of the expression is logical-false.

**double**:  Fundamental data type used to define a floating-point number.

**else**: Used specifically in an if-else statement.

**enum**: To declare a user-defined enumeration data type.

**extern**: An identifier specified as an extern has an external linkage to the block.

**float**:- Fundamental data type used to define a floating-point number.

**for**: Indicates the start of a statement to achieve repetitive control.

**friend**: A class or operation whose implementation can access the private data members of a class.

**goto**: Transfer control to a specified label.

**if**: Indicate the start of an if statement to achieve selective control.

**inline**: A function specifier that indicates to the compiler that inline substitution of the function body is to be preferred to the usual function call implementation.

**int**: Fundamental data type used to define integer objects.

**long**: A data type modifier that defines a 32-bit int or an extended double.

**new**: Memory allocation operator.

**operator**: Overloads a c++ operator with a new declaration.

**private**: Declares class members which are not visible outside the class.

**protected**: Declares class members which are private except to derived classes

**public**: Declares class members who are visible outside the class.

**register**: A storage class specifier that is an auto specifier, but which also indicates to the compiler that an object will be frequently used and should therefore be kept in a register.

**return**: Returns an object to a function’s caller.

**short**: A data type modifier that defines a 16-bit int number.

**signed**: A data type modifier that indicates an object’s sign is to be stored in the high-order bit.

**sizeof**: Returns the size of an object in bytes.

**static**: The lifetime of an object-defined static exists throughout the lifetime of program execution.

**struct**: To declare new types that encapsulate both data and member functions.

**switch**: This keyword is used in the “Switch statement”.

**template**: parameterized or generic type.

**this**:  A class pointer points to an object or instance of the class.

**throw**: Generate an exception.

**try**: Indicates the start of a block of exception handlers.

**typedef**: Synonym for another integral or user-defined type.

**union**: Similar to a structure, struct, in that it can hold different types of data, but a union can hold only one of its members at a given time.

**unsigned**: A data type modifier that indicates the high-order bit is to be used for an object.

**virtual**: A function specifier that declares a member function of a class that will be redefined by a derived class.

**void**: Absent of a type or function parameter list.

**volatile**: Define an object which may vary in value in a way that is undetectable to the compiler.

**while**: Start of a while statement and end of a do-while statement.


Strings
