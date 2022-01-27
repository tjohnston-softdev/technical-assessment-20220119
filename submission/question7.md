### Question 7

---

A program you are writing adds various math methods to the `double` struct in such a way that they can be used as any other instance method of the `double` struct.

Add a `Log10()` method to the `double` struct that calls the `Math.Log10(double)` method in such a way that `10.0.Log10();` would return `1.0`.

```csharp
using System;

public static class LogPatch
{
    // Write the code that goes here.
            
    public static void Main(string[] args)
    {
        // Example case.
        // Console.WriteLine(10.0.Log10());
    }
}
```

\
\
**Answer:**

```csharp
using System;

public static class DoubleExtensions
{
    public static double Log10(this double dblVal)
    {
        return Math.Log10(dblVal);
    }
}


public static class LogPatch
{  
    public static void Main(string[] args)
    {
        // Example case.
        double res = 10.0.Log10();
		Console.WriteLine(res);
    }
}
```


---

**Previous:** [Question 6](./question6.md)  
**Next:**

[Return to Index](../readme.md)