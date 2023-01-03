#### Bridge Design Pattern

The bridge pattern is a structural design pattern that separates an abstraction from its implementation, allowing the two to vary independently. The bridge uses encapsulation, aggregation, and inheritance to implement this separation. The abstraction is an interface that contains a reference to the implementation, and the implementation is a class that implements the interface.

*Pros:*

- Decouples the abstraction from the implementation, allowing the two to vary independently.
- Allows you to change the implementation of an abstraction without affecting the client code that uses the abstraction.
- Can improve the performance of the system, as you can create different implementations for different scenarios and choose the best one at runtime.

*Cons:*

- Increases the complexity of the code, as you need to create an interface and two separate class hierarchies (one for the abstraction and one for the implementation).
- Can make the code more difficult to read and understand, as it involves multiple levels of indirection.

*When to use the bridge pattern:*

- When you want to decouple an abstraction from its implementation, so that the two can vary independently.
- When you want to create a reusable class that can work with multiple implementations of an interface.
- When you want to hide the implementation of an abstraction behind a simple interface.

*Use Case:*

You are building a system to manage the inventory of a warehouse. The warehouse stores a variety of products, including food, electronics, and clothing. Each product has a name, a price, and an expiration date (for food items). You want to be able to search the inventory by these different attributes.

*Implementation:*

```csharp
// Abstract class for product
abstract class Product
{
    public abstract string GetName();
    public abstract double GetPrice();
    public abstract DateTime GetExpirationDate();
}

// Concrete implementations of Product class for different types of products
class FoodProduct : Product
{
    private string name;
    private double price;
    private DateTime expirationDate;

    public FoodProduct(string name, double price, DateTime expirationDate)
    {
        this.name = name;
        this.price = price;
        this.expirationDate = expirationDate;
    }

    public override string GetName()
    {
        return name;
    }

    public override double GetPrice()
    {
        return price;
    }

    public override DateTime GetExpirationDate()
    {
        return expirationDate;
    }
}

class ElectronicsProduct : Product
{
    private string name;
    private double price;

    public ElectronicsProduct(string name, double price)
    {
        this.name = name;
        this.price = price;
    }

    public override string GetName()
    {
        return name;
    }

    public override double GetPrice()
    {
        return price;
    }

    public override DateTime GetExpirationDate()
    {
        return DateTime.MaxValue; // Electronics products do not expire
    }
}

class ClothingProduct : Product
{
    private string name;
    private double price;

    public ClothingProduct(string name, double price)
    {
        this.name = name;
        this.price = price;
    }

    public override string GetName()
    {
        return name;
    }

    public override double GetPrice()
    {
        return price;
    }

    public override DateTime GetExpirationDate()
    {
        return DateTime.MaxValue; // Clothing products do not expire
    }
}

// Interface for search criteria
interface SearchCriteria
{
    bool Match(Product product);
}

// Concrete implementations of SearchCriteria interface for different types of search criteria
class NameSearchCriteria : SearchCriteria
{
    private string name;

    public NameSearchCriteria(string name)
    {
        this.name = name;
    }

    public bool Match(Product product)
    {
        return product.GetName() == name;
    }
}

class PriceSearchCriteria : SearchCriteria
{
    private double minPrice;
    private double maxPrice;

    public PriceSearchCriteria(double minPrice, double maxPrice)
    {
        this.minPrice = minPrice;
        this.maxPrice = maxPrice;
    }

    public bool Match(Product product)
    {
        double price = product.GetPrice();
        return price >= minPrice && price <= maxPrice;
    }
}

class ExpirationDateSearchCriteria : SearchCriteria
{
    private DateTime minDate;
    private DateTime maxDate;

    public ExpirationDateSearchCriteria(DateTime minDate, DateTime maxDate)
    {
        this.minDate = minDate;
        this.maxDate = maxDate;
    }
    
    public bool Match(Product product)
    {
        DateTime date = product.GetExpirationDate();
        return date >= minDate && date <= maxDate;
    }
}
```
