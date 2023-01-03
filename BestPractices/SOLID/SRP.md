#### Single Responsibility Principle

*Definition:*

The Single Responsibility Principle (SRP) is a software design principle that states that a class or module should have only one reason to change. In other words, it should have a single, well-defined responsibility, and should not be responsible for multiple, unrelated tasks.

*Code Example:*

```csharp
public class User
{
    private readonly IUserRepository repository;
    public User(IUserRepository repository)
    {
        this.repository = repository;
    }

    public void Save(User user)
    {
        // Validate user input
        if (string.IsNullOrEmpty(user.Username))
        {
            throw new ArgumentException("Username is required");
        }

        // Save user to repository
        repository.Save(user);
    }
}
```

In this example, the User class has a single responsibility: saving a user to the repository. It does not have any other responsibilities, such as validating user input or sending email notifications. This helps to ensure that the class is simple and easy to understand, and that it is easy to modify or extend without causing unintended side effects.
