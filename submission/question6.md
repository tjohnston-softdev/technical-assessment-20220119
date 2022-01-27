### Question 6

---

Write a function that removed all items that are not numbers from the array. The function should modify the existing array, not create a new one.

For example, if the input array contains values `[1, 'a', 'b', 2]`, after processing, the array will only contain the values `[1, 2]`.

```javascript
function filterNumbersFromArray(arr) {
  // Write the code that goes here
}

var arr = [1, 'a', 'b', 2];
filterNumbersFromArray(arr);
// At this point, arr should have been modified in place
// and contain only 1 and 2.
for (var i = 0; i < arr.length; i++)
  console.log(arr[i]);
```

\
\
**Answer:**

```javascript
function filterNumbersFromArray(arr)
{
  var elementIndex = 0;
  var currentElement = null;
  var currentType = "";
  
  while (elementIndex >= 0 && elementIndex < arr.length)
    {
      currentElement = arr[elementIndex];
      currentType = typeof currentElement;
      
      if (currentType === "number")
      {
        elementIndex += 1;
      }
      else
      {
        arr.splice(elementIndex, 1);
      }
      
    }
}

var arr = [1, 'a', 'b', 2];
filterNumbersFromArray(arr);
// At this point, arr should have been modified in place
// and contain only 1 and 2.
for (var i = 0; i < arr.length; i++)
  console.log(arr[i]);
```


---

**Previous:** [Question 5](./question5.md)  
**Next:** [Question 7](./question7.md)

[Return to Index](../readme.md)