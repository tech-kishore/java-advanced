# Reflection

Reflection is a powerful feature in Java that allows you to examine and modify the behavior of Java objects at runtime. It allows you to inspect the structure and behavior of classes, interfaces, and objects, and also to invoke methods, access fields, and create new instances of classes dynamically.

## Examples of how to use reflection 

### Ex 1: Access a private field of a class
```
import java.lang.reflect.Field;

public class MyClass {
    private String myPrivateField = "Hello, World!";

    public static void main(String[] args) throws Exception {
        MyClass obj = new MyClass();
        Field field = MyClass.class.getDeclaredField("myPrivateField");
        field.setAccessible(true);
        String value = (String) field.get(obj);
        System.out.println(value); // Output: Hello, World!
    }
}
```
#### Explaination
In this example, we have a class MyClass with a private field myPrivateField. Using reflection, we are able to access and retrieve the value of this field, even though it is declared as private.

First, we obtain a reference to the field using the getDeclaredField() method of the Class class. This method returns a Field object that represents the specified field of the class. We pass the name of the field as a string to this method.

Next, we need to make the field accessible, since it is private. We do this by calling the setAccessible() method of the Field class and passing true as the argument.

Finally, we can retrieve the value of the field using the get() method of the Field class. We pass the object instance of MyClass as the argument to this method, since the field is an instance field and not a static field.


### Ex 2: Create objects dynamically
```
import java.lang.reflect.Constructor;

public class MyClass {
    private String message;

    public MyClass(String message) {
        this.message = message;
    }

    public void displayMessage() {
        System.out.println("Message: " + message);
    }

    public static void main(String[] args) throws Exception {
        Class<?> clazz = Class.forName("MyClass");
        Constructor<?> constructor = clazz.getConstructor(String.class);
        Object obj = constructor.newInstance("Hello, World!");
        MyClass myObj = (MyClass) obj;
        myObj.displayMessage(); // Output: Message: Hello, World!
    }
}
```
#### Explaination
In this example, we have a class MyClass with a constructor that takes a String parameter. Using reflection, we are able to create an instance of this class dynamically at runtime.

First, we obtain a reference to the Class object of MyClass using the Class.forName() method, passing the fully qualified name of the class as a string.

Next, we obtain a reference to the constructor of MyClass that takes a String parameter using the getConstructor() method of the Class object. We pass the Class object of String as the argument to this method to specify the type of the parameter.

Then, we use the newInstance() method of the Constructor class to create a new instance of MyClass, passing the String argument to the constructor. This method returns an Object reference to the new instance.

Finally, we cast the Object reference to MyClass and call the displayMessage() method on the new instance to display the message "Hello, World!".


