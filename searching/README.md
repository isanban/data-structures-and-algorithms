# Searching

Searching is the process of finding an item with specified properties among a collection of items. The items may be stored as records in database, elements in arrays, texts in files nodes in trees and etc.

## Types of searching

- Linear search (unordered & ordered)
- Binary search
- Hashing
- String searching algorithm, Tries suffix trees

First we will discuss **unordered linear search**, **ordered linear search** and **binary search**.

### Linear search (unordered)

Linear search is the simplest searching algorithm. In this type of search, a sequential search is made over all items one by one.

```js
let arr = [5, 8, 2, 9, 1];

function findElement(arr, elm) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === elm) {
      return i;
    }
  }

  return -1;
}
```

#### Complexity

- Time complexity: O(n)
- Space complexity: O(1) because no extra space has been used.

### Linear search (ordered)

In ordered linear search a sequential search is made over items of an array one by one but with one extra check, because we know that list is sorted if the item that we are looking is less than the current item we simply returned from that point to prevent further iterations.

```js
let arr = [1, 4, 7, 8, 12];

function findElement(arr, elm) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === elm) {
      return i;
    }

    if (arr[i] > elm) {
      return -1;
    }
  }

  return -1;
}
```

#### Complexity

- Time complexity: O(n)
- Space complexity: O(1) because no extra space has been used
