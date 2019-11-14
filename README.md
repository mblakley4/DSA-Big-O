# Big O Notation

## Even or Odd
```javascript
function isEven(value){
  if (value % 2 == 0){
    return true;
  }
  else
    return false;
}
```
O(1), constant time: only one expression evaluated

## Are You Here
```javascript
function areYouHere(arr1, arr2) {
    for (let i=0; i<arr1.length; i++) {
        const el1 = arr1[i];
        for (let j=0; j<arr2.length; j++) {
            const el2 = arr2[j];
            if (el1 === el2) return true;
        }
    }
    return false;
}
```
O(n^2), polynomial: two nested loops

## Doubler
```javascript
function doubleArrayValues(array) {
    for (let i=0; i<array.length; i++) {
        array[i] *= 2;
    }
    return array;
}
```

O(n), linear: one expression evaluated on each item of the array

## Naive Search
```javascript
function naiveSearch(array, item) {
    for (let i=0; i<array.length; i++) {
        if (array[i] === item) {
            return i;
        }
    }
}
```
O(n), linear: up until the value is found

## Creating Pairs
```javascript
function createPairs(arr) {
    for (let i = 0; i < arr.length; i++) {
        for(let j = i+1; j < arr.length; j++) {
            console.log(arr[i] + ", " +  arr[j] );
        }
    }
}
```
O(n^2), polynomial:  nested loops

## Compute the sequence
```javascript
function compute(num) {
  let result = [];
    for (let i = 1; i <= num; i++) {

        if (i === 1) {
            result.push(0);
        }
        else if (i == 2) {
            result.push(1);
        }
        else {
            result.push(result[i - 2] + result[i - 3]);
        }
    }
    return result;
}
```
Fibonacci sequence.  O(n) this iterates from 0 to the input and performs one expression per operation

## An Efficient Search
```javascript
function efficientSearch(array, item) {
    let minIndex = 0;
    let maxIndex = array.length - 1;
    let currentIndex;
    let currentElement;

    while (minIndex <= maxIndex) {
        currentIndex = Math.floor((minIndex + maxIndex) / 2);
        currentElement = array[currentIndex];

        if (currentElement < item) {
            minIndex = currentIndex + 1;
        }
        else if (currentElement > item) {
            maxIndex = currentIndex - 1;
        }
        else {
            return currentIndex;
        }
    }
    return -1;
}
```
O(log n), logarithmic: halves the search size every iteration assuming the array is sorted

## Random Element
```javascript
function findRandomElement(arr) {
    return arr[Math.floor(Math.random() * arr.length)];
}
```
O(1) This will run one expression no matter the input array size

## What Am I?
```javascript
function isWhat(n) {
    if (n < 2 || n % 1 != 0) {
        return false;
    }
    for (let i = 2; i < n; ++i) {
        if (n % i == 0) return false;
    }
    return true;
}
```
Checks if prime.  O(n) one expression run on each iteration
