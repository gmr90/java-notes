Inheritance: 

A class can extends one class in java. multiple inheritance is not possible due to diamond problem

class A {
}

class B extends A {
}


Abstract class: 

Defining a super class without intending to create instances 

    abstract class Animal {
        // implementation common to all animals
    }
    
    abstract class pet extends Animal {
        // implementation common to all pets 
    }
    class Rabbit extends Animal{
    
    // Additional implementation 
    
    }
    
Abstract Methods: 

    abstract class Animal {
       //define the contract of method 
       abstrat public void move();
    } 
    abstract class pet extends Animal {
        // Can choose to implement move() 
    }
    
    class Rabbit extends Pet {
        // Must implement move 
        public void move() {
        }
    } 

Abstract Keyword: 
    - Can be applied to classes that you don't want instantiated 
    - Can be a hierarchy of abstract classes 
    - Abstract methods indicate the method signature without implementation 
    - Anything abstract cannot be instantiated 
    - A non-abstract class extending an abstract class must implement all abstract memebers 

   
final Keyword with inheritance 

  Prevent inheritance 
  
    final class A {
    }
    
    class B extends A { -- Cannot inherit from final 'A'
    }

Prevent method overrides  

    class Rabbit extends Pet {
        final public void move() {
        }
    } 

Interfaces: Defines a class'interace separate from implementation 
 - external contract.
 
        public interface Car{
            public void drive();
            public void refuel (Fuel f)
         }
         
         class SportCar implements Car {
            @Override
            public void drive() {
            }
            @Override
            public void refuel(Fuel f) {
            }
         }
 
- Implementing multiple interfaces. 

        public interface Drivable {
            public void drive();
        }
        
        public interface FuelVehicle {
            public void refule(Fuel F);
        }
       
        class SportCar implements FuleVehicle {
            @Override
            public void drive(){
            }
            
            @Override
             public void refule(Fuel F) {
             }
        }

Interfaces Vs Abstract classes 

Define a contract  | Template or Starting point for classes      


Interface Default methods:

        public interface Drivable {
            public void drive(){
                System.out.println("Driving");
            }
        }
        public interface FuelVehicle extends Drivable {
            public void refule(Fuel F);
        }
    - We can override default methods from interface.
    
Polymorphism: Many Forms


    public class Animal {
        public int age;
        public String species; 
        public void move(){
            System.out.println ("Animal moving");
        }
    }
    
    
    public class Bird extends Animal {
        public void move(){
            System.out.println ("Bird Flying");
        }
    }
    
    public class Fish extends Animal {
     
        public void move(){
            System.out.println ("Fish Swimming");
        }
    }
    
    public void moveAnimal(Animal animal){
        animal.move();
    }
    Fish fish = new Fish();
    movieAnimal(fish);
    
    ** SuperClass reference = subclassInstance;
    
    Animal fish = new Fish();
    fish.move();// move should have the method in super class, only super class methods
    
  Polymorphism with interfaces too. 
  
  Casting with Object references:     
          public interface Drivable {
                public ovid drive();
           }
           public interface FuelVehicle {
                 public void refuel (Fuel f);
           }    
   
       Drivable car = new SportCar();
       car.drive();
       FuelVehicle vehicle = (FuelVehicle)car;
       vehicle.refuel(new Fuel());
 
 Is-a relationship:
 
    Subclass is-a Super class 
  
 The Object class: 
    Inheritance hierarchy
    Object class   <-A <- B <- C
    
    
    - toString
        public class car {
        
        }
        
        Car car = new Car();
        System.out.println(car);  --> Car@774876287

                public class car {
                
                 @Override
                 public String toString() {
                    return("this is a car")
                 }
                }
        
        Car car = new Car();
        System.out.println(car);  --> This is a car

        
 Equals Method: 
   myNewCar == neighborCar --> false ; it only compare the references not the actual content
   
                   public class car {
                        private int seats;
                        private string make;
                        @Override
                        public boolean equals(Object o ) {
                           // check to see if the paramerter o has the same values
                        }
                   }
   
    +