#### Decorator Design Pattern

The decorator pattern is a structural design pattern that allows you to add new behavior to existing objects dynamically by wrapping them in a decorator class. The decorator class implements the same interface as the wrapped object and contains a reference to the wrapped object. When the client code calls a method on the decorator, the decorator passes the call to the wrapped object and may add some additional behavior before or after the call.

*Pros:*

- Allows you to add new behavior to existing objects dynamically, without changing the objects' code.
- Makes it easy to create different combinations of behavior, as you can decorate an object with multiple decorators.
- Decouples the client code from the objects that it uses, making it easier to change the objects without affecting the client code.

*Cons:*

- Increases the complexity of the code, as you need to create a decorator class for each type of behavior that you want to add.
- Can make the code more difficult to read and understand, as it involves multiple levels of indirection.

*When to use the decorator pattern:*

- When you want to add new behavior to existing objects dynamically, without changing their code.
- When you want to create flexible and reusable objects that can have different combinations of behavior.
- When you want to avoid creating a large number of subclasses to support every combination of behavior.

*Use Case:* 

Imagine that you are creating a software application for a coffee shop. The application allows the user to order coffee drinks and customize them with various toppings such as whipped cream, chocolate syrup, and sprinkles.

*Implementation:*

```csharp
public interface ICoffee
{
    string GetDescription();
    double GetCost();
}
```

Next, you can create a concrete class called Espresso that implements the ICoffee interface:

```csharp
public class Espresso : ICoffee
{
    public string GetDescription()
    {
        return "Espresso";
    }

    public double GetCost()
    {
        return 1.99;
    }
}
```

Then, you can create a decorator class called ToppingDecorator that implements the ICoffee interface and contains a reference to an ICoffee object:

```csharp
public abstract class ToppingDecorator : ICoffee
{
    protected ICoffee coffee;

    public ToppingDecorator(ICoffee coffee)
    {
        this.coffee = coffee;
    }

    public virtual string GetDescription()
    {
        return coffee.GetDescription();
    }

    public virtual double GetCost()
    {
        return coffee.GetCost();
    }
}
```

Next, you can create concrete decorator classes for each topping that you want to offer, such as WhippedCream and ChocolateSyrup:

```csharp
public class WhippedCream : ToppingDecorator
{
    public WhippedCream(ICoffee coffee) : base(coffee)
    {
    }

    public override string GetDescription()
    {
        return coffee.GetDescription() + ", Whipped Cream";
    }

    public override double GetCost()
    {
        return coffee.GetCost() + 0.50;
    }
}

public class ChocolateSyrup : ToppingDecorator
{
    public ChocolateSyrup(ICoffee coffee) : base(coffee)
    {
    }

    public override string GetDescription()
    {
        return coffee.GetDescription() + ", Chocolate Syrup";
    }

    public override double GetCost()
    {
        return coffee.GetCost() + 0.75;
    }
}
```

Finally, you can use the decorator classes to create and customize coffee drinks in your client code:

```csharp
ICoffee espresso = new Espresso();
Console.WriteLine(espresso.GetDescription() + ": $" + espresso.GetCost());
 
 // Add whipped cream and chocolate syrup to the espresso
 ICoffee espressoWithToppings = new WhippedCream(new ChocolateSyrup(espresso));
 console.WriteLine(espressoWithToppings.GetDescription() + ": $" + espressoWithToppings.GetCost());
```

This will output the following:

```csharp
Espresso: $1.99
Espresso, Chocolate Syrup, Whipped Cream: $3,24
```
