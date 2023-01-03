#### Adapter Design Pattern

The adapter pattern is a structural design pattern that allows you to convert the interface of a class into another interface that the client expects. The adapter wraps an instance of the adaptee class and implements the target interface by delegating calls to the adaptee. This allows the client to use the adaptee class through the adapter's target interface.

*Pros:*

- Allows you to reuse classes that have incompatible interfaces by adapting their interfaces to a compatible interface.
- Decouples the client from the adaptee class, making it easier to change the adaptee without affecting the client.

*Cons:*

- Increases the complexity of the code, as you need to create an adapter class for each class that you want to adapt.
- Can make it more difficult to understand the code, as it involves multiple levels of indirection.

*When to use the adapter pattern:*

- When you want to reuse an existing class that has an incompatible interface.
- When you want to create a reusable class that cooperates with classes that have incompatible interfaces.
- When you want to hide the complexity of adapting an adaptee class behind a simple interface.

*Use Case:*

You are building a system that allows users to search for products on various e-commerce websites. The system should return a list of products that match the search criteria, along with their prices and availability. However, each e-commerce website has a different API for retrieving product information, and the format of the data returned by the APIs is also different. To allow the system to work with any e-commerce website, you decide to use the adapter pattern.

*Implementation:*

```csharp
public interface IProduct
{
    string Name { get; set; }
    decimal Price { get; set; }
    bool InStock { get; set; }
}

public class EcommerceWebsite1
{
    public List<Product1> Search(string searchTerm)
    {
        // Search products on website 1 and return results
    }
}

public class Product1
{
    public string Title { get; set; }
    public decimal Cost { get; set; }
    public bool Available { get; set; }
}

public class EcommerceWebsite2
{
    public List<Product2> Search(string searchTerm)
    {
        // Search products on website 2 and return results
    }
}

public class Product2
{
    public string Name { get; set; }
    public decimal Price { get; set; }
    public bool InStock { get; set; }
}

public class ProductAdapter1 : IProduct
{
    private Product1 _product;

    public ProductAdapter1(Product1 product)
    {
        _product = product;
    }

    public string Name
    {
        get => _product.Title;
        set => _product.Title = value;
    }

    public decimal Price
    {
        get => _product.Cost;
        set => _product.Cost = value;
    }

    public bool InStock
    {
        get => _product.Available;
        set => _product.Available = value;
    }
}

public class ProductAdapter2 : IProduct
{
    private Product2 _product;

    public ProductAdapter2(Product2 product)
    {
        _product = product;
    }

    public string Name
    {
        get => _product.Name;
        set => _product.Name = value;
    }

    public decimal Price
    {
        get => _product.Price;
        set => _product.Price = value;
    }

    public bool InStock
    {
        get => _product.InStock;
        set => _product.InStock = value;
    }
}
```
