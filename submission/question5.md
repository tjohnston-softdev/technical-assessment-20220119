### Question 5

---

The `DocumentStore` class is used to model a document store. It needs to satisfy the following conditions:

* The `Documents` property should return the contents of the store. There should be no way to modify the content through it or through the object it returns, except with the reflection.

* The `AddDocument(document)` method should add a new document to the store. If the store is full, `InvalidOperationException` should be thrown.

* The `ToString()` method should return the document store's description in the format "Document store: number of documents/capacity". For example, if the capacity of the document store is 2 and one document is added to it, it should return "Document store: 1/2".

Fix the bugs!

```csharp
using System;
using System.Collections.Generic;

public class DocumentStore
{
    private readonly List<string> documents = new List<string>();
    private readonly int capacity;

    public DocumentStore(int capacity)
    {
        capacity = capacity;
    }

    public int Capacity { get { return capacity; } }

    public IEnumerable<string> Documents { get { return documents; } }

    public void AddDocument(string document)
    {
        if (documents.Count > capacity)
            throw new InvalidOperationException();

        documents.Add(document);
    }

    public override string ToString()
    {
        return $"Document store: (documents.Count)/(capacity)";
    }
}

public class Program
{
    public static void Main(string[] args)
    {
        DocumentStore documentStore = new DocumentStore(2);
        documentStore.AddDocument("item");
        Console.WriteLine(documentStore);
    }
}
```

\
\
**Answer:**

```csharp
using System;
using System.Collections.Generic;

public class DocumentStore
{
    private readonly List<string> documents = new List<string>();
    private readonly int capacity;

    public DocumentStore(int enteredCapacity)
    {
        capacity = enteredCapacity;
    }

    public int Capacity { get { return capacity; } }

    public IEnumerable<string> Documents { get { return documents.AsReadOnly(); } }

    public void AddDocument(string document)
    {
        if (documents.Count < capacity)
        {
            documents.Add(document);
        }
        else
        {
            throw new InvalidOperationException();
        }
    }

    public override string ToString()
    {
        string writeRes = "";
        
        writeRes += "Document store: ";
        writeRes += documents.Count.ToString();
        writeRes += "/";
        writeRes += capacity.ToString();
        
        return writeRes;
    }
}

public class Program
{
    public static void Main(string[] args)
    {
        DocumentStore documentStore = new DocumentStore(2);
        documentStore.AddDocument("item");
        Console.WriteLine(documentStore);
    }
}
```


---

**Previous:** [Question 4](./question4.md)  
**Next:** [Question 6](./question6.md)

[Return to Index](../readme.md)