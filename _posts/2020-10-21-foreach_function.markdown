---
layout: post
title:      ".forEach Function"
date:       2020-10-22 03:49:08 +0000
permalink:  foreach_function
---


The forEach is a function that will call each element in the array one time.

There are 3 parameters that can be used when using .forEach prototype.

The 1st parameter being passed into the .forEach is the currentValue (item) which shown in the output below:

```
let items = [
     { id: 1, lanuage:  'Ruby', level: 'Novice' },
		 { id: 2, lanuage:  'JavaScript', level: 'Intermediate' },
		 { id: 3, lanuage:  'React', level: 'Advanced' },
]

items.forEach(function(item) => {
console.log(item)
});

\\ output:   { id: 1, lanuage: 'Ruby', level: 'Novice' }
                     { id: 2, lanuage: 'JavaScript', level: 'Intermediate' }
                     { id: 3, lanuage: 'React', level: 'Advanced' }
```

The 2nd parameter parameter passed allows you to display the `index` of the item in the array, see output below.

```
items.forEach(function(item, index) => {
console.log(index, item)
});

\\ output: 0 { id: 1, lanuage: 'Ruby', level: 'Novice' }
                   1 { id: 2, lanuage: 'JavaScript', level: 'Intermediate' }
                   2 { id: 3, lanuage: 'React', level: 'Advanced' }

```

The 3rd parameter passed allows you to display entire array that the forEach was called on, see output below.

```
items.forEach(function(item, index, array) => {
console.log(index, item, array)

\\ output: 0 { id: 1, lanuage: 'Ruby', level: 'Novice' } [ { id: 1, lanuage: 'Ruby', level: 'Novice' },
                       { id: 2, lanuage: 'JavaScript', level: 'Intermediate' },
                       { id: 3, lanuage: 'React', level: 'Advanced' } ]
                   1  { id: 2, lanuage: 'JavaScript', level: 'Intermediate' } [ { id: 1, lanuage: 'Ruby', level: 'Novice' },
                       { id: 2, lanuage: 'JavaScript', level: 'Intermediate' },
                       { id: 3, lanuage: 'React', level: 'Advanced' } ]
                   2 { id: 3, lanuage: 'React', level: 'Advanced' } [ { id: 1, lanuage: 'Ruby', level: 'Novice' },
                       { id: 2, lanuage: 'JavaScript', level: 'Intermediate' },
                       { id: 3, lanuage: 'React', level: 'Advanced' } ]
```

The .forEach does not return anything but it allows you to logout each item in the array in any way that we choose whether it just be the index, the item, or just the original array.  










