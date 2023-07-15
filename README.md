# Encapsulation-oops-
*   The encapsulation is "wrapping data" OR "combining data" variable and method in class
*   The methods that work on data within one unit. 
*   This puts restrictions on accessing variables and methods directly and can prevent the accidental modification of data.
*   To PREVENT THE "ACCIDENTAL MODIFICATIN", an object’s variable can only be changed by an object’s method. 
*   Those types of variables are known as  "PRIVATE VARIABLES".
https://media.geeksforgeeks.org/wp-content/uploads/20230501154755/Encapsulation-in-Python.webp
*   methods and variable encapsulate the class.
  # Real time example
  *    Consider a real-life example of encapsulation, in a company, there are different sections like the accounts section, finance section, sales section etc. The finance section handles all the financial transactions and keeps records of all the data related to finance. Similarly, the sales section handles all the sales-related activities and keeps records of all the sales. Now there may arise a situation when due to some reason an official from the finance section needs all the data about sales in a particular month. In this case, he is not allowed to directly access the data of the sales section. He will first have to contact some other officer in the sales section and then request him to give the particular data. This is what encapsulation is. Here the data of the sales section and the employees that can manipulate them are wrapped under a single name “sales section”. Using encapsulation also hides the data. In this example, the data of the sections like sales, finance, or accounts are hidden from any other section.
    
# *  if i have money. i placed into outside my home is called "PUBLIC MEMBER"
                     If i placed into secret placed no one can know about the money is called "PRIVATE MEMBER"
                     If i placed into my house which is know only me and my family is called "PROTECTED MEMBER".
       PUBLIC MEMBER accessing data and method outside class
       PRIVATE MEMBER accessing data and method only within the class
       PROTECTED MEMBER accessing data and method within the class and also inheritance class we can access that data.
# school bag it will protect the books and  pens inside the bag.
# When you log into your email accounts such as Gmail, Yahoo Mail, or Rediff mail, there is a lot of internal processes taking place in the backend and you have no control over it.
# Calculator show the results of the equation but hide the mothod of the implementation.
# ink pen protect the ink.

Example for protected member
*  for protected member using single underscore "_"
*  the protected variable can be accessed out of the class as well as in the derived class (modified too in derived class), it is customary(convention not a rule) to not access the protected out the class body.
*  protected is accessing inside the class and also accessing the inheritance class.It cannot access outside the class.
  
class Base:
    def __init__(self):
  
        # Protected member
        self._a = 2
  
# Creating a derived class
class Derived(Base):
    def __init__(self):
  
        # Calling constructor of
        # Base class
        Base.__init__(self)
        print("Calling protected member of base class: ", 
              self._a)
  
        # Modify the protected variable:
        self._a = 3
        print("Calling modified protected member outside class: ",
              self._a)
  
  
obj1 = Derived()
  
obj2 = Base()
  
# Calling protected member
# Can be accessed but should not be done due to convention
print("Accessing protected member of obj1: ", obj1._a)
  
# Accessing the protected variable outside
print("Accessing protected member of obj2: ", obj2._a)

OUTPUT:
Calling protected member of base class:  2
Calling modified protected member outside class:  3
Accessing protected member of obj1:  3
Accessing protected member of obj2:  2

Example for private member
*   private should neither be accessed outside the class nor by any base class
*   Private instance variables that cannot be accessed except inside a class.
*   for private member using double underscore "__"
*   
eg:
   class Student:
    __schoolName = 'XYZ School' # private class attribute

    def __init__(self, name, age):
        self.__name=name  # private instance attribute
        self.__salary=age # private instance attribute
    def __display(self):  # private method
	    print('This is private method.')

std = Student("Bill", 25)
print(std.__schoolName) #AttributeError
print(std.__name)   #AttributeError
print(std.__display())  #AttributeError
