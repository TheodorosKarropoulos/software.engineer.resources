## Extract Method
The `Extract Method` refactoring technique involves breaking down a section of code into a separate, named method. This technique is beneficial for improving code readability, promoting code reuse, and making the codebase more maintainable.
#### Simple Explanation:
Imagine you have a block of code that performs a specific task within a method. Instead of keeping all that code in one place, you can extract it into a separate method with a meaningful name. This is the `Extract Method` refactoring.
#### Example of Extract Method (Before):
Consider a method that calculates the total price of items in a shopping cart. Initially, the code might look like this:
```csharp
public class ShoppingCart
{
    private List<Item> items;

    // ... other methods ...

    public decimal CalculateTotalPrice()
    {
        decimal totalPrice = 0;

        foreach (var item in items)
        {
            // Complex logic for calculating item price
            decimal itemPrice = item.Price * item.Quantity;

            // Additional logic, perhaps applying discounts or taxes
            itemPrice = ApplyDiscounts(itemPrice);
            itemPrice = ApplyTaxes(itemPrice);

            totalPrice += itemPrice;
        }

        return totalPrice;
    }

    private decimal ApplyDiscounts(decimal price)
    {
        // Complex logic for applying discounts
        // ...

        return price;
    }

    private decimal ApplyTaxes(decimal price)
    {
        // Complex logic for applying taxes
        // ...

        return price;
    }
}
```
#### Refactored Code using "Extract Method" (After):
In this refactoring, we'll extract the logic for calculating the price of an individual item into a separate method:
```csharp
public class ShoppingCart
{
    private List<Item> items;

    // ... other methods ...

    public decimal CalculateTotalPrice()
    {
        decimal totalPrice = 0;

        foreach (var item in items)
        {
            // Extracted method for calculating item price
            decimal itemPrice = CalculateItemPrice(item);

            totalPrice += itemPrice;
        }

        return totalPrice;
    }

    private decimal CalculateItemPrice(Item item)
    {
        // Complex logic for calculating item price
        decimal itemPrice = item.Price * item.Quantity;

        // Additional logic, perhaps applying discounts or taxes
        itemPrice = ApplyDiscounts(itemPrice);
        itemPrice = ApplyTaxes(itemPrice);

        return itemPrice;
    }

    private decimal ApplyDiscounts(decimal price)
    {
        // Complex logic for applying discounts
        // ...

        return price;
    }

    private decimal ApplyTaxes(decimal price)
    {
        // Complex logic for applying taxes
        // ...

        return price;
    }
}
```
In this refactored code, the logic for calculating the price of an individual item is now encapsulated in the `CalculateItemPrice` method. This makes the `CalculateTotalPrice` method more readable and maintains a separation of concerns. It also allows for potential reuse of the `CalculateItemPrice` logic elsewhere in the codebase.