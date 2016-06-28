# Parser
Designed a recursive descent parser from scratch by using the given project specifications. Parser was designed to recognize user input and build data structures during runtime, then the data structures were to be executed in order upon end of input. Parser was required to read input formatted as C++ code and build data structures based on various variable declarations. Parser was then required to build custom data structures to store scoping information and have the data structure behave similar to a traditional compiler would in regards to static scoping. The parser would read various scopes even nested scopes and check for variable declarations. Then if a user entered a variable name by itself within a scope, the parser would trace the custom graphed data structure and locate if the variable exists in an accessible outer scope and print its value. If the variable was listed as a private variable or if it is outside of a nested scope's end brace there will be no results. Overall the project goal was to create a program that stores scope variables and evaluates static scoping principles similar to any traditional compiler.

#Example

**Input**
```
a, b, c;
test
  {
    public:
      a,b,helo;
    private:
      x,y;
      
    a = b;
    hello = c;
     y = r;
     nested
     {
      public:
        b;
        
      a=b
      x=hello;
      c=y;
    }
  }
 ```
 **Output**
```
test.a = test.b
test.hello = ::c
test.y = ?.r
test.a = nested.b
?.x = test.hello
::c = ?.y
 ```
 **The '?' symbol represents a variable which could not be found, while '::' represents global variable scope for the given variable.**
