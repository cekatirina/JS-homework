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

### Задание 3
```js
function sum(left_value, right_value) { 
    if ((typeof left_value !== 'number') && (typeof right_value !== 'number')) { 
      return 'Operands are not numbers';
    }
    else if (typeof left_value !== 'number') { 
      return 'The left operand is not number'; 
    }
    else if (typeof right_value !== 'number') { 
      return 'The right operand is not number';
    }
    else {
      return left_value + right_value; //
    }    
}

// Тест:
const testSum_num = sum(2, 3)
const testSum_left = sum('hey', 12)
const testSum_right = sum(5, 'bye')
const testSum_both = sum(false, true)
console.log('testSum_num:', testSum_num, 'testSum_left:', testSum_left, 'testSum_right:', testSum_right, 'testSum_both:', testSum_both)
```

### Задание 4
```js
function getMinimalCVS(array) {
  const history = [array.slice()] 
  return {
    head: () => array.slice(), 
    history: () => history.slice(), 
    push: (new_element) => {
      array.push(new_element); 
      history.push(array.slice());
    }, 
    pop: () => {
      const new_element = array.pop();
      history.push(array.slice()); 
      return new_element 
    }
  };
}

// Тест:
const cvs = getMinimalCVS(['a', 'b', 'c']);
cvs.push('hello');
cvs.push('world')
console.log(cvs.pop()); 
console.log(cvs.history());
console.log(cvs.head())
```

### Задание 6
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
console.log(hitOrRun(8, 15))
```

### Задание 7
```js
function solutionFn(someString) {  
  let separateWords = someString.split('_'); 
  for (let singleWord = 1; singleWord < separateWords.length; singleWord++) { 
    separateWords[singleWord] = separateWords[singleWord][0].toUpperCase() + separateWords[singleWord].slice(1).toLowerCase() ; 
  }
  return separateWords.join(''); 
}

// Тест:
const someString = "backend_developer_wrote_this_name"
const testFunct = solutionFn(someString)
console.log(testFunct)
```

### Задание 8
```js
function isSpam(text, keywords) { 
  for (let len = 0; len < keywords.length; len++) {  
    if (text.toLowerCase().includes(keywords[len].toLowerCase())) { 
      return true; 
    }
  }
  return false; 
}

// Тест:
const nasty_mail = "Поздравляем! Наш алгоритм выбрал вас для доступа к ПРЕМИУМ программе. Это 100% не развод"
const good_mail = "Привет! Подскажи, пожалуйста, что задано по веб-разработке?"
const stopwords = ["Алгоритм", "Премиум", "Развод", "Выигрыш"]

const spamTest = isSpam(nasty_mail, stopwords)
const noSpamTest = isSpam(good_mail, stopwords)
console.log(spamTest, noSpamTest)
```

### Задание 9
```js
function theWorld(ms) {
  const end = new Date().getTime() + ms; 
  const interval = setInterval(() => { 
    const countDown = end - new Date().getTime(); 
    if (countDown <= 0) { 
      clearInterval(interval); 
      console.log("Время снова в силе!"); 
    } else { 
      const remainingSeconds = Math.ceil(countDown / 1000);
      console.log(`До возобновления: ${remainingSeconds} секунд / секунды / секунда`);
    }
  }, 1000);
}

// Тест:
theWorld(5000)
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
