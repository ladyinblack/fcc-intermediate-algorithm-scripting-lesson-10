## ALTERNATE SOLUTIONS

### Solution 1
```js
function uniteUnique(arr1, arr2, arr3) {
  // Creates an empty array to store our final result.
  const finalArray = [];

  // Loop through the arguments object to truly make the program work with two or more arrays
  // instead of 3.
  for (let i = 0; i < arguments.length; i++) {
    const arrayArguments = arguments[i];

    // Loops through the array at hand
    for (let j = 0; j < arrayArguments.length; j++) {
      let indexValue = arrayArguments[j];

      // Checks if the value is already on the final array.
      if (finalArray.indexOf(indexValue) < 0) {
        finalArray.push(indexValue);
      }
    }
  }

  return finalArray;
}

uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]);
```

### Code Explanation
- Create empty array **finalResult** to store the final result.
- Loop through the **arguments** object in the outer loop and store it in **arrayArguments**.
- The inner loop is used to loop through individual array elements.
- If the element doesn't already exist in **finalArray**, add it.
- Return **finalArray**.

### REFERENCE LINKS
- [JS For Loops Explained](https://www.freecodecamp.org/news/javascript-for-loops/)
- [`array.length`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/length)
- [JS String Prototype IndexOf](https://forum.freecodecamp.org/t/javascript-string-prototype-indexof-index-of-explained-with-examples/15936)
- [JS Array Prototype Push](https://forum.freecodecamp.org/t/how-to-use-javascript-array-prototype-push-javascript-push-explained-with-examples/14298)


### Solution 2
```js
function uniteUnique(arr) {
  const args = [...arguments];
  const result = [];
  for (let i = 0; i < args.length; i++) {
    for (let j = 0; j < args[i].length; j++) {
      if (!result.includes(args[i][j])) {
        result.push(args[i][j]);
      }
    }
  }
  return result;
}

uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]);
```

### Solution 3
```js
function uniteUnique(...arr) {
  return [...new Set(arr.flat())];
}

// Or as an arrow function
const uniteUnique = (...arr) => [...new Set(arr.flat())];
```

### REFERENCE LINKS
- [Array.prototype.flat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flat)
- [Arguments](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)
- [Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)

### Solution 4
```js
function uniteUnique() {
  return [...arguments]
    .flat()
    .filter((item, ind, arr) => arr.indexOf(item) === ind);
}

uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]);
```

