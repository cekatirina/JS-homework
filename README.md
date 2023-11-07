# JS-homework
*Автор: Екатерина Черных*

### 1. Custom Array.prototype.filter
```js
function customFilter(array, filterFn, inplace = false) {
    if (inplace) {
        for (let i = array.length - 1; i >= 0; i--) {
            if (!filterFn(array[i], i, array)) {
                array.splice(i, 1);
            }
        }
        return array;
    } 
    else {
        const filteredArray = [];
        for (let i = 0; i < array.length; i++) {
            if (filterFn(array[i], i, array)) {
                filteredArray.push(array[i]);
            }
        }
        return filteredArray;
    }
}

// Тест:
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];
const result = customFilter(words, (word) => word.length > 6);
console.log(result) 
```

### 2. Ключи и свойства
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
  a: 'some string 1',
    b: 42,
    c: { c1: 'some string 2' },
    d: [],
    e: 123,
};
const resultObj = solutionFn(initialObj);
console.log(resultObj) 
```

### 3. Больше никаких шуток про 1 + '1' === '11'
```js
function sum(left, right) { 
    if ((typeof left !== 'number') && (typeof right !== 'number')) { 
      return 'Operands are not numbers';
    }
    else if (typeof left !== 'number') { 
      return 'The left operand is not number'; 
    }
    else if (typeof right !== 'number') { 
      return 'The right operand is not number';
    }
    else {
      return left + right; //
    }    
}

// Тест:
const test_nums = sum(7, 20)
const test_left = sum('a', 1117)
const test_right = sum(1107, 'b')
const test_both = sum('c', 'd')
console.log('test_nums:', test_nums, 'test_left:', test_left, 'test_right:', test_right, 'test_both:', test_both)
```

### 4. CVS на минималках
```js
function getMinimalCVS(array) {
  const history = [array.slice()] 
  return {
    head: () => array.slice(), 
    history: () => history.slice(), 
    push: (new_entry) => {
      array.push(new_entry); 
      history.push(array.slice());
    }, 
    pop: () => {
      const new_entry = array.pop();
      history.push(array.slice()); 
      return new_entry 
    }
  };
}

// Тест:
const cvs = getMinimalCVS(['a', 'b', 'c']);
cvs.push('d');
cvs.push('e')
console.log(cvs.pop()); 
console.log(cvs.history());
console.log(cvs.head())
```

### 5. Глобальный переключатель
```js
function globalToggle(className) {
    const elements = document.querySelectorAll('.' + className);
    
    if (elements.length === 0) {
        return;
    }
    
    const isDefault = !className.endsWith('_active');
    
    const newClassName = isDefault ? className + '_active' : 
        className.replace('_active', '');
        
    elements.forEach((element) => {
        element.classList.remove(className);
        element.classList.add(newClassName);
    });
}

// Тест:
 
```

### 6. Hit Or Run
```js
function hitOrRun(a, b) {
  let randomNumber = Math.floor(Math.random() * (b - a + 1)) + a; 
  if (randomNumber < 2) { 
    return "hit";
  }
  for (let divisor = 2; divisor <= Math.sqrt(randomNumber); divisor++) { 
    if (randomNumber % divisor === 0) {
      return "hit" + '\n' + randomNumber; 
    }
  }
  return "run" + '\n' + randomNumber;
}

// Тест:
console.log(hitOrRun(7, 20))
```

### 7. Case Converter
```js
function solutionFn(someString) {  
  let separateWords = someString.split('_'); 
  for (let singleWord = 1; singleWord < separateWords.length; singleWord++) { 
    separateWords[singleWord] = separateWords[singleWord][0].toUpperCase() + separateWords[singleWord].slice(1) ; 
  }
  return separateWords.join(''); 
}

// Тест:
const snakeData = 'data_in_snake_case';
const result = solutionFn(snakeData);
console.log(result);
```

### 10. Задача с собеседования
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
