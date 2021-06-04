# Steps to better code

_Isaac Lyman_

When you start out coding, you usually spend a year or two completely oblivious to the rules of "good code." You may hear words like "elegant" or "clean" tossed around, but you can't define them. That's okay. For a programmer without any experience, the main metric worth keeping tabs on is "does it work?"

Soon, though, you'll need to raise your expectations. Good code doesn't just _work._ It's simple, modular, testable, maintainable, thoughtful. Some of these terms may apply to your code without you even knowing it, but probably not. If you're lucky, your team carefully plans and architects its code solutions and guides you gently, trusting that you'll develop an intuition for well-written software. If you're not lucky, they [wince](https://xkcd.com/1513/) [or](https://xkcd.com/1695/) [complain](https://xkcd.com/1833/) every time they see your code. Either way, you can get a lot of mileage out of learning a few universal principles.

Take, for example, the _global variable_: a variable that can be used anywhere in the project. Suppose your app has a `username` variable that's set when the user logs in and can be accessed from any function in the app just by referencing the variable name---that's a global variable. Global variables are universally despised by bloggers and style guides, but most entry-level coders don't understand why. The reason is---and pay attention, because this is the reason for almost all best practices in coding---that _it makes the code faster to write, but harder to understand_. In this case, a global variable makes it really easy to insert the user's username into the app anywhere you want, which may mean fewer lines of code and fewer minutes until you finish your current task. That's false comfort, though: you've sacrificed safety for convenience. If you discover a bug involving `username`, you will have to debug not just a single file or function, but the entire project. I'll talk more about this later.

The difference between "good code" and "bad code" isn't usually based on the way it affects _you_ as you write it. Code is always a shared resource: you share it with other open-source contributors, or with the other developers on your team, or with the person who will have your job in the future, or with "future you" (who won't have a clue what "present you" was thinking), or even just with "debugging you," who is going through your fresh code looking for bugs and is totally frustrated. All of these people will be grateful if your code makes sense. It will make their job easier and less stressful. In this way, writing good code is a form of professional courtesy.

You may still be skeptical, but read on---I'll talk about several principles that lead to good code and try to justify each one.

### 0. Naming things

> There are only two hard things in Computer Science: cache invalidation and naming things.
> 
> ~ Phil Karlton

Well-written code tells a story, and is often readable even for someone who only has a passing familiarity with code. An important part of this is well-named variables, classes, files, and methods. When naming something, it's far more important to be descriptive than brief: a variable name like "elementarySchoolStudentLastNameFirstLetterRegEx" may have room for improvement, but it's much better than "b". It's useful to be able to know what something is immediately, right when you look at it, even if you haven't read the rest of the file or project. And that goes double for public fields and methods. Any element of code whose name doesn't fully communicate its purpose is one more thing you have to think about every time you use or modify it.

Beyond descriptiveness, _uniqueness_ is also valuable. Sometimes when modifying code, you'll want to do a project-wide search for a method or variable and find everywhere it's being used. In this situation it's best if its name is unique. If you've been calling things `method1` and `stringA`, your search results will be full of irrelevant stuff and it will be hard to make changes without breaking anything.

Renaming things is a great way to improve code quality as a junior developer. Make sure you know the naming conventions of your team and project---if they use underscores or capital letters to separate words, if they like to include a variable's type in its name, and so on---then find a couple of things with confusing names and suggest better ones.

### 1. [Separation of concerns](https://en.wikipedia.org/wiki/Separation_of_concerns)

A fair analogy for coding is writing a recipe. In simple recipes, each step depends on the one before it, and once all the steps are complete, the recipe is done. But if you've ever tried to follow a more complex recipe, you've probably experienced the stress of having two pots boiling on the stove, a plate spinning in the microwave, three kinds of vegetables half-chopped on a cutting board, and a smorgasbord of spice and herb shakers strewn across the countertop (and you can't remember which ones you've already added).

Having another cook in the kitchen complicates the problem as often as it simplifies it. You waste time coordinating, handing things back and forth, and fighting over stove space and oven temperature. It takes practice to figure out how to do it well.

If you know you're going to have several cooks in the kitchen, wouldn't it be more efficient for the recipe to be split into mostly-independent sub-recipes? Then you could hand part of the recipe to each cook and they could work with as little interaction as possible. One of them is boiling water for pasta. One of them is chopping and cooking vegetables. One of them is shredding cheese. One of them is making sauce. And the points of interaction are clearly defined, so each of them knows when to hand off their work.

