# Reflection

Reflection is a powerful feature in Java that allows you to examine and modify the behavior of Java objects at runtime. It allows you to inspect the structure and behavior of classes, interfaces, and objects, and also to invoke methods, access fields, and create new instances of classes dynamically.

## What can be done

- Access a private field of a class
- Create objects dynamically at runtime
- Invoke a method dynamically at runtime
- Inspect the structure of a class and an object

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
#### _Explaination_
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
#### _Explaination_
In this example, we have a class MyClass with a constructor that takes a String parameter. Using reflection, we are able to create an instance of this class dynamically at runtime.

First, we obtain a reference to the Class object of MyClass using the Class.forName() method, passing the fully qualified name of the class as a string.

Next, we obtain a reference to the constructor of MyClass that takes a String parameter using the getConstructor() method of the Class object. We pass the Class object of String as the argument to this method to specify the type of the parameter.

Then, we use the newInstance() method of the Constructor class to create a new instance of MyClass, passing the String argument to the constructor. This method returns an Object reference to the new instance.

Finally, we cast the Object reference to MyClass and call the displayMessage() method on the new instance to display the message "Hello, World!".


### Ex 3: Invoke a method dynamically
```
import java.lang.reflect.Method;

public class MyClass {
    public void displayMessage(String message) {
        System.out.println("Message: " + message);
    }

    public static void main(String[] args) throws Exception {
        Class<?> clazz = Class.forName("MyClass");
        Object obj = clazz.newInstance();
        Method method = clazz.getMethod("displayMessage", String.class);
        method.invoke(obj, "Hello, World!"); // Output: Message: Hello, World!
    }
}

```
#### _Explaination_
In this example, we have a class MyClass with a method displayMessage() that takes a String parameter. Using reflection, we are able to invoke this method dynamically at runtime.

First, we obtain a reference to the Class object of MyClass using the Class.forName() method, passing the fully qualified name of the class as a string.

Next, we create a new instance of MyClass using the newInstance() method of the Class object, which returns an Object reference to the new instance.

Then, we obtain a reference to the displayMessage() method of MyClass using the getMethod() method of the Class object. We pass the name of the method as a string and the Class object of the String parameter as arguments to this method.

Finally, we invoke the method on the object instance using the invoke() method of the Method object, passing the object instance and the String argument to the method.

### Ex 4: Inspect the structure of a class and an object
```
import java.lang.reflect.Field;
import java.lang.reflect.Method;

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
        
        // Inspect fields of the class
        Field[] fields = clazz.getDeclaredFields();
        System.out.println("Fields of MyClass:");
        for (Field field : fields) {
            System.out.println(field.getName());
        }
        
        // Inspect methods of the class
        Method[] methods = clazz.getDeclaredMethods();
        System.out.println("Methods of MyClass:");
        for (Method method : methods) {
            System.out.println(method.getName());
        }
        
        // Inspect fields and values of an object
        MyClass myObj = new MyClass("Hello, World!");
        Field messageField = clazz.getDeclaredField("message");
        messageField.setAccessible(true);
        Object value = messageField.get(myObj);
        System.out.println("Value of message field in myObj: " + value);
    }
}
```
#### _Explaination_
In this example, we have a class MyClass with a field message and a method displayMessage(). Using reflection, we are able to inspect the structure of the class and an object of the class at runtime.

First, we obtain a reference to the Class object of MyClass using the Class.forName() method, passing the fully qualified name of the class as a string.

Next, we use the getDeclaredFields() method of the Class object to obtain an array of Field objects representing the fields of the class. We iterate over this array and print the names of the fields.

Then, we use the getDeclaredMethods() method of the Class object to obtain an array of Method objects representing the methods of the class. We iterate over this array and print the names of the methods.

Finally, we create an instance of MyClass and use the getDeclaredField() method of the Class object to obtain a Field object representing the message field of the class. We call the setAccessible() method of the Field object to make it accessible, and then use the get() method of the Field object to obtain the value of the message field in the object instance. We print the value of the field.
