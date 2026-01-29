Default access modifier:


- Default is package private
- Acts like public if in the same package
- Acts like private to other packages

Public - everywhere
private - In class
protected - inheritance 

The Static keyword: 
    - When you need to define a class member as independent of any object  instance 
    - Can be accessed before any instances are created 
    - No instance assumption- example : no this, no non-static access
    - All instances of a class share the same static variable
    - Used by the method that starts every java program

The final modifier:  
       - Used to declare a variable as a constant
       - Affects the variable / reference only 
       - Object references can be final - but doesn't affect containing elements
       -Collections can be final - but doesn't affect containing elements 
       - Benefits - runtime optimization 
       - Benefits - Programming best practice