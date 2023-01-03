#### Open Close Principle

*Definition:*

The Open/Closed Principle (OCP) is a software design principle that states that software entities (classes, modules, functions, etc.) should be open for extension but closed for modification. This means that you should be able to add new functionality to a class or module without changing its existing code.

*Code Example:*

```csharp
public class Shape
{
    public virtual double Area()
    {
        throw new NotImplementedException();
    }
}

public class Circle : Shape
{
    private readonly double radius;
    public Circle(double radius)
    {
        this.radius = radius;
    }

    public override double Area()
    {
        return Math.PI * radius * radius;
    }
}

public class Rectangle : Shape
{
    private readonly double width;
    private readonly double height;
    public Rectangle(double width, double height)
    {
        this.width = width;
        this.height = height;
    }

    public override double Area()
    {
        return width * height;
    }
}

public class ShapeCalculator
{
    public double CalculateTotalArea(IEnumerable<Shape> shapes)
    {
        double totalArea = 0;
        foreach (var shape in shapes)
        {
            totalArea += shape.Area();
        }
        return totalArea;
    }
}
```

In this example, the Shape class is designed to be open for extension but closed for modification. The Area() method is marked as virtual, which allows subclasses of Shape to override it and provide their own implementation. This means that you can add new shapes (such as a Triangle class) by creating a new subclass of Shape, without changing the Shape class itself. The ShapeCalculator class can then calculate the total area of any collection of shapes, without needing to know the specific details of each shape. This helps to ensure that the code is flexible and easy to modify without causing unintended side effects.
