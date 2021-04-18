# Technical-Interview-A

## findOdd

[REPL](https://repl.it/@michaelpetty/findOdd#index.js)

Given an array, find the int that appears an odd number of times. Assume there will always be only one integer that appears an odd number of times.

```javascript
function findOdd(array) {
  // happy coding!
}

// Tests:
findOdd([20,1,-1,2,-2,3,3,5,5,1,2,4,20,4,-1,-2,5]);
// => 5

findOdd([1,1,2,-2,5,2,4,4,-1,-2,5]);
// => -1

findOdd([20,1,1,2,2,3,3,5,5,4,20,4,5]);
// => 5

findOdd([10]);
// => 10

findOdd([1,1,1,1,1,1,10,1,1,1,1]);
// => 10

findOdd([5,4,3,2,1,5,4,3,2,10,10]);
// => 1
```

<hr>

## Solution

<details>
  <summary>Click here to reveal a possible solution.</summary>
  <p>

```javascript
// SOLUTION 1
function findOddOccurrence(array) {
  let oddOccuringNum = null;

  // Loop through array
  array.forEach((int) => {
    // for each int
      
    // find number of occurrences
      let occurrences = 0;

      array.forEach((num) => {
        if (num === int) {
          occurrences += 1;
        }
      });

      // if occurrences is odd return
      if (occurrences % 2 === 1) {
        oddOccuringNum = int;
      }
  });

  return oddOccuringNum;
}

// SOLUTION 2
// Loop through array
  // for each int
  // find number of occurrences
  // if occurrences is odd return int
function findOddOccurrence(array) {
  return array.find((int) => {
    const occurrences = array.filter(num => num === int).length;
    return occurrences % 2 === 1;
  });
}
  ```

</p>
</details>

<hr>

# SmallestInt

[REPL](https://repl.it/@michaelpetty/smallestInt)

Given an array of integers your solution should find the smallest integer.

For example:
```
Given [34, 15, 88, 2] your solution will return 2
Given [34, -345, -1, 100] your solution will return -345
```

You can assume, for the purpose of this problem, that the supplied array will not be empty.

```javascript
function findSmallestInt(args) {
  // Happy coding!  
}
```

<hr>

## Solution

<details>
  <summary>Click here to reveal a possible solution.</summary>
  <p>

```javascript
// SOLUTION 1
function findSmallestInt(array) {
  let smallestInt = null;

  // Loop through array
  array.forEach((int) => {
    if (smallestInt === null) {
      smallestInt = int;
    } else {
      // if number is smallest so far make it new smallest number
      if (int < smallestInt) {
        smallestInt = int;
      }
    }
  });
  // return the smallest number
  return smallestInt;
}

///////////////////////////////////////////////////////
// SOLUTION 2
function findSmallestInt(array) {
  return array.reduce((smallest, int) => {
    return int < smallest ? int : smallest;
  }, Infinity);
}

///////////////////////////////////////////////////////
// SOLUTION 3
function findSmallestInt(array) {
  return Math.min(...array);
}
```

</p>
</details>

<hr>

# Convert to CamelCase

[REPL](https://repl.it/@michaelpetty/camelCase#index.js)

Complete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case).

Examples:
```javascript
toCamelCase("the-stealth-warrior") // returns "theStealthWarrior"

toCamelCase("The_Stealth_Warrior") // returns "TheStealthWarrior"
```

<hr>

## Solution

<details>
  <summary>Click here to reveal a possible solution.</summary>
  <p>

  ```javascript
// SOLUTION 1
function toCamelCase(phrase) {
  // If phrase contains - split on -
  let splitChar = '';
  if (phrase.includes('-')) {
    splitChar = '-';
    // If phrase contains _ split on _
  } else if (phrase.includes('_')) {
    splitChar = '_';
  }

  const words = phrase.split(splitChar);

  // Loop through each word
  const wordsWCaps = words.map((word, index) => {
    // Capitalize first letter of each word
    if (index === 0) {
      return word;
    }
    return word.charAt(0).toUpperCase() + word.slice(1);
  });

  // Join words and return
  return wordsWCaps.join('');
}


// convert string to array of words
// Loop through array
  // for each word after 1st, convert to capital casing
  // join words into single string

// SOLUTION 2
function toCamelCase(phrase) {
  const words = phrase.split(/[-_]/);

  const convertedWords = words.map((word, index) => {
    if (!index) return word;
    return word.charAt(0).toUpperCase() + word.slice(1);
  });

  return convertedWords.join('');
}

  ```
  </p>
</details>

# Knowledge Check
Technical interviews aren't often 100% coding. Usually your interviewer will ask you some questions to guage your knowledge in a particular topic. Run through these questions with your partner and if you come across one that you both aren't sure about, run down an answer together or call for help.

<hr>

### HTML/CSS
1. Does a hyperlink only apply to text?
2. What is semantic HTML?
3. What is the use of required attribute in HTML5?
4. What are the three main ways to add CSS to a webpage?

### Javascript
1. Which one is more efficient, `document.getElementbyId("myId")` or `$("#myId")`? 
2. What is ‘NaN’? What is its type?
3. What will be the output when the following code is executed?

```javascript
var x = 21;
var girl = function () {
    console.log(x);
    var x = 20;
};
girl();
```

### Node/Express
1. Why use NodeJs?
2. Explain the role of REPL (not the repl.it web app!) in Node.js .
3. What are Synchronous and Asynchronous calls?
4. What is the purpose of module.exports in Node.js?

### Python/Django
1. What are dunder methods in Python?
2. What is dictionary in Python?
3. Name the features available in Django or Flask web framework?

### React
1. List some of the major advantages of React.
2. What are the features of React? 
3. What is JSX?
4. What are Pure Components?

# Technical-Interview-B

## Square Every Digit

[REPL](https://repl.it/@michaelpetty/SquareEveryDigit)

Welcome. In this problem, you are asked to square every digit of a number.

For example, if we run 9119 through the function, 811181 will come out, because 9^2 is 81 and 1^2 is 1.

Note: The function accepts an integer and returns an integer

<hr>

## Solution
<details>
<summary>Click here to reveal a possible solution.</summary>
<p>

```javascript
// SOLUTION 1
function squareEveryNumber(number) {
  // Convert number into an array of digits
  const digits = number.toString().split('');

  let result = '';
  // Loop through each digit
  digits.forEach((digit) => {
    // get the square of each digit
    const square = parseInt(digit) ** 2;
    // add square to end of string
    result += square.toString();
  });

  return result;
}

// SOLUTION 2
function squareEveryNumber(number) {
  // Convert number into an array of digits
  const digits = number.toString().split('');

  // Get an array of squares as strings
  const squares = digits.map((digit) => {
    const square = parseInt(digit) ** 2;
    return square.toString();
  });

  // Join all the square strings together
  return squares.join('');
}

// SOLUTION 3
function squareDigits(num){
    var string = num.toString();
    var results = [];
    for (var i = 0; i < string.length; i++){
        results[i] = string[i] * string[i];
    }
    return Number(results.join(''));
};


// SOLUTION 4
function squareDigits(num){
  return num.toString().split('').map(i => i * i).join('');
}
```
</p>
</details>

<hr>

# Regex PIN Validator

[REPL](https://repl.it/@michaelpetty/RegexPINValidator#index.js)

ATM machines allow 4 or 6 digit PIN codes and PIN codes cannot contain anything but exactly 4 digits or exactly 6 digits.

If the function is passed a valid PIN string, return true, else return false.

eg:
```javascript
validatePIN("1234") === true
validatePIN("12345") === false
validatePIN("a234") === false
```

<hr>

## Solution
<details>
<summary>Click here to reveal a possible solution.</summary>
<p>
  
  ```javascript
  // a solution, but nothing special 
  function validatePIN(pin) {
    //return true or false
    var n = pin.length;
    if( n != 4 && n != 6)
        return false;
    for (var i in pin)
        if (pin[i] > '9' || pin[i] < '0')
            return false;
    return true;
  }
  
  // good solution
  function validatePIN(pin) {

    var pinlen = pin.length;
    var isCorrectLength = (pinlen == 4 || pinlen == 6);
    var hasOnlyNumbers = pin.match(/^\d+$/);

    if(isCorrectLength && hasOnlyNumbers){
      return true;
    }

    return false;

  }
  
  // cleanest solution
  function validatePIN(pin) {
    return /^(\d{4}|\d{6})$/.test(pin)
  }
  ```
</p>
</details>

<hr>

# Growth of a Small Town

[REPL](https://repl.it/@michaelpetty/GrowthSmallTown#index.js)

In a small town the population is 1000 at the beginning of a year (p0). The population regularly increases by 2 percent per year and in addition to that, 50 new inhabitants per year come to live in the town. How many years will it take for the town to see its population greater or equal to 1200 inhabitants?

```
At the end of the first year there will be: 
1000 + 1000 * 0.02 + 50 => 1070 inhabitants

At the end of the 2nd year there will be: 
1070 + 1070 * 0.02 + 50 => 1141 inhabitants (number of inhabitants is an integer)

At the end of the 3rd year there will be:
1141 + 1141 * 0.02 + 50 => 1213

It will need 3 entire years.
```

Write a function that takes in the starting population, the rate of population growth, the number of new inhabitants, and the population limit. The function should return the number of years it will take to reach or surpass the population limit.

Examples:
```javascript
calcYears(startingPop, growthRate, newcomers, limit) {
  // Calculate years here
}

calcYears(1500, 5, 100, 5000) -> 15
calcYears(1500000, 2.5, 10000, 2000000) -> 10
```

Note: Don't forget to convert the `percent` parameter as a percentage in the body of your function: if the parameter `percent` is `2` you have to convert it to `0.02`.

<hr>

## Solution
<details>
<summary>Click here to see the solution</summary>
<p>
  
  ```javascript
  // good and readable solution
  function calcYears(startingPop, growthRate, newComers, limit) {
    let population = startingPop;
    let year = 0;

    // Increment the population and the year while the population is under
    // the limit.
    while (population <= limit) {
      population = population + (population * growthRate / 100) + newComers;
      year++;
    }

    return year;
  }
  
  // nice use of recursion
  function calcYears(p0, percent, aug, p) {
      // your code
      if (p0 >= p) {
        return 0;
      }

      return 1 + calcYears(p0 + p0 * percent / 100 + aug, percent, aug, p);
  }
  
  // clever, but not best practice
  function calcYears(p0, percent, aug, p, years = 0) {
    return p0 < p ? calcYears(p0 + p0 * percent / 100 + aug, percent, aug, p, years + 1) : years; 
  }
  ```
</p>
</details>

# Knowledge Check
Technical interviews aren't often 100% coding. Usually your interviewer will ask you some questions to guage your knowledge in a particular topic. Run through these questions with your partner and if you come across one that you both aren't sure about, run down an answer together or call for help.

<hr>

### HTML/CSS
1. List the basic layout components of the CSS box model with a brief description for each.
2. What is the difference between `<form method="get">` and `<form method="post">`?
3. What’s the difference between display:inline and display:inline-block?
4. What is the default position property?

### Javascript
1. What will be the output of this code?
```javascript
console.log(false == '0');
console.log(false === '0');
```
2. How do you add an element at the beginning and end of an array in ES6?
3. What's the difference between Javascript and jQuery?

### Node/Express
1.	What is package.json? What is it used for?
2.	What is typically the first argument passed to a Node.js callback handler?
3.	What is local installation of dependencies in NPM?
4.	What is global installation of dependencies?

### Python/Django
1. What does this mean: ```*args```, ```**kwargs```? And why would we use it?
2. What are the advantages of using Django/Flask for web development?
3. What is the process of creating a project in Django/Flask?
4. What is the difference between list and tuples?

### React
1. What is a state in React and how is it used?
1. Differentiate between states and props.
1. Differentiate between stateful and stateless components.
1. What is the significance of keys in React?