The worst form of code is like a simple recipe: a bunch of steps in order, each written out in the same space, and listed from top to bottom. In order to understand it and modify it, you have to read the whole thing a couple of times. A variable on line 2 could affect an operation on line 832, and the only way to find out is to read the entire program.

A slightly better form of code is like having a second cook in the kitchen. You hand off some operations to other parts of the program, but your goal is mostly to make your files smaller, not necessarily to organize and simplify your code. It's an improvement, just not taken far enough.

The best form of code is like splitting a recipe into sub-recipes, usually called "modules" or "classes" in code. Each module is concerned with a single simple operation or piece of data. The vegetable chef shouldn't have to worry about the sauce ingredients, and the person cooking pasta shouldn't have to worry about the cheese grater. Their concerns are separated (hence the term _separation of concerns_).

The benefits to this are significant. Suppose a coder needs to modify the program later---to make it gluten-free for a client with celiac disease or to add a seasonal vegetable. That coder will only need to read, understand and modify one small part of the program. If all of the code dealing with vegetables is contained in a single small class with a few well-defined inputs and outputs, the coder never needs to worry that adding a vegetable will ruin the sauce.

The goal here is to make sure that, to make any given change, the coder has to think about as few parts of the program as possible, instead of all the parts at once.

### 2. [Global variables](https://en.wikipedia.org/wiki/Global_variable) (are bad)

Let's jump back to your `username` variable. When you built the login page for your app, you realized you'd need to display the user's username in a few other places, like perhaps the site header and the settings page. So you take the path of least resistance: you create it as a global variable. In Python, it's declared with the `global` keyword. In JavaScript, it's a property of the `window` object. It seems like a good solution. Anywhere you need to show the username, you just pop in the `username` variable and you're on your way. Why aren't all variables maintained like this?

Then things go sideways. There's a bug in the code, and it has something to do with `username`. Despite the availability of an instant search tool in most code editors, this is going to take a while to fix. You'll search `username` and there will be hundreds or thousands of results; some will be the global variable you set up at the beginning of the project, some will be other variables that also happen to be named `username`, and some will be the word "username" in a comment, class name, method name, and so forth. You can refine your search and reduce the amount of noise, but debugging will still take longer than it should.

The solution is to put `username` where it belongs: inside of a container (e.g. an object) that gets imported or passed as an argument to the classes and methods that need it. This container can also hold similar pieces of data---anything that's set at login is a good candidate (but don't store the password. Don't ever store a password without encryption). If you're so inclined, you can make this container immutable, so that once `username` is set, it can't ever be changed. This will make debugging extremely easy, even if `username` is used tens of thousands of times in your app.

Coding this way will make your life easier. You'll always be able to find the data you're looking for, in exactly one place. And if you ever need to track when a piece of data is used or changed, you can add some functionality to your object (like a _getter_ and _setter_---see Appendix A) and be on your way.

### 3. [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)

Suppose you're building a website that sells fancy hats. You build a page for the first hat and write the code for adding it to someone's shopping cart. You've got 24 more hats, so you build pages for them, then copy the shopping cart code from the first page and paste it into each one. Everything is working great. You make little modifications here and there: some of the hats have optional feathers or lace, others have a lot of color options. After a while, that shopping cart code doesn't look quite the same on any two pages.

Then you learn there's a bug in the original shopping cart code and it's making your customers upset. You need to fix it right away. And you realize you've made a huge mistake: since you copied and pasted the code from one page to another, you have to fix it 25 times, once for each fancy hat. You have to do it by hand, since the code is a little different on each page. That's going to take forever. You're up late rubbing your eyes and coding fix after tedious fix, and your customers are buying their fancy hats from competitors.

Ugh.

There's a better way: next time you build a website, don't be so quick to copy and paste. Write the code for the first page, then if you need some of that code in other pages, put it in a class method or a function and let each page refer to it, passing in arguments to handle any little differences between them.

DRY stands for "Don't Repeat Yourself." It's a good guideline to remember.

The goal is this: if an operation needs to change in some way, you should only have to modify a single class or method. This is quicker and far more reliable than trying to maintain several copies of the same code.

Don't take it too far, though---if two operations are really different, let them be different. Trying to force two distinct pieces of code into the same function can result in strange and confusing code.

Many programmers prefer the acronym WET, for "Write Everything Twice." That is, go ahead and copy something once, but if you find yourself with three copies of the same code, then it's time to refactor them into shared functionality. This is a very practical way to apply the spirit of DRY without overdoing it.

### 4. [Hiding complexity](https://en.wikipedia.org/wiki/Information_hiding)

