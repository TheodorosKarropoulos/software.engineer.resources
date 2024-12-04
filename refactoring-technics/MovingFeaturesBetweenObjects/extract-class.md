## Extract class
The `Extract Class` refactoring technique involves moving part of the functionality from an existing class into a new class. This is often done when a class becomes too large, has too many responsibilities, or when a subset of its features could be better encapsulated in a separate, more specialized class.
### Simple Explanation:
If a class is doing too much or has a section of functionality that could be better encapsulated in its own class, you can create a new class and move that functionality into it. This can lead to a more modular and maintainable codebase.
### Example of Code Before Extract Class:
Consider a class that manages both a person's information and their employment details:
```csharp
public class Person
{
    public string FirstName { get; set; }
    public string LastName { get; set; }

    public string JobTitle { get; set; }
    public decimal Salary { get; set; }

    public void DisplayPersonDetails()
    {
        Console.WriteLine($"Name: {FirstName} {LastName}");
        Console.WriteLine($"Job Title: {JobTitle}");
        Console.WriteLine($"Salary: {Salary:C}");
    }
}
```
### Refactored Code using Extract Class:
In this refactored code, we'll create a new class, `JobDetails`, to encapsulate employment-related information:
```csharp
public class Person
{
    public string FirstName { get; set; }
    public string LastName { get; set; }

    public JobDetails EmploymentDetails { get; set; }

    public void DisplayPersonDetails()
    {
        Console.WriteLine($"Name: {FirstName} {LastName}");
        EmploymentDetails.DisplayJobDetails();
    }
}

public class JobDetails
{
    public string JobTitle { get; set; }
    public decimal Salary { get; set; }

    public void DisplayJobDetails()
    {
        Console.WriteLine($"Job Title: {JobTitle}");
        Console.WriteLine($"Salary: {Salary:C}");
    }
}
```
In the refactored code, the employment-related information has been moved into a separate class, `JobDetails`. The `Person` class now has a property of type `JobDetails`, and the `DisplayPersonDetails` method calls the `DisplayJobDetails` method from the `JobDetails` class. This separation of concerns can make the code more modular and easier to understand and maintain.