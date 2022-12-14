# Searching

Searching is the process of finding an item with specified properties among a collection of items. The items may be stored as records in database, elements in arrays, texts in files nodes in trees and etc.

## Types of searching

- Linear search (unordered & ordered)
- Binary search
- Hashing
- String searching algorithm, Tries suffix trees

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

### Binary search

Binary search is a very simple, yet efficient searching algorithm based on divide-and-conquer strategy. The only caveat is that it works only on sorted arrays, so some preprocessing on data might be required.

#### Implementation of binary search

Middle element: Math.floor((**startIndex** + **endIndex**) / 2)

- Find the middle element of the given array.
- Compare the middle element with the value we are looking for (called **key**)
  - If the key is less than the middle element, search in the left half (**endIndex = mid - 1**).
  - If the key is greater than the middle element, search in the right half (**startIndex = mid + 1**).
  - If the key is equal to the middle element, return the index of the middle element.
- Continue with steps 1,2 unitl **startIndex** is either less than or equal to **endIndex**.
- If the key is still not found return -1.

```js
function binarySearch(arr, key) {
  let startIndex = 0;
  let endIndex = arr.length - 1;

  while (startIndex <= endIndex) {
    let mid = Math.floor((startIndex + endIndex) / 2);

    if (arr[mid] === key) {
      return mid;
    } else if (key < arr[mid]) {
      endIndex = mid - 1;
    } else {
      startIndex = mid + 1;
    }
  }

  return -1;
}
```
