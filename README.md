# JS-homework
*Автор: Екатерина Черных*
### Задание 2
```js
function solutionFn(object) { 
  const resultObj = {}; 
  for (let key in object) { 
    const type = typeof object[key]; 
    if (resultObj[type]) { 
      resultObj[type]++; 
    } else {
      resultObj[type] = 1; 
    }
  }
  return resultObj;
};

// Тест:
const initialObj = {
  a: 'hello',
  b: false,
  c: 70,
  d: {name: 'Igor', course: 'Web Development'},
  e: true,
  f: 65
};
const resultObj = solutionFn(initialObj);
console.log(resultObj) 
```
### Задание 10
```js
function solutionFn(number) {
  while (number >= 10) {
    const digits = Array.from(String(number), Number);
    
    let product = 1;
    
    for (let i = 0; i < digits.length; i++) {
      product *= digits[i];
    }
    
    number = product;
  }
  return number;
}

// Тест:

const initialNumber = 9348
const number = solutionFn(initialNumber);
console.log(number)
```
