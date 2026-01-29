Exception Handling: 
   - Protect the code that can throw an exception 
   - Specify what needs to happen on exception
   - Specify what needs to happen no matter what 
   - Throw the exception when something wrong happens
 
          try-catch

          try{
            //risky code
          } catch(Exception e){
          } finally {
            // Wrap up / clean up
          }
       
   - finally is option
   - can you have multiple catch blocks

                 try{
                   //risky code
                 } catch(ExceptionClass1 e1){
                 
                 }
                 catch(ExceptionClass e2){
                 }                   
                  catch(Exception e){
                 } finally {
                   // Wrap up / clean up
                 }
 
                        Exception 
                          |
                     Child Exception Classes 
                          
          Nested Try-catch blocks
          
                           try{
                             //risky code
                              try{
                              } catch(Exception e){
                                // handle exception for the inner try
                              }
                           } catch(ExceptionClass1 e1){
                           }
                           catch(ExceptionClass e2){
                           }                   
                           catch(Exception e){
                           } finally {
                             // Wrap up / clean up
                           }
                           
                           
   throw: 
    throw new ArthmeticException("You passed zero for a denominator!");
    
   Exceptions and call stack: 
   
    try {
        method();
    } catch(Exception e){
    }
     method: 
      try{
      } 
      catch(){
      }
      
   -- Uncaught Exception can lead to end of the program
   
    public class App{
        public static void main(String args[]){
            int i= 4/0;
        }
    }
    
   --Exception Types 

            
    --                                    Throwable <- root of all exceptions 
                                          /       \  
                                   Exception       Error
                                      /
                                RuntimeException (unchecked exception)          
                                
    Runtime exception are unchecked exceptions 
    
    
 --Custom Runtime Exception 
        
        public class CustomRuntimeException extends RuntimeException {
        
        }
        
        public void run (){
            throw new CustomRuntimeException();
        }
 
 if you want to caught then need to extend from Exception 
    
  Custom Exception: 
      
      public class CustomException extends Exception {

      }  
      
      public void run (){
        throw new CustomException(); --unhandled exception: CustomException
      }
      you have to surrounded with try-catch 
      
      try {  - checked exception
        throw new CustomException();
      } catch (Exception e){
            // handle exception
      }
      
      
      public void myAwesomeMethod(InputArgs inputObj) throws CustomException{
        if (inputObj.isInvalid())
            throw new CustomException();
      }
      -- whoever calling myAwesomeMethod should have try catch
      
      -- only applies for checked exceptions
      try{
        myAwesomeMethod();
      } catch(CustomException e){
        // handle the exception 
      }
      
  --Custom Exception constructors 
  
              public class CustomException extends Exception {
                public CustomException(String message){
                        super(message);
                }
                public CustomException(Throwable cause){
                    super(cause);
                }
              }  
