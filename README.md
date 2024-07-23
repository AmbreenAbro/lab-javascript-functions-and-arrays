<img src="https://imgur.com/XOS1Vdh.png"  width="150px" height="150px">

  

# LAB | JS Functions & Arrays

  

<br>

  

## Introduction

Manipulating arrays is a fundamental operation in coding. Whether you're summing up the total in a shopping cart, extracting first names from a list of full names, or repositioning a piece on a game board, you're likely dealing with arrays in some capacity.



  

## Requirements

  

- Fork this repo

- Clone it to your machine

  
  
  

## Submission

  

- Upon completion, run the following commands:

  

```bash

git add .

git commit -m "Solved lab"

git push origin master

```

  

- Create a Pull Request so that we can check your work.

  

<br>

  
  
  

## Instructions

  

You will work on the `src/functions-and-arrays.js` file, which is already loaded in the `index.html` file.

  

To run the JavaScript code open the `index.html` file use the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) VSCode extension.

  

To see output of your JavaScript code open the [Console in the Developer Tools](https://developer.chrome.com/docs/devtools/open/#console).

  

While following the instructions for each iteration, make sure to carefully read the instructions to fully understand the task requirements. Do not rush. You should take your time to carefully read every iteration.

  
  
  

### Note about tests

  

This LAB, along with some of the labs you will be working on during the bootcamp, is equipped with unit tests to provide automated feedback on your lab progress.

  

**After you’ve completed the basic iterations**, go to the **"Test Your Code"** section at the bottom. There you'll be asked to install the testing dependencies and run the tests to check how many tests your code is passing.

  
  
  

<br>

Iteration #1: Find the maximum

function maxOfTwoNumbers(a, b) {
  return a > b ? a : b;
}

<br>

Iteration #2: Find the longest word


function findLongestWord(words) {
  if (words.length === 0) return null;
  
  let longestWord = words[0];
  
  for (let word of words) {
    if (word.length > longestWord.length) {
      longestWord = word;
    }
  }
  
  return longestWord;
}

<br>

Iteration #3: Calculate the sum

function sumNumbers(numbers) {
  let sum = 0;
  
  for (let number of numbers) {
    sum += number;
  }
  
  return sum;
}

<br>

Bonus - Iteration #3.1: A generic sum() function

function sum(mixedArr) {
  let total = 0;

  for (let element of mixedArr) {
    if (typeof element === 'number') {
      total += element;
    } else if (typeof element === 'string') {
      total += element.length;
    } else if (typeof element === 'boolean') {
      total += element ? 1 : 0;
    }
  }

  return total;
}

<br>


Iteration #4: Calculate the average
Level 1: Array of numbers

function averageNumbers(numbers) {
  if (numbers.length === 0) return null;
  
  return sumNumbers(numbers) / numbers.length;
}

<br>


Level 2: Array of strings

function averageWordLength(words) {
  if (words.length === 0) return null;

  let totalLength = 0;

  for (let word of words) {
    totalLength += word.length;
  }

  return totalLength / words.length;
}

Bonus - Iteration #4.1: A generic avg() function


<br>


function avg(arr) {
  if (arr.length === 0) return null;
  
  let total = sum(arr);
  return total / arr.length;
}

<br>

Iteration #5: Unique arrays

function uniquifyArray(words) {
  if (words.length === 0) return null;

  let uniqueWords = [];

  for (let word of words) {
    if (!uniqueWords.includes(word)) {
      uniqueWords.push(word);
    }
  }

  return uniqueWords;
}


<br>

Iteration #6: Find elements

function doesWordExist(words, wordToSearch) {
  if (words.length === 0) return null;
  
  for (let word of words) {
    if (word === wordToSearch) {
      return true;
    }
  }

  return false;
}


<br>

Iteration #7: Count repetition

function howManyTimes(words, wordToSearch) {
  let count = 0;
  
  for (let word of words) {
    if (word === wordToSearch) {
      count++;
    }
  }

  return count;
}

<br>

Bonus - Iteration #8: Product of adjacent numbers

function greatestProduct(matrix) {
  let maxProduct = 0;

  for (let i = 0; i < matrix.length; i++) {
    for (let j = 0; j < matrix[i].length; j++) {
      // Horizontal product
      if (j + 3 < matrix[i].length) {
        let product = matrix[i][j] * matrix[i][j + 1] * matrix[i][j + 2] * matrix[i][j + 3];
        if (product > maxProduct) maxProduct = product;
      }

      // Vertical product
      if (i + 3 < matrix.length) {
        let product = matrix[i][j] * matrix[i + 1][j] * matrix[i + 2][j] * matrix[i + 3][j];
        if (product > maxProduct) maxProduct = product;
      }
    }
  }

  return maxProduct;
}

<br>

Bonus - Iteration #8.1: Product of diagonals

function greatestProductOfDiagonals(matrix) {
  let maxProduct = 0;

  for (let i = 0; i < matrix.length; i++) {
    for (let j = 0; j < matrix[i].length; j++) {
      // Diagonal to the right
      if (i + 3 < matrix.length && j + 3 < matrix[i].length) {
        let product = matrix[i][j] * matrix[i + 1][j + 1] * matrix[i + 2][j + 2] * matrix[i + 3][j + 3];
        if (product > maxProduct) maxProduct = product;
      }

      // Diagonal to the left
      if (i + 3 < matrix.length && j - 3 >= 0) {
        let product = matrix[i][j] * matrix[i + 1][j - 1] * matrix[i + 2][j - 2] * matrix[i + 3][j - 3];
        if (product > maxProduct) maxProduct = product;
      }
    }
  }

  return maxProduct;
}

<br>

Testing

Make sure to fork the repository.
Clone the repository to your local machine.
Implement the functions in src/functions-and-arrays.js.
Run npm install to install dependencies.
Run npm run test:watch to run the tests and check your code.
Once all tests pass, add, commit, and push your code:
bash


<br>

git add .
git commit -m "Solved lab"
git push origin master
Create a Pull Request for review.


By following this structured approach, you can methodically solve each iteration and ensure your code is working correctly by passing the provided tests.


  



  

