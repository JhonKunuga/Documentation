Task 1 (5 points): Variables, Operators, and Conditionals

Create a C# program that does the following:

Declare and initialize an integer variable named "myAge" with your age.

Declare and initialize a double variable named "bankBalance" with a random value (e.g., 1500.75).

Implement a conditional statement (if-else) that checks whether your bank balance is greater than or equal to 1000. If it is, print "I have a healthy bank balance!" Otherwise, print "I need to save more."

Task 2 (5 points): Classes, Inheritance, and Properties

Create a C# class hierarchy for geometric shapes: "Shape," "Rectangle," and "Circle."

The "Shape" class should have a protected double field "area."

The "Rectangle" class should inherit from "Shape" and have prßivate fields for "length" and "width."

Implement properties for "Length" and "Width" with get and set accessors in the "Rectangle" class.

Calculate and set the area of a rectangle when an object is created.

The "Circle" class should inherit from "Shape" and have a private field for "radius." Implement properties for "Radius" with get and set accessors in the "Circle" class.

Calculate and set the area of a circle when an object is created.

Create instances of "Rectangle" and "Circle," set their dimensions, and display their areas.

Task 3 (5 points): Methods, Encapsulation, and Access Modifiers

Create a C# class named "Person" with the following members:

A private integer field for "age."

A public property for "Name" with get and set accessors.

A constructor that takes two parameters to initialize the age and name.

Implement a public method called "PrintDetails" that prints the person's name and age to the console. Create an instance of the "Person" class, set its name and age, and call the "PrintDetails" method to display the information.
==================================================================
Task 1 ( peints): Generics and Data Handling

Create a C# class named "DataHandler<T> that simulates a data handler using generics. It should include the following methods:

Awethod "AddData" that adds an element of type T to the data handler.

sethod "RetrieveData" that retrieves and returns an element from the data handler at a specific index.

Create an instance of "Datalandler" for integers and add some data to the handler. Use the "RetrieveData" method to retrieve and print data from the handler based on given indices.

Task 2 (5 points): Interfaces and Devices

Create an interface called "Device" with a method "Activate()" that represents activating a device. Then, create a class "DeviceController" that implements the "IDevice" interface. The "DeviceController" class should have a field for the device type (e.g., "TV," "Phone") and should implement the "Activate()" method to display a message like "The [DeviceType] is now active."

Create an instance of the "DeviceController" class for a device with a specific type and call the "Activate()" method to display the activation message

Task 3 (5 points): Abstract Classes and Vehicles

Create an abstract class called "Vehicle with the following members:

Alistract method "Start Engine()" with no implementation. An abstract method "Accelerate()" with no implementation.

Create a derived class "Car" that inherits from "Vehicle." In the "Car" class, implement the "StartEngine()" method to display "Car engine started" and Leplement the "Accelerate() method to display "Car is accelerating.

Create a derived class "Bike" that also inherits from "Vehicle." In the "Bike" class, implement the "StartEngine()" method to display "Bike engine started and implement the "Accelerate()" method to display "Bike is pedaling."

Create instances of both the "Car" and "Bike" classes. Call their "StartEngine()" and "Accelerate() methods to display the appropriate messages.



using System;
using System.Collections.Generic;

// Task 1: Custom Data Repository
public class CustomDataRepository<T>
{
    private List<T> elements = new List<T>();

    public void InsertElement(T element)
    {
        elements.Add(element);
    }

    public T FetchElement(int index)
    {
        if (index < 0 || index >= elements.Count)
        {
            throw new ArgumentOutOfRangeException("The specified index is invalid.");
        }
        return elements[index];
    }
}

// Task 2: Device Activation Interface
public interface IActivatable
{
    void PowerOn();
}

public class DeviceActivator : IActivatable
{
    private string deviceName;

    public DeviceActivator(string name)
    {
        this.deviceName = name;
    }

    public void PowerOn()
    {
        Console.WriteLine($"Powering on the {deviceName}.");
    }
}

// Task 3: Abstract Class for Vehicles
public abstract class VehicleBase
{
    public abstract void Ignite();
    public abstract void Drive();
}

public class Coupe : VehicleBase
{
    public override void Ignite()
    {
        Console.WriteLine("Coupe engine is running.");
    }

    public override void Drive()
    {
        Console.WriteLine("Coupe is cruising.");
    }
}

public class Tricycle : VehicleBase
{
    public override void Ignite()
    {
        Console.WriteLine("Tricycle is ready to roll.");
    }

    public override void Drive()
    {
        Console.WriteLine("Tricycle is pedaling along.");
    }
}

class MainApp
{
    static void Main()
    {
        // Task 1: Using CustomDataRepository for integers
        var intRepository = new CustomDataRepository<int>();
        intRepository.InsertElement(7);
        intRepository.InsertElement(14);
        intRepository.InsertElement(21);

        Console.WriteLine("Stored elements in CustomDataRepository:");
        for (int idx = 0; idx < 3; idx++)
        {
            Console.WriteLine(intRepository.FetchElement(idx));
        }

        // Task 2: Using DeviceActivator
        var smartTv = new DeviceActivator("Smart TV");
        smartTv.PowerOn();

        // Task 3: Using vehicle classes
        VehicleBase myCoupe = new Coupe();
        myCoupe.Ignite();
        myCoupe.Drive();

        VehicleBase myTricycle = new Tricycle();
        myTricycle.Ignite();
        myTricycle.Drive();
    }
}
