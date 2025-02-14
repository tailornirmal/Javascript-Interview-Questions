# Javascript-Interview-Questions

Repository for Interview Questions Related to JS, HTML, CSS, React JS, Redux, Tailwind, API Integration etc.

<h1>HTML Interview Questions</h1>

<p> What are the symentic tags available within HTML ?</p>

<h1>Javascript Programms</h1>

<p>Write a javascript function to get the total of given arguments like total(2,3,4,5)(4,5,6)</p>

```js
function getTotal(...args) {
  let sum = 0;
  for (let i = 0; i < args.length; i++) {
    sum += args[i];
  }

  return function (...ar) {
    for (let i = 0; i < ar.length; i++) {
      sum += ar[i];
    }
    return sum;
  };
}

console.log(total(2, 3, 4, 5)(4, 5, 6)); // Output 29
```

<p>Write a javascript function to get a count of repeated items in an array in key-value </p>

For Example:-

const values = [“pencil”, “pen”, “sharpener”, “pen”, “pencil”];

const output = [{ pencil: 2 }, { pen: 2 }, { sharpener: 1 }];

```js
function CountArrayValues(arr) {
  let obj = {};
  let result = [];
  for (let i = 0; i < arr.length; i++) {
    if (obj[arr[i]]) {
      obj[arr[i]] += 1;
    } else obj[arr[i]] = 1;
  }
  for (let key in obj) {
    result.push({ [key]: obj[key] });
  }
  return result;
}
console.log(CountArrayValues(values));
// Output - { pencil: 2, pen: 2, sharpener: 1 }
```

<p>
    Write a javascript method to find a pair of duplicate elements in the given array.<br />
    const input = [4, 3, 2, 7, 8, 2, 3, 1]; <br />
    output = [2,3]
</p>

```js
function DuplicateElementPair(arr) {
  let result = [];
  let obj = {};
  for (let i = 0; i < arr.length; i++) {
    if (obj[arr[i]]) {
      result.push(arr[i]);
    } else {
      obj[arr[i]] = 1;
    }
  }
  return result;
}

console.log(DuplicateElementPair(input));
// output - [2,3]
```

<p>
    Write a Javascript function to sort an array without using the sort method. Implement bubble sort.
</p>

```js
function SortArray(arr) {
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length; j++) {
      if (arr[j] > arr[j + 1]) {
        let tmp = arr[j];
        arr[j] = arr[j + 1];
        arr[j + 1] = tmp;
      }
    }
  }
  return arr;
}

console.log(SortArray([9, 41, 52, 6, 14, 85, 14]));
```

<p>
    Write Javascript code to find the index of individual elements in an array whose sum equals a given target and return a new array.<br /><br />
    For Example : <br />
    const input = [2, 7, 11, 15, 5, 5, 4]; <br />
    const target = 9; <br />
    output return [[0,1][5,6]];
</p>

```js
let result1 = [];
function SumByTarget(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    for (let j = i + 1; j < arr.length; j++) {
      if (arr[i] + arr[j] === target) {
        result1.push([i, j]);
      }
    }
  }
  return result1;
}

console.log(SumByTarget(input, target));
```

<p>
    Write the javascript method to the flat array.
</p>

```js
const flatten = (arr) => {
  const result = [];
  arr.forEach((item) => {
    if (Array.isArray(item)) {
      result.push(...flatten(item));
    } else {
      result.push(item);
    }
  });
  return result;
};

// Usage
const nested = [1, 2, 3, [4, 5, [6, 7], 8, 9]];
console.log(flatten(nested)); // [1, 2, 3, 4, 5, 6, 7, 8, 9]
```
