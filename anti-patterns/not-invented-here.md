## Not invented here
The `Not Invented Here` anti-pattern, often abbreviated as NIH, refers to the tendency of developers or organizations to avoid using existing solutions or libraries in favor of building their own, even when suitable and proven solutions already exist. This can lead to wasted time, resources, and increased complexity.

#### Simple Explanation:
Imagine you have a problem to solve, and instead of using a well-established solution that others have already developed and tested, you decide to build your own solution from scratch. This is the `Not Invented Here` anti-pattern.

#### Example of Not Invented Here (Before):

Consider a scenario where a software project needs to parse JSON data, and the developer decides to create a custom JSON parser instead of using a well-known library:

```csharp
public class CustomJsonParser
{
    public Dictionary<string, object> ParseJson(string json)
    {
        // Custom JSON parsing logic implemented here
        // This is reinventing the wheel
        // ...
    }
}
```

In this example, the developer is creating a custom JSON parser despite the availability of well-tested and widely used JSON parsing libraries like Newtonsoft.Json.

#### Refactored Code (After):

To address the `Not Invented Here` anti-pattern, it's often better to leverage existing, well-established solutions. Here's an example using Newtonsoft.Json:

```csharp
using Newtonsoft.Json;

public class JsonParser
{
    public Dictionary<string, object> ParseJson(string json)
    {
        // Use a widely adopted JSON parsing library
        return JsonConvert.DeserializeObject<Dictionary<string, object>>(json);
    }
}
```

In the refactored code, the widely adopted Newtonsoft.Json library is used for JSON parsing. This approach is more maintainable, less error-prone, and avoids unnecessary reinvention of functionality that is already available and well-tested. It's often a good practice to rely on established libraries and frameworks, as they are likely to be more robust and have undergone extensive testing and optimization.