### Question 2

---

Consider the following C# code:

```csharp
public class MilesToKmConverter
{
	public virtual double MilesToKmFactor { get { return 1.609; } }
	
	public double MilesToKm(double miles)
	{
		return this.MilesToKmFactor * miles;
	}
}

public class NauticalMilesToKmConverter : MilesToKmConverter
{
	public override double MilesToKmFactor { get { return 1.852; } }
}
```

Select all the correct answers.

\
\
**Answers:**

```csharp
((MilesToKmConverter)new NauticalMilesToKmConverter()).MilesToKm(1)
```
will return 1.609
 - [ ] Selected

<br>

```csharp
new MilesToKmConverter().MilesToKm(1)
```
will return 1.609
 - [X] Selected

<br>

```csharp
((NauticalMilesToKmConverter)new MilesToKmConverter()).MilesToKm(1)
```
will return 1.852
 - [ ] Selected

<br>

```csharp
new NauticalMilesToKmConverter().MilesToKm(1)
```
will return 1.852
 - [X] Selected


---

**Previous:** [Question 1](./question1.md)  
**Next:** [Question 3](./question3.md)

[Return to Index](../readme.md)