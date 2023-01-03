#### Liskov Substitution Principle

*Definition:*

The Liskov Substitution Principle (LSP) is a software design principle that states that subtypes must be substitutable for their base types. This means that if a class is a subtype of another class, it should be able to be used in the same way as the base class without causing any issues.

*Code Example:*

```csharp
public class Rectangle
{
    public virtual double Width { get; set; }
    public virtual double Height { get; set; }

    public double Area()
    {
        return Width * Height;
    }
}

public class Square : Rectangle
{
    public override double Width
    {
        get => base.Width;
        set
        {
            base.Width = value;
            base.Height = value;
        }
    }

    public override double Height
    {
        get => base.Height;
        set
        {
            base.Width = value;
            base.Height = value;
        }
    }
}

public class ShapeCalculator
{
    public double CalculateTotalArea(IEnumerable<Rectangle> rectangles)
    {
        double totalArea = 0;
        foreach (var rectangle in rectangles)
        {
            totalArea += rectangle.Area();
        }
        return totalArea;
    }
}
```

In this example, the Rectangle class represents a standard rectangle, with separate Width and Height properties. The Square class is a subclass of Rectangle, and it overrides the Width and Height properties to ensure that they are always equal (since a square has equal sides). The ShapeCalculator class calculates the total area of a collection of rectangles, without knowing or caring whether they are squares or standard rectangles. This demonstrates the Liskov Substitution Principle, since the Square class can be used in the same way as the Rectangle class without causing any issues.
