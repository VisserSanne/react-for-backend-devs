---
sidebar_position: 5
---

# Operators

## Comparison operators

In JavaScript you have two different comparison operators that seem similar but act slightly different.

### ==

The double equals (==) is a comparison operator, which transforms the operands to have the same type before comparison. This means that if you're comparing an integer and a string, it converts the string to an interger before comparing.

```js title="Shallow compare strings and numbers"
const operandString = "test";
const operandNumberOne = 1;

console.log(operandString == operandNumberOne); // false

const operandEmptyString = ""; // An empty string defaults to 0
const operandNumberZero = 0;

console.log(operandEmptyString == operandNumberZero); // true
```

### ===

The trippel equals (===) is a comparison operator, which does a deep compare with both the operands. This means it also does a type check.

```js title="Deep compare strings and numbers"
const operandString = "test";
const operandNumberOne = 1;

console.log(operandString === operandNumberOne); // false

const operandEmptyString = "";
const secondOperandEmptyString = "";
const operandNumberZero = 0;

console.log(operandEmptyString === operandNumberZero); // false

console.log(operandEmptyString === secondOperandEmptyString); // true
```

This doesn't make things more easy if you wanna (deep) compare an object though. In case of an object it doesn't compare each property but it compares the reference.

```js title="Deep compare an object"
const javascriptObject = {
    language: "JavaScript"
};
const identicalJavascriptObject = {
    language: "JavaScript"
};

console.log(javascriptObject === identicalJavascriptObject); // false
```

But rest assured! There are solutions for this! 🎉 🥳 We can find our saviour in a library called [lodash](../libraries#lodash). More on this later!
