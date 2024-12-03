# Challenge #2: Framing names 🖼️

## Instructions

**Santa Claus** 🎅 wants to frame the names of the good children to decorate his workshop 🖼️, but the frame must follow specific rules. Your task is to help the elves generate this magical frame.

*Rules:*

+ Given an array of names, you must create a rectangular frame that contains all of them.
+ Each name must be on a line, aligned to the left.
+ The frame is built with * and has a border one line thick.
+ The width of the frame automatically adapts to the longest name plus a margin of 1 space on each side.
Example of how it works:

```js
createFrame(['midu', 'madeval', 'educalvolpz'])

// Expected result:
***************
* midu        *
* madeval     *
* educalvolpz *
***************

createFrame(['midu'])

// Expected result:
********
* midu *
********

createFrame(['a', 'bb', 'ccc'])

// Expected result:
*******
* a   *
* bb  *
* ccc *
*******

createFrame(['a', 'bb', 'ccc', 'dddd'])
```

## Solution

```js
function createFrame(names) {

  // Find the length of the longest name in the array
  const longestName= Math.max( ...names.map( name => name.length ) )

  // Create the top and bottom borders of the frame
  const frame = '*'.repeat( longestName + 4 )

  // Create each framed name with proper padding for alignment
  const framedNames = names.map( name => {
    const padding = ' '.repeat( longestName - name.length )

    return `* ${name}${padding} *`
  } )

  // Combine the frame and the names into a single
  // string, separated by newlines
  return [frame, ...framedNames, frame].join('\n')
}
```

1. `Math.max(...values)`

    + Finds the largest value in a set of numbers.
    + The spread operator (`...`) expands an array so its elements are passed as individual arguments to `Math.max`

1. `map(callback)`

    + Iterates over each element in an array, applies a function to it, and returns a new array with the results.

1. `repeat(count)`

    + Repeats a string a specified number of times and returns the resulting string.

1. `join(separator)`

    + Combines the elements of an array into a single string, separated by the specified character or string.


***
[🔙 AdventJS](../README.md)