# Challenge #1: First gift repeated! 🎁

## Instructions

**Santa Claus** 🎅 has received a list of magical numbers representing gifts 🎁, but some of them are duplicated and must be removed to avoid confusion. Additionally, **the gifts must be sorted in ascending order before being delivered to the elves**.

Your task is to write a function that receives a list of integers (which may include duplicates) and returns a new list without duplicates, sorted in ascending order.

```js
const gifts1 = [3, 1, 2, 3, 4, 2, 5]
const preparedGifts1 = prepareGifts(gifts1)
console.log(preparedGifts1) // [1, 2, 3, 4, 5]

const gifts2 = [6, 5, 5, 5, 5]
const preparedGifts2 = prepareGifts(gifts2)
console.log(preparedGifts2) // [5, 6]

const gifts3 = []
const preparedGifts3 = prepareGifts(gifts3)
console.log(preparedGifts3) // []
// There are no gifts, the list remains empty
```

## Solution

```js
function prepareGifts(gifts) {

  // Remove duplicate gifts by converting the array
  // into a Set and then back to an array.
  const uniqueGifts = [...new Set(gifts)]

  // Sort the unique gifts in ascending order
  // (numerical sorting)
  const sortedGifts = uniqueGifts.sort( (a, b) => a - b )

  return sortedGifts
}
```

+ `Set` es una estructura de datos en JS que ***almacena valore únicos***, eliminando automáticamente duplicados.

+ `sort()`
  + Método que ordena un array.
  + Para ordenar números correctamente, se usa una función de comparación como `(a, b) => a - b`
    + Si el resultado es negativo, `a` va antes que `b`.
    + Si el resultado es positivo, `b` va antes que `a`.
    + Si es 0, el orden permanece.


## Resources

📺 [Detect if Array has duplicate elements in JavaScript](https://www.youtube.com/watch?v=FA_6XaPzcs0) by @midudev (Spanish)

📺 [How to SORT any ARRAY in JavaScript](https://www.youtube.com/watch?v=gmDAMQiyfSE) by @Dorian Designs (Spanish)

***
[🔙 AdventJS](../README.md)