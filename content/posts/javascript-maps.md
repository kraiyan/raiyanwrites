---
title: "JavaScript Basic Concepts of Map"
date: 2024-08-12T10:00:00+06:00
draft: false
cover:
    image: img/js-maps.jpeg
    alt: 'This is test'
    caption: 'Javscript maps'
description: "Understanding the basic concepts of the JavaScript Map object, including how it works, use cases, and examples."
tags: ["JavaScript", "Map", "Data Structures", "Programming"]
categories: ["Web Development", "JavaScript"]
---

The `Map` object in JavaScript is a collection of key-value pairs where the keys can be of any data type. It is similar to an object but provides more flexibility with key types.

### Key Features of Map
1. **Unique Keys**: A Map object doesn’t allow duplicate keys. Each key is unique.
2. **Any Data Type for Keys**: Unlike objects, a map's keys can be of any type, even functions, objects, or primitive values.
3. **Order of Elements**: The elements in a Map are ordered. They are iterated in the order of their insertion.
4. **Size Property**: Map has a `size` property that returns the number of key-value pairs.
5. **Iterable**: You can iterate through a Map's keys, values, or entries using methods like `keys()`, `values()`, `entries()`, and for...of loops.

### Creating a Map
```javascript
const myMap = new Map();
myMap.set('name', 'John Doe');
myMap.set(42, 'The Answer');
myMap.set(true, 'boolean key');
console.log(myMap.get('name'));
console.log(myMap.has(42));  // Output: true
myMap.delete('name');  // Removes the key-value pair with the key 'name'
for (let [key, value] of myMap) {
    console.log(key, value);
}
```

This above code snippet, we have declared one single map and stored multiple key values in it . By providing any specific key,we can find any value that we want in O(1) time complexity. This is very beneficial in specific codes

So now next , we will learn about how we can use this technique in solving problem in efficient time.

[Count element frequency of an array](https://takeuforward.org/data-structure/count-frequency-of-each-element-in-the-array/).

This is a very popular basic question in dsa of counting multiple occurrences of all the element in the array.So if we use normal array iterating function, then we have to iterate through the whole array twice.But by using a map,we can do it by just O (1) time complexity.Let's deep dive into how we can make it in action.

```javascript
function calculateElementCounts(inputArray) {
    const counts = new Map();
    for (const item of inputArray) {
        counts.set(item, (counts.get(item) || 0) + 1);
    }
    return counts; 
}
const inputData = 
    [5, 6, 6, 7, 7, 7, 8, 8, 8, 8];
const countsMap = 
    calculateElementCounts(inputData);
```

In this above code snippet, we have used a map to store all the occurrences of an element by using the get function to get the counts of all the elements in the array and updating it by one if found existing element. This algorithm is very time efficient as it gets the job done in O(1) algorithm.

By using this approach we got rid of looping the array twice which required big O (n^2) time complexity. Hence,In this blog, we learnt about how basic map works and how we can reduce and optimiise our solution by using maps.