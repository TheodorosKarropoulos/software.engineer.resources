#### Builder Design Pattern

The builder pattern is a creational design pattern that allows you to construct complex objects step by step. The builder provides an interface for creating the parts of the object and an implementation of the builder that constructs the object using the provided parts. The client code creates the builder object, calls the build methods to create the parts, and then retrieves the object using a get method.

*Pros:* 

- Allows you to create complex objects step by step, hiding the construction process from the client code.
- Makes it easy to create different representations of the same object, as you can use different builders to create the object in different ways.
- Can improve the performance of the system, as you can reuse the same builder and build methods to create multiple objects.

*Cons:*

- Increases the complexity of the code, as you need to create a builder interface and a separate class for each type of object that you want to build.
- Can make the code more difficult to read and understand, as it involves multiple levels of indirection.

*When to use the builder pattern:*

- When you want to construct complex objects step by step.
- When you want to hide the construction process from the client code.
- When you want to create different representations of the same object.

*Use Case:*

Imagine you are building a meal ordering system for a fast food restaurant. Customers can choose from a variety of options to customize their meals, including the type of main dish (e.g. burger, chicken sandwich, salad), the type of side dish (e.g. fries, onion rings, side salad), and the type of drink (e.g. soda, water, lemonade).

To represent a meal, you can create a Meal class with fields for the main dish, side dish, and drink. You can then create a MealBuilder class with methods for setting each option, as well as a Build method that returns a Meal object. Here is how the Meal and MealBuilder classes might look:

*Implementation:*

```csharp
public class Meal
{
    public string MainDish { get; set; }
    public string SideDish { get; set; }
    public string Drink { get; set; }

    public override string ToString()
    {
        return $"Main dish: {MainDish}, Side dish: {SideDish}, Drink: {Drink}";
    }
}

public class MealBuilder
{
    private readonly Meal _meal = new Meal();

    public MealBuilder SetMainDish(string mainDish)
    {
        _meal.MainDish = mainDish;
        return this;
    }

    public MealBuilder SetSideDish(string sideDish)
    {
        _meal.SideDish = sideDish;
        return this;
    }

    public MealBuilder SetDrink(string drink)
    {
        _meal.Drink = drink;
        return this;
    }

    public Meal Build()
    {
        return _meal;
    }
}
```

To use the MealBuilder class, you can create an instance of it, set the options using the Set methods, and then call the Build method to get the Meal object. Here is an example:

```csharp
MealBuilder mealBuilder = new MealBuilder();
Meal meal = mealBuilder.SetMainDish("Burger").SetSideDish("Fries").SetDrink("Soda").Build();
Console.WriteLine(meal);
```

This will output the following:

```csharp
Main dish: Burger, Side dish: Fries, Drink: Soda
```

The MealBuilder class uses the Builder pattern to separate the construction of the Meal object from its representation. This makes it easy to create complex objects step by step, and allows you to use different builders to create different representations of the same object.
