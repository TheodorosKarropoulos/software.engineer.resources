## Extract Variable
The `Extract Variable` refactoring technique involves creating a new variable to hold the result of an expression or part of a complex statement. This technique improves code readability by giving a meaningful name to a value that might otherwise be embedded in the code.
#### Simple Explanation:
Imagine you have a complex expression or value within your code. Instead of using that expression directly, you can assign it to a variable with a meaningful name. This is the `Extract Variable` refactoring.
#### Example of Extract Variable (Befor):
Consider a method that calculates the total price of items in a shopping cart with some complex logic:
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
#### Refactored Code using "Extract Variable" (After):
In this refactoring, we'll extract the result of the complex calculation for the item price into a separate variable:
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
            // Extracted variable for calculating item price
            decimal baseItemPrice = item.Price * item.Quantity;

            // Additional logic, perhaps applying discounts or taxes
            decimal discountedPrice = ApplyDiscounts(baseItemPrice);
            decimal finalItemPrice = ApplyTaxes(discountedPrice);

            totalPrice += finalItemPrice;
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
In this refactored code, the result of the calculation for the item price is now stored in the `baseItemPrice` variable, making the code inside the loop more readable. This variable is then used in subsequent steps, improving clarity and maintainability.