# JS-homework
*Автор: Екатерина Черных*
### Задание 1
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
console.log(resultObj) // { boolean: 2, number: 2, object: 1, string: 1 }
```
