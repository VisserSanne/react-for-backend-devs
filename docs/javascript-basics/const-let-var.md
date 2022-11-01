---
sidebar_position: 1
---

# Const, let and var
In every language you need a binding to define a variable, in JavaScript you have three.


## Const
Lets start with the most easy and most used one: const. This is a constant, the reference can never change. This means that if you for example have a constant string "Java-script" you can not overwrite it with "JavaScript".

```js title="You can not overwrite a constant"
const javascriptConstant = "Java-script";
javascriptConstant = "JavaScript"; ❌
```

If you wanted to say override a property on an object! Now THAT is something we can do with constants. The reference stays the same but the value of the property changes.

```js title="You can overwrite a property within a constant"
const javascriptObject = {
    language: "Java-script"
};
javascriptObject.language = "JavaScript"; ✅
```

### The scope
You will probably know this but I'll explain it anyway! The scope is the block of code where you can use a variable. This can be as small as an if block or as large as an entire code base depending on where you set it and how you define it.

For a constant this is usually the place you define it and the smaller scopes within that scope. Don't worry, I'll give you an example!

```js title="The scope for constants"
const doesThisWork = {
    inFunctions: false
};

function createNewScope() {
    doesThisWork.inFunctions = true; ✅

    const newConstant = {
        definedWithinFunction: "does this work"
    };
}

newConstant.definedWithinFunction = "nope!"; ❌
```


## Let
When you need a variable you also need to overwrite you should choose let. This can be used in the exact same way as const but the only difference is that you can overwrite it.


```js title="You can overwrite a let anywhere in the right scope"
let javascriptLet = "Java-script";
javascriptLet = "JavaScript"; ✅

function createNewScope() {
    javascriptLet = "JavaScript let"; ✅
}
```


## Var
Last but not least is the option that used to be the only option till ES6: var. Since const and let appeared we try to stop using var. The reason for this is why const and let were introduced to JavaScript: there are certain issues associated with variables decleared with var.

The scope for a var is the same as for constants and lets.

Now here is the tricky part: you can overwrite the var by either redeclaring it or overwriting it in the same fashion as let.

```js title="The scope for vars"
var javascriptVar = "Java-script";
javascriptVar = "JavaScript"; ✅
var javascriptVar = "JavaScript var"; ✅
```

Can you already tell where this can get confusing..? Let me show you.

:::info
We'll be using `console.log` in this example which is the way to log whatever you want in the console of the browser.
:::

```js title="The pitfall of vars"
var javascriptVar = "Java-script";

function createNewScope() {
    var javascriptVar = "JavaScript var"; 
}

console.log(javascriptVar); // "Java-script"

createNewScope();
console.log(javascriptVar); // "JavaScript var"
```

You can't clearly see if and when you're overwriting these vars. This can create a lot of unexpected results.

Lesson from this article: use const and let!