Imagine I'm selling you a car. It will take some training for you to learn how to use it.

To start the car, take red wire #2 and white wire #7 and touch them together while kicking the engine-rev pinwheel with your foot and pouring an appropriate amount of fuel into the injector, which you'll find under the center console. Once the car has started, reach into the gearbox and push the layshaft into place against the first gear on the differential shaft. To accelerate, increase the flow of gasoline into the injector. To brake, hold your feet against the tires.

I'm sure this car frustrates you as much as it frustrates me. Now let's channel that angst toward code elements with over-complicated interfaces.

When you build a class or method, the first thing you write should be the _interface_: the part that a different piece of code (a caller) would need to know about in order to use the class or method. For a method, this is also called the _signature_. Every time you look up a function or class in API documentation (like on [MDN Web Docs](https://developer.mozilla.org/en-US/) or the [Python documentation](https://docs.python.org/3/)), what you're seeing is the interface---only what you need to know to use it, without any of the code it contains.

An interface should be simple but expressive. It should make sense in plain English, without expecting the caller to know about the order in which things happen, data that the caller isn't responsible for, or external variables.

This is a bad interface:

```javascript
function addTwoNumbersTogether(
  number1, number2, memoizedResults, globalContext, sumElement, addFn
) // returns an array
```

This is a good interface:

```javascript
function addTwoNumbersTogether(
  number1, number2
) // returns a number
```

If an interface can be smaller, it should be. If a value you're providing with an argument could be calculated from other values instead, it probably shouldn't be an argument (or the others shouldn't be). If a method has more than a few parameters, you should ask yourself if you're doing something wrong (although you might make an exception for some class constructors).

Don't take this too far. If you're setting and using global variables in order to avoid passing arguments to a function, you're doing it wrong. If a method requires a lot of different pieces of data, try splitting it out into more specific functions; if that's not possible, create a class or object specifically for passing this data around.

Remember that _all methods and data_ that are in a class but can be accessed from outside of that class are part of its interface. This means you should make as many methods and fields private as you possibly can. In JavaScript, variables declared using `var`, `let`, or `const` are automatically private to the function they're declared in, as long as you don't return them or assign them to an object; in many other languages, there is a `private` keyword. This should be your best friend. Only make data public on a need-to-know basis.

### 5. Proximity

Declare things as close as possible to where they're used.

Your instinctive urge to organize can work against you here. You may think an organized method looks like this:

```javascript
function () {
  var a = getA(),
  b = getB(),
  c = getC(),
  d = getD();

  doSomething(b);
  doAnotherThing(a);
  doOtherStuff(c);
  finishUp(d);
}
```

`getA()` and its compatriots aren't defined in this snippet, but imagine that they return useful values.

In a small method like this, you may be forgiven for thinking the code is well-organized and easy to read. But it's not. `d`, for some reason, is declared on line 5 even though it isn't used until line 10, which means you have to read _almost the entire method_ to make sure it isn't used anywhere else.

A better method looks like this:

```javascript
function () {
  var b = getB();
  doSomething(b);

  var a = getA();
  doAnotherThing(a);

  var c = getC();
  doOtherStuff(c);

  var d = getD();
  finishUp(d);
}
```

Now it's clear when a variable is going to be used: immediately after it's declared.

Most of the time the situation isn't so simple; what if `b` needs to be passed to both `doSomething()` and `doOtherStuff()`? In that case, it's your job to weigh the options and make sure the method is still simple and readable (usually by keeping it short and using more descriptive variable names than `a` and `b`). In any case, make sure you don't declare `b` until immediately before its first use, and use it in the shortest possible code segment.

If you do this consistently, you'll sometimes find that part of a method is completely independent from the code above and beneath it. This is a good opportunity to extract it into its own method. Even if that method is only used once, it will be valuable as a way to enclose all the parts of an operation in an easily understandable, well-named block.

### 6. Deep nesting (is bad)

JavaScript is known for an uncomfortable situation known as "callback hell":

```javascript
function getSumOfLetters(callback, errorCallback) {
  getA().then(a => {
    getB().then(b => {
      getC().then(c => {
        getD().then(d => {
          getE().then(e => {
            getF().then(f => {
              postSum([a, b, c, d, e, f]).then(
                sum => callback(sum),
                err => errorCallback(err)
              )
            })
          })
        })
      })
    })
  })
}
```

See that trail of `})` running down the last several lines? That's the calling card of callback hell. It's avoidable, but that's a subject that plenty of other writers have already addressed.

What I want you to consider is something more like "if hell."

```javascript
callApi(function(result) {
  try {
    if (result.status === 0) {
      model.apiCall.success = true

      if (result.data.items.length > 0) {
        model.apiCall.numOfItems = result.data.items.length

        if (isValid(result.data)) {
          model.apiCall.result = result.data
        }
      }
    }
  } catch (e) {
    // ignore errors
  }
})
```

Count the pairs of `{` curly braces `}`. Six, five of which are nested. That's too many. This block of code is hard to read, partially because the code is about to creep off the right side of the screen and programmers hate horizontal scrolling, and partially because you have to read all the `if` conditions to figure out how you got to line 10.

`try` and `catch` are keywords you may not have encountered yet. Any time an error occurs inside of a `try` block, it will immediately skip the rest of the block and jump to the following `catch` block to be processed. In this case, the `catch` block isn't doing anything, so we're ignoring errors completely. This is a bad idea because if something goes wrong, we have no way of knowing.

Now look at this:

```javascript
callApi(function(result) {
  if (result.status !== 0) {
    return
  }

  model.apiCall.success = true

  if (result.data.items.length <= 0) {
    return
  }

  model.apiCall.numOfItems = result.data.items.length

  if (!isValid(result.data)) {
    return
  }

  model.apiCall.result = result.data
})
```

That's a lot better. I removed the `try/catch` block, for starters (although it would have been equally good to properly handle and report the error). We can clearly see the "normal path" for the code to follow, and only in abnormal situations does the code stray off into an `if` block. Debugging is much simpler. And if we want to add extra code to handle error conditions, it will be easy to add a couple of lines inside those `if` blocks (imagine if the `if` blocks in the original code had `else` blocks attached! That would be so confusing).

### 7. [Pure functions](https://en.wikipedia.org/wiki/Functional_programming#Pure_functions)

A pure function (or functional method) is a function that does not alter or use external data (it's _stateless_). In other words, for a given input, it will always provide exactly the same output, no matter what has changed outside of it, and all your other variables will be completely unaffected by what happens inside of it. All pure functions have at least one argument and return at least one value.

This function is pure:

```javascript
function getSumOfSquares(number1, number2) {
  return Math.pow(number1, 2) + Math.pow(number2, 2)
}
```

And this one is not:

```javascript
function getSumOfSquares() {
  scope.sum = Math.pow(scope.number1, 2) + Math.pow(scope.number2, 2)
}
```

If you want to debug the first function, everything you need is right there in three lines of code. You can paste it into a separate environment, like [jsfiddle](https://jsfiddle.net/) or the browser console, and play with it until you find out what's wrong.

If you want to debug the second function, you may have to dig through the entire program in order to make sure that you've found all the places where `scope.sum`, `scope.number1` and `scope.number2` are accessed. And if you ever want to move the function to another class or file, you'll have to worry about whether it has access to all the same data.

Not all methods can be pure; if your application didn't have state, its usefulness would be limited. But you should write pure functions often. This will make your program easy to maintain and scale.

### 8. [Automated tests](https://en.wikipedia.org/wiki/Software_testing#Testing_levels)

An automated test is a piece of code that executes another piece of code and checks the results to make sure it's working. This is much faster and more reliable than trying to test every feature of the app on your own every time you make a change. Every major programming language has tools and libraries to help you write these tests. Some are called *unit tests*, which test a small, self-contained piece of code (like a class or method), and others are *integration tests*, which test the way different pieces of code interact.

Writing automated tests for your own code is considered an essential part of being an effective programmer. Any class or method that's more than a bare wrapper over other code---that is, any class or method that contains logic---should be accompanied by a unit test. That unit test should run automatically whenever your team merges code to the main branch.

Unit tests, properly written, weed out false assumptions and make your code easier to understand. If someone doesn't know what a piece of code does, they can look at the unit test and see use cases. Writing tests can be tedious, and there's such a thing as too many tests, but if you ever go into a task thinking, _wow, this one's tricky_, that's a sure sign that you should be writing tests along the way.

### Conclusion

Good code is a joy to maintain, build upon, and solve problems with. Bad code is painful to work with. Choose to write good code; you'll thank yourself for it.

A good question to ask yourself when writing code is: will this be easy to delete when we don't need it any more? If it's deeply nested, copied-and-pasted all over the place, dependent on various levels of state and lines of code throughout the program, and otherwise confusing, people will be unable to understand its purpose and impact and they'll be uncomfortable deleting it. But if it's immediately clear how it's used and what other code it interacts with, people will be able to delete it confidently when its usefulness runs out. I know you love your code, but the truth is that the world will be better off without it someday. And that's okay.
