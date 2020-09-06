# Dart language notes

## Tutorial: 
* Online tutorial article: https://www.tutorialspoint.com/dart_programming/index.htm

## Notes:
* The Cascade operator (..): The cascade operator can be used as a shorthand in cases where there is a sequence of invocations.
```
class Student { 
   void test_method() { 
      print("This is a  test method"); 
   } 
   
   void test_method1() { 
      print("This is a  test method1"); 
   } 
}  
void main() { 
   new Student() 
   ..test_method() 
   ..test_method1(); 
}
```
