{:: encoding="UTF-8" /}

# Appendix A: A coder's vocabulary

Following, in alphabetical order, are some terms that are commonly used among software developers. You may have learned some of them already. Note that these definitions aren't intended to be comprehensive, but rather to help you understand and participate in online and offline conversations about code as quickly as possible. Many of them are based on the most common situations and may not apply to every company or tool (e.g. the definitions relating to version control are specific to Git, the most popular version control system).

**Agile** - A philosophy for creating and releasing high-quality software gradually (as opposed to Waterfall, where software is delivered all at once). Even though the entirety of the Agile manifesto is available online ([https://agilemanifesto.org/](https://agilemanifesto.org/)) and takes less than ten minutes to read, most people in the technology sector severely misunderstand it or ignore it altogether. If a company says they "do Agile," this generally means that they have a lot of meetings and sell subscriptions to their products, not that they follow Agile principles like valuing simplicity and trusting their developers. Agile is one of the most popular buzzwords in the technology sector.

**Algorithm** - A set of steps for doing something. An algorithm is the concept that drives a piece of code, not the code itself.

**Antipattern** - Something that seems like an easy or obvious solution to a problem, but has hidden negative consequences. In other words, "lots of people do this, but it's a bad idea." Be wary of developers who use this to describe any pattern they dislike.

**Application Programming Interface (API)** - All the parts of a piece of software that are public in a given context - for example, if you're coding something that uses the software, the API is all the parts you can refer to from your own code. The commands in a programming language are part of its API. The methods you import from a third-party library are part of its API. If you write a web server, all the methods that can be accessed via an HTTP request are part of its API. In your own software, every public method and field you create is part of the internal API.

**Argument** - see "Parameter".

**Array** - A collection of one or more pieces of data, together in the same group. An array can be as simple as `[1, 2, 3]` or much more complicated---arrays can contain objects or even other arrays.

**Assign** - To set or change the value of a variable.

**Associative array** - See "Object".

**Asynchronous (async)** - Refers to processes that don't necessarily happen in order and could finish at any time (or not at all). Different coding languages handle this in different ways, but usually by letting you give them a function to execute when a process is finished, and another function to execute if the process throws an error.

**Automated test** - A piece of code that executes another piece of code and makes sure it does what it's supposed to do. Automated tests include unit tests, integration tests, and end to end tests, among others.

**Back end** - The server in a web application. This includes the database and all the server-side code. Many developers specialize in back end development.

**Best practice** - Any standard that a group of experts have decided is the "best way" to do something. Knowing the best practices of a programming language, framework, or business process can help you develop quickly and avoid expensive mistakes. It's also valuable to know when to ignore a best practice in favor of something that's faster or more practical.

**Big O notation** - A way of measuring the efficiency of an algorithm, like sorting an array or retrieving data from an object. In Big O notation, _O_ represents a function whose output is the amount of time (or space) it takes to run the algorithm, and _n_ represents the number of items the algorithm is operating on. Since every computer is different, we don't measure in absolute units, but for the following examples I'll use seconds. _O(n)_ could mean "this algorithm will take 1 second to operate on 1 item, 2 seconds to operate on 2 items, 3 seconds to operate on 3 items, and so forth." You can think of it as a line graph, like _y = x_. And _O(2n)_ would mean the algorithm will take two seconds to operate on each item. _O(1)_ would mean the algorithm takes the same exact amount of time regardless of how many items it operates on---this is usually the best case scenario. And _O(n^2^)_ would mean the algorithm takes as long as the number of items squared---this is one of the worst case scenarios, since the algorithm will get exponentially slower as the number of items increases linearly.

**Blocker** - Anything outside of your control that is preventing you from moving forward with your work. Blockers are a common topic of standup meetings.

**Branch** - One copy of a repository that can be worked on without affecting everyone else's copy. This is managed via version control. When you've finished doing a piece of work in a branch, you merge it back to the main branch (the "trunk"). "Branch" can also refer to a logical possibility in a piece of code---if a piece of code has an "if" statement, one logical branch is the code that executes if the statement is `true`, and the other logical branch is the code that executes if the statement is `false`.

**Boolean** - A data type that contains either `true` or `false`. A boolean variable is also called a bit or a flag. Booleans are one of the most essential and useful data types.

**Bug** - When an application doesn't behave the way it's expected to. This is almost always due to a mistake made by a developer while coding the application, or a miscommunication from their manager when describing the requirements for the application. On rare occasions it's due to a deficiency in the programming language itself. Bugs are common and developers learn to expect them in every piece of code. The term "bug" was coined by programming pioneer Grace Hopper, who once traced a malfunction in a computer program to an actual moth trapped in an electromagnetic relay.

**Build** - A compiled version of a codebase, or the process that compiles it and prepares it for delivery to the user or production server.

**Caching** - A way of speeding up access to data by storing it in memory. Generally, anything you assign to a variable in code is cached, and retrieving it from that variable is much faster than reading it from a database or a remote API call. Back-end developers tend to use caching liberally, since memory is cheap and cached data scales extremely well.

**Character** - A letter, number, symbol, space, or other indivisible piece of a string. Some programming languages have a specific data type for characters and represent strings as arrays of characters.

**Class** - The blueprint or instruction manual for an object. You can use a class to create an object, usually with the `new` keyword. The class tells you what data the object can hold and what methods it has.

**Clean code** - Code that has minimal dependencies and is easy to read, well-tested, and error-resistant. Truly clean code is a standard that isn't often achieved in the real world. The best developers strive for this ideal in a pragmatic way, improving existing code while making realistic compromises.

**Client** - In a web application, the computer on the user's side (as opposed to the server). Can also refer to an application that communicates with another computer over the internet.

**Cloud** - A general term for computers or servers that are owned by someone else and only accessible via the internet, usually paid for by the consumer on a monthly basis. Your emails and Dropbox files live in the cloud, as do most websites.

**Codebase** - All the code in a project or repository, or any collection of interconnected files that together form the source code of an application.

**Code quality** - A measure of the usefulness and readability of a piece of code. See the chapter "Steps to better code".

**Code review** - When one developer reviews another developer's code and provides feedback.

**Code smell** - A behavior in code that isn't necessarily wrong, but is an obvious red flag for low-quality code or hidden bugs. For example, a variable named `x` is a code smell, not because it doesn't work, but because it doesn't describe what the variable contains and could easily be misinterpreted.

**Code style** - A matter of preference in how code is formatted. Code style includes topics like tabs versus spaces, maximum line length, and bracket placement. Code style doesn't matter much but is still hotly debated on some teams. Ideally, a development team should set up an auto-formatter with rules chosen by any arbitrary method. As a developer, you should conform to the style conventions of whatever team or project you're working in.

**Command Line Interface (CLI)** - Often called a "console." A CLI is a text interface for using software. The user (often a programmer) types a command and presses Enter, and the software responds and puts the result on the next line. Bash, Powershell, Command Prompt on Windows, and Terminal on Mac are popular examples of CLIs.

**Commit** - See "Git".

**Compile** - To transform code into lower-level code, like turning C++ code into machine language. One way or another, this has to be done before the code can execute. Many programming languages come with a compiler that does this transformation quickly and efficiently. Compilation is often done ahead of time, before the software is released to users, but some languages have "JIT" (Just In Time) compilation that happens while the software is being used; still other languages are interpreted rather than compiled (See "Interpret"). Depending on the language and the environment it runs in, a combination of compilation techniques may be used.

**Concurrency** - When multiple things can happen at once in code.

**Constructor** - A class method that is called the moment a new object is created. The constructor is usually in charge of assigning default values to the object's fields and setting up its dependencies.

**Continuous Integration (CI)** - On a software development team, the practice of merging each developer's code to a shared repository frequently and testing it after each merge. Any CI tool on the market will allow you to automatically compile new code and run unit tests on it whenever it is merged, then notify the development team if the tests fail.

**Continuous Delivery (CD)** - The practice of making sure a piece of software is always ready to release, and releasing it frequently. This requires a little extra work to make sure that half-finished or untested features aren't released by accident. This can be done by hiding unfinished work behind feature flags or by releasing a feature gradually in small but fully-implemented layers.

**Convention** - Tradition. Programmers speak of "the conventional approach" or "style conventions," by which they mean "the way things have always been done around here." _Here_ in this phrase could mean your company, your city, a programming language, or the field of computer science as a whole. Sometimes conventions are a useful shortcut to code and techniques that have stood the test of time; other times, they're obstacles that prevent you from seeing a better way to do things.

**Create, Read, Update, Delete (CRUD)** - Some of the most common behaviors in interactive applications. A word processor app, for example, will have the ability to Create, Read, Update or Delete documents. An app with little to no logic other than what's required to store and retrieve data is often described as a CRUD app.

**Culture fit** - This can usually be understood as "someone who looks or talks like us." When a company's culture isn't well defined, this is too often used to shut out job candidates for personal reasons that have no correlation to competence or success in a given role. Using job interviews as a chance to communicate specific cultural values, such as teamwork, inclusion and tactfulness, can reverse these negative effects and produce "culture add" candidates who preserve a company's values while increasing diversity and reducing bias.

**Data** - Any piece of information that a computer can keep in its memory. Numbers, dates, strings, booleans, and objects are all examples of data.

**Database** - A set of data stored in memory, usually on a hard drive. Applications almost always have some kind of database where they store data they'll want to use later. For example, an app can store the name and email address of every person who signs up to use it.

**Dead code** - Code that is unreachable; that is, it can never be executed. For example, if a function is never called, or if code appears after a `return` statement, it's considered dead code. In some cases your IDE will automatically find dead code and bring it to your attention.

**Debugging** - Finding and fixing bugs in code. Bugs are very common. You should expect to spend far more time debugging code than writing it.

**Declare** - To give a variable a name (and possibly a type). A variable declaration is like a birth certificate for a piece of data.

**Dependency** - Anything that is required for a class to be constructed or for an application to run.

**Dependency injection** - The practice of passing a class's dependencies to it as parameters to the constructor, rather than making it responsible for gathering everything it needs. Dependency injection is a best practice in most programming languages and makes it easier to write unit tests.

**Deploy** - To move resources from one environment to another. Deploying software is a process that may include moving files to a server, compiling them, and running automated tests. Most companies automate this process to make it predictable and convenient. See also "Release".

**Design pattern** - A popular way to solve a particular problem in code. These often have odd names like "the decorator pattern" or "the adapter pattern". Sometimes language-specific patterns are called design patterns, but generally a design pattern should be applicable to an entire family or paradigm of languages. As you explore a codebase, you'll notice the patterns that exist in it without necessarily learning their names. It's more important to know what a pattern does and why it's useful than to know what it's called.

**Dev** - Short for "developer." Someone who develops software, including the work of writing code.

**DevOps** - An abbreviation combining "development" and "operations". DevOps describes the overlap between development tasks---defining and creating a product---and operations tasks like deploying software to an environment. Someone who works in DevOps will generally have experience in both areas.

**Dictionary** - See "Object".

**Diff** - The result of running a "diff tool." A diff tool is a piece of software that compares two code files and displays the differences between them, much like the "View Changes" tool in a word processor. Code that was added will be shown in green and/or with a "+" symbol, while code that was removed will be shown in red and/or with a "-" symbol. Diffing is often done while merging code, to make sure that changes made by different developers are all integrated together correctly.

**Documentation** - Written instructions, descriptions, or historical records related to a team or a piece of software.

**Edge case** - Something that's unlikely to happen in a particular application, but should be planned for anyway. For example, the user of an email application could decide to forward an email to themself, and while this isn't something most users will ever do, the application should still be able to handle it without breaking.

**Elegant** - Code that is well-written, even beautiful. If two pieces of code do the same task and are both performant and bug-free, the more elegant one is the one that is easier to understand or makes better use of the programming language and its standard library. Calling someone's code "elegant" is a compliment. Elegance shouldn't be confused with "cleverness," which can sometimes mean using language features in a confusing way to get shorter or faster code.

**Encapsulation** - Taking data and logic that belong together and putting them in a self-contained unit of code. This makes it easy to hand them out to any code that wants to use them, and to control the way they are used.

**Encryption** - The use of a secret cypher to make important data difficult or impossible for hackers to read.

**End to end (e2e) test** - An automated test that runs an application as if it were a real user, including clicking, tapping, typing, scrolling, or anything else a real user might do. These tests are time-consuming but they're also the only way to ensure the application actually works without testing it manually. For that reason, they tend to provide a lot of value.

**Estimating** - The practice of trying to guess how long it will take to develop something. These guesses are usually wrong. The more specific a guess is, the less accurate it's likely to be. Nonetheless, managers desperate for control will often try to get developers to give highly specific estimates for all their work.

**Evaluate** - To execute a piece of code. If the code produces a value, we can say the code "evaluated to" that value.

**Expression** - A piece of code that produces a value. Expressions can be made of smaller expressions. The number `2` is an expression in code, as is `120 / 1 + 1` and `getUserData()`.

**Feature flag** - A boolean value that determines whether a feature is visible or usable to the end user. This is useful when a feature isn't finished yet but the current latest version of the code needs to be released. It can be as simple as placing a piece of code inside an `if` block, or as complex as using different data types across multiple files based on a value in a database.

**Flag** - See "Boolean".

**Foo, bar, baz, qux** - Generic, meaningless variable names often used in code samples or documentation. They're equivalent to `a`, `b`, `c`, and `d`. They shouldn't be used in actual application code.

**Framework** - A generic piece of software that makes certain common tasks easier; this is meant to be used as the foundation for an application. A web framework, for example, can simplify the work of creating websites by providing methods for updating web pages when data changes, sharing data between pages, and communicating with a web server.

**Front end** - In a web application, the code that runs on the user's computer (generally a website or an app). The opposite of "back end." Many developers specialize in front end development. Front end development often includes elements of graphic design.

**Full stack** - Both the front end and the back end in a web application. The term "full stack developer" is contentious because many people believe that a developer can't effectively specialize in both the front end and the back end. However, most web developers know some of both.

**Function** - One or more lines of code that are grouped together in the same block and share data with each other. A function usually has a name so you can call it from another piece of code. Functions can accept arguments and return values (but they don't have to do either). They're a good way to break down a long process into simpler steps or share logic between several pieces of code.

**Functional programming (FP)** - A paradigm that describes programming languages or techniques where all data is immutable, all functions are pure, and the core concepts are based on advanced math. Haskell, Elm and F# are examples of functional programming languages. However, a functional programming "style" can be used in many other languages, including JavaScript and C#.

**Garbage collection (GC)** - A feature in many programming languages that keeps track of data you aren't using anymore and automatically deletes it to free up memory. This is a major convenience for developers. In languages without garbage collection, you have to keep track of all your data and delete it yourself to avoid memory leaks.

**Getter** - A function that controls what happens when a variable is accessed. Getters are sometimes used to control who can access a variable and what value they receive. The code referring to the variable probably doesn't know that it's calling a function, so getters should be used carefully. See also "Setter".

**Git** - The most popular version control system. Git keeps track of a series of "commits," each of which is a collection of file changes or "deltas." These commits exist in one or more "branches". When one branch is merged into another, Git tries to take all the changes in each file and weave them together. It often can't figure out how to do so without losing anyone's changes; this results in merge conflicts.

**Gotcha** - A pitfall. Anything about a programming language, library, design pattern, or apparent solution that can have unexpected effects, often without the developer realizing it.

**Hard-coding** - When data is written into code as a shortcut, forcing the code to use that data instead of getting it from whatever "real" source it's supposed to use. This is a form of technical debt. It's often done on purpose when building a new app or feature. For example, when you build a new web page, you might hard-code some fake data for it to display (like a username, profile picture, and map location) so you can focus on the design and interface. Every time you load the page, the same fake data will be shown. Once the design work is finished, then you'll need to refactor so that the page uses data from a real logged-in user, maybe by fetching that data from the application's server. Hard-coding can also be called "stubbing."

**Graphical User Interface (GUI)** - A visual interface for using software, generally accessed with a mouse and keyboard. Ubuntu Linux, Mac OS, and Windows all come with GUIs installed, as does every major internet browser and almost every other application meant for end users.

**Idempotent** - Describes a method that can be called once, twice, or multiple times, and the result is always the same---that is, it doesn't matter how many times you call it.

**Idiomatic** - The most obvious or normal way to do something in a programming language. Idiomatic code takes advantage of a language's built-in features and standard library to complete a task in an expectable way, rather than writing unnecessary methods or misusing language features to do something they weren't intended for.

**Immutable** - Refers to data that can't or shouldn't be altered. A changed version of that data could be created and stored in a different variable, but the original data should always stay the same. Immutable data can be nice to work with because it's unlikely to surprise you.

**Infinite loop** - A loop, such as a `while` or `for` loop, that has a bug causing it to repeat forever. This often happens when the programmer forgets to increase a value on each iteration, or when the condition of the loop is written incorrectly. `while(true) {}` is an example of an infinite loop.

**Integrated development environment (IDE)** - A code editor that includes code-specific features, like a compiler, a test runner, a debugger, and/or autocomplete. Visual Studio, IntelliJ, and WebStorm are examples of IDEs.

**Integration test** - An automated test that makes sure two or more pieces of code work together correctly.

**Interface** - The way you interact with a piece of code. This can refer to the input boxes and buttons of a Graphical User Interface, the hardware buttons on a microwave, or the public parts of a class. In code, the _interface_ keyword is used to describe a collection of public fields and method signatures which describe the interactivity an object is expected to have without specifying the exact logic it should be using under the hood.

**Interpret** - Refers to the process of executing code without compiling it to machine language first (see "Compile"). This requires a special piece of software called an interpreter. Languages that are interpreted instead of compiled are often called "scripting" languages. JavaScript is an example of an interpreted language; every major web browser comes with a JavaScript interpreter.

**It works on my machine** - Often said by a developer when an application is broken for the QA team, managers, or users, but doesn't seem to have any issues when they run it on their computer. There are many reasons this can happen, including out-of-date code, a race condition, concurrency bugs, differences in data, differences in environment, unforeseen user behavior, or bugs in the build and delivery system.

**Kanban** - A set of processes that are often used in software development. Kanban is most easily recognized by the presence of a "Kanban board," a grid representing tasks that are available, in progress, or finished, often with intermediate steps in between. See also "Scrum" and "Agile".

**Keyword** - See "Reserved word".

**Legacy code** - Any code that no longer brings joy to the developers that maintain it. Legacy code may have been written ten years ago or last week; the point of the phrase isn't necessarily to describe the code's age, but to indicate that it's obsolete in some way and needs to be updated.

**Library** - See "Package". Can also refer to a collection of related packages.

**Linter** - A tool that detects style issues or common mistakes in code without actually compiling or running it. Linting is a form of static analysis.

**Load test** - An automated test that simulates heavy usage of an application (e.g. by a lot of different users at the same time). The goal is to measure the performance of the application "under load," or in other words, to find out how much it slows down or stops working in worst case scenarios.

**Logic** - What an application does or how it makes decisions.

**Memory** - See "Random access memory".

**Memory leak** - When an application fails to free up memory it doesn't need anymore, it can gradually use more and more memory until the computer runs out. This can happen in any programming language, whether or not it has garbage collection.

**Merge** - See "Git".

**Merge conflict** - When two developers have modified the same code and the version control system can't figure out how to weave their changes together, the result is a merge conflict. A developer then needs to resolve the conflict, usually by opening the file and modifying it so neither developer's work is lost.

**Method** - A function that lives inside of an object. It's often defined in a class.

**Minimum viable product (MVP)** - The smallest and simplest version of a software product or feature that could be valuable to a user. Releasing an MVP is a good way to find out what's important to users and learn about their needs without a lot of development effort.

**Mob programming** - Often called "mobbing". When more than two developers gather around a single computer and focus on a single task, with the entire group contributing to discussion about how to do it.

**Mock** - A "fake" version of a dependency (like an object or method) that can be used during unit testing, so the test won't fail for reasons outside of the piece of code being tested.

**Mockup** - See "Prototype".

**Modular** - Refers to a piece of code that is self-contained, making it portable between codebases.

**Module** - See "Package".

**Monitoring** - Use of a system that keeps track of different events and metrics for an application. You can use monitoring to learn what kinds of errors are happening for your users or how fast or slow your app is. Monitoring can also notify you when a server crashes or a database takes too long to perform an operation.

**Mutable** - Refers to data that can be altered. The opposite of immutable.

**Namespace** - A name that groups one or more pieces of code together under the same umbrella for the programmer's convenience. Some programming languages require every class to be in a namespace. When one class refers to another, you can use its namespace to help the compiler find it, or to differentiate between multiple classes with the same name.

**Object** - A piece of data that holds other pieces of data and/or logic. Organizing data like this is a good way to describe a complicated real-world concept, like a person or a subscription. Objects are usually organized into keys and values. The keys are like words in a real-life dictionary; the values are like the definitions of those words. Therefore, you use the keys (which you usually know beforehand) to retrieve the values from the object or to change them. An object can be created by using a class. Objects can also be called dictionaries or associative arrays.

**Object-oriented programming (OOP)** - A paradigm that describes programming languages where the code is organized around mutable data objects. OOP languages generally use classes and each class has methods for operating on its own data.

**Open source** - Describes a project or application whose code is publicly available. Open source coding is extremely popular, and tens of millions of open source repositories can be found on sites like GitHub and BitBucket. Developers value open source code because of the communities that form around it, the way it propagates ideas, the transparency it offers, and the fact that most open source code is free to use.

**Package** - A bundle of code intended to be used by other code. A package may depend on other packages, but it usually handles those dependencies on its own. In the simplest situations, you can add a package to your project and use it without worrying about how it works.

**Pair programming** - When two developers share a computer. One of them, the "driver", controls the mouse and keyboard; the other one tells them what to do or type. The goal is to reduce mistakes and increase development speed by having two people focused on the same task.

**Paradigm** - A category of programming language, or a certain way of programming regardless of language. Functional programming and object-oriented programming are examples of paradigms.

**Parameter** - A piece of data you provide to a function when you call it. It's assumed that the function will use and/or alter that data.

**Performance** - How fast or slow an application or part of an application is. Something that's relatively fast is called "performant."

**Premature optimization** - When someone tries to make an application faster without knowing how fast it is already. Most of the time, "fast enough" is good enough. Almost any piece of code can be fine-tuned and worked over until it's lightning-fast, but this is wasted effort if a user will never notice the difference.

**Primitive** - A simple, "pure" data type that isn't an object. What's considered a "primitive" can vary by programming language. Numbers, booleans and characters are usually primitives.

**Production** - In a web application, the server that is interacting with real users. This is the last stop for any piece of code that's been merged into the main branch.

**Proof of Concept (PoC)** - A small example of working software to demonstrate that a particular idea or technique is feasible.

**Prototype** - An application design that represents both the appearance and the interactivity of the app, usually put together by a designer. Usually a prototype is purely visual and doesn't contain any code or do any work under the hood.

**Pseudocode** - Fake code written as an example or to describe how an algorithm might be written. Pseudocode may look like a specific programming language or no programming language at all. Many programmers like to write pseudocode when planning their approach to a problem, so they can figure out the solution without worrying about syntax, spelling, code style, and errors.

**Pull request (PR)** - In version control, a proposal for one branch to be merged into another. A pull request usually includes a written description of the changes the developer has made and a list of all the commits that would need to be applied. Most online code repositories have a way to read through all the code changes that a pull request is proposing, and a method for approving or rejecting the request.

**Pure function** - A function that doesn't change anything outside of itself and doesn't use any data aside from its arguments. A function that accepts a Fahrenheit value and returns the equivalent Celsius value, doing the conversion with a simple mathematical formula, is an example of a pure function. Pure functions are easy to use and very predictable, which makes them a useful tool for any developer.

**Quality assurance (QA)** - Testing software to find bugs. Depending on the organization, this can be a person or team's full-time job, or a responsibility shared by everyone. It's an extremely valuable role that often prevents catastrophic bugs from affecting users.

**Race condition** - A bug that occurs when two or more things happen at the same time and are expected to finish in a certain order, but might not. Race conditions are common in asynchronous code and in web applications that expect data to be delivered from the server in a particular order.

**Random access memory (RAM)** - Often just called "memory". The place where the computer stores data temporarily. RAM is very fast and easy to access. All variables in a computer program are stored in RAM.

**Read--eval--print loop (REPL)** - See also "Command Line Interface". A text interface for evaluating expressions in a programming language. Most languages ship with a REPL. The developer console in Chrome, Firefox and Safari includes a JavaScript REPL.

**Read the fucking manual (RTFM)** - An abusive way to suggest that someone is asking an excessively simple question, and instead of bothering you they should read the documentation for the programming language or tool they're struggling with. RTFM is an unhelpful response regardless of the situation, and generally only used by people who are exceptionally difficult to work with.

**Recursion** - When a function calls itself. This is often done when a function is working with data like an array or tree of indefinite length or depth. The function can operate on the first part of the data, then call itself with the rest of the data. Eventually it will be called with the last piece of data, and then it can finish.

**Refactor** - To change a piece of code without changing how the application behaves on the surface. The purpose of refactoring can be to make code easier to read, to organize it better, to make it easier to add new behavior in the future, or to take advantage of new features in a programming language or library.

**Reference** - The memory address of a variable. When you create a variable and use it, the code is keeping track of its reference (usually behind the scenes). If you delete the variable or the compiler notices you're not using it anymore, it can "free" the reference so that memory can be used by something else. If something is "passed by reference" to a function, that means its actual memory address is provided, so modifying it within the function will modify it for the entire application.

**Reflection** - The ability of code to modify itself at runtime. In practical terms, this usually refers to the ability in certain programming languages to look at an object and access any of its fields and methods that are created at runtime or would usually be hidden. This is especially useful if you don't know what the object is going to look like ahead of time.

**Relational database** - A database consisting of tables that can refer to each other. You can think of a database table like a spreadsheet. It commonly has an ID column and other columns that describe a complex piece of data; in this way the table definition (or "schema") is like a class and each row is like an object of that class. If you have a table called "Orders" and a table called "Products", the "Orders" table could have a "ProductID" column that refers to the ID column of "Products". Then each order could be related to a product (usually by using the numerical ID of a single row). Relational databases are the best choice for most applications. Most relational databases are created, queried and updated via SQL, a programming language made for this purpose.

**Release** - To publish code to an environment, usually production; or, a version of code that is ready to be released.

**Repository** - A collection of files that are all kept in the same place. Often abbreviated to "repo".

**Reserved word** - In a given programming language, any word that has special meaning and therefore can't be used for variable or function names. For example, the word `if` is usually a reserved word, and if you try to declare a variable named `if` you'll get an error.

**Representational state transfer (REST)** - By strict definition, this is a set of rules for web server APIs that dictates, among other things, how APIs are structured and what information the client must provide. In common usage, a REST API is any web API that uses common HTTP request bodies and HTTP verbs like GET, POST and PUT.

**Retrospective** - A meeting during which developers and managers consider the work they've done recently and discuss ways to improve. This is the only meeting that is actually part of Agile: "At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly." ([https://agilemanifesto.org/principles.html](https://agilemanifesto.org/principles.html))

**Rollback** - A process by which a piece of software is "un-updated"; any changes in the latest release are undone and the software reverts to an older state. This is usually done when a severe bug or security flaw that didn't exist in previous versions is discovered. Software companies generally plan for this possibility by (for example) setting up an automated way to do a rollback with a single click.

**Rubber ducking** - The practice of explaining a problem to an inanimate object (it's called a "rubber duck" for illustrative purposes). As you describe the issue out loud in your own words, the solution will often become obvious. This is an especially effective tool for debugging.

**Runtime** - The time during which the code is actually running (not being written or compiled); or, the environment in which the code runs.

**Scaling** - A set of strategies and considerations around the question, "how could our application or organization handle a significant increase in the number of customers we serve?" Scaling can also refer to challenges with increasing amounts of data or organizational growth.

**Schema** - See "Relational database".

**Scope** - The boundary between what you intend to build and what you don't intend to build. If you're planning to build a feature in a certain period of time, that feature is "in scope." Otherwise it's "out of scope." If you've already made plans but extenuating circumstances cause you to do more work than you were planning, that's called "scope creep."

**Scrum** - A set of meetings and processes that are a popular way to "do Agile." The most common mark of Scrum is the "standup", a daily meeting where members of a team report what they're working on. Some organizations wrongly believe that they are Agile solely because they have sprints and standup; see "Agile".

**Setter** - A function that controls what happens when a variable is changed. A setter can be used to track changes to a variable, prevent it from being changed, or determine if the user has permission to change it. The code referring to this variable probably doesn't know that it's calling a function, so setters should be used carefully. See also "Getter".

**Ship** - To release a version of a product, usually the latest version.

**Signature** - Everything you need to know in order to use a method: its name, the types of arguments it expects, and what type of argument it returns.

**Soft skills** - Refers to non-technical skills that are essential in the workplace, like communication, respectfulness, compromise, time management, and creativity. The phrase has some unfortunate connotations, like wrongly implying that "soft" skills are less important than "hard" (technical) skills, or that they're a sign of intellectual weakness. Many programmers prefer to call them "catalytic skills," since they enable and facilitate every kind of work.

**Software** - Applications built with code that run on a computer.

**Software as a Service (SaaS)** - A way of delivering software on a subscription basis. Customers usually pay monthly and receive regular, automatic updates. SaaS is a popular way to sell software on the internet.

**Software development kit (SDK)** - The software and APIs necessary to develop an application that works on a particular platform, like Windows 10, iPhone, or the Java Virtual Machine (JVM).

**SOLID** - An acronym for five principles that are common in the study of object-oriented programming: Single responsibility principle, Open-closed principle, Liskov substitution principle, Interface segregation principle, and Dependency inversion principle. These aren't defined here because some of them are relatively advanced, but you should study them once you feel confident with the basics of object-oriented programming.

**Spaghetti code** - Code that is disorganized, spread out, and hard to follow, as if the code were noodles in a bowl of spaghetti. Developers who are in a rush to meet deadlines or don't have the guidance of a senior developer will often produce spaghetti code. An application made of spaghetti code is a nightmare to debug, refactor, and build upon. Be wary of developers who use the term to describe any code they dislike.

**Specification** - A detailed human-language description of a software or programming language feature, including details on how it works and how to use it.

**Sprint** - A period of time during which software is built. The Agile principles state, "Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale" ([https://agilemanifesto.org/principles.html](https://agilemanifesto.org/principles.html)). Sprints are a popular implementation of this principle. A sprint often begins with a planning meeting and ends with a retrospective.

**Stack** - A memory structure where pieces of data are "stacked" on top of each other. Only the top piece of the stack can be accessed or removed at any given time. The "stack" also refers to all the lines of code that are active when a specific line of code is executed. If code A calls code B, which calls code C, then A, B and C are all part of the stack. If C throws an error, you'll usually see a "stack trace" listing C, then B, then A.

**Staging** - The environment where an application is released before it goes to production. Staging is where all the final testing and verification happens and often has similar data to production. If a bug isn't caught in staging, it will go to production and affect users.

**Standard library** - All the functionality that comes built-in with a programming language, even though it isn't part of the syntax itself. The standard library usually includes functions for manipulating strings, handling input and output, and doing advanced math.

**Standup** - See "Scrum".

**State** - The data kept in memory as an application runs.

**Statement** - A basic unit of code that describes an action. In programming, we often talk about "if statements," "return statements," and several others. An "if statement" is a statement that uses the `if` keyword, such as `if (x == 2)`.

**Static** - A keyword in many programming languages that refers to a method or field that exists on the class itself, not on objects of that class.

**Static analysis** - A type of debugging that can be done without compiling or running the code. Linting is a form of static analysis. Most IDEs will do static analysis to let you know about bugs as soon as possible.

**String** - A data type that holds text. In code, strings are usually put inside of quotes. `"John Smith"` is a string, as is `" "` (a string full of spaces), `""` (an empty string) and `"😂"`.

**Style guide** - A set of rules documenting a group or project's preferred code style. Some teams have unwritten style guides; in this case, the best thing to do is explore the project beforehand and try to make your code look like theirs.

**Syntax** - The grammar of a programming language, including all its reserved words and the way numbers, symbols, and other tokens are used.

**Technical debt** - The gradual buildup of confusing, disorganized or buggy code in an application. This is inevitable over time, especially if the team is rushed, the work environment is hostile, or there's a lot of pressure to produce new features. Technical debt can only be controlled by regularly setting aside development time to refactor. If technical debt is allowed to grow too large, it can cause mental exhaustion for developers, seriously slow down feature development, and make bugs hard or impossible to fix.

**Test-driven development (TDD)** - The practice of writing unit tests for a piece of code before that code is even written. The process can be remembered as "red-green-refactor": first the test is written, and it fails (red) because no code has been written. Then code is implemented so that the test passes (green). Then the code can be refactored to improve quality.

**Throw** - If a piece of code runs into an error it can't or shouldn't handle on its own, it can throw the error (or do nothing, in which case the error will usually be thrown automatically). Then the code that called it will receive the error. That code can also handle, throw, or ignore the error. If the error is thrown enough times, it can reach the user.

**Type** - The kind of data stored in a variable, e.g. a whole number, a decimal number, a boolean, a string, or an object.

**Unicorn** - A privately-held tech company whose total stock value is over one billion dollars. Sometimes this word is also used to indicate something incredibly rare and precious, like certain types of developers.

**Unit test** - An automated test that makes sure a single, isolated piece of code (like a class or method) does what it's expected to do. Unit tests usually run very quickly and can help build confidence in a tricky piece of code. The best unit tests verify a unit's behavior, not its implementation---that is, they test _what_ it does, not _how_ it does it. This way the code can be refactored without breaking the test.

**Usability testing** - The practice of having someone (usually a person from outside of the team or company) use an application or prototype while a member of the team watches. Ideally, the team member shouldn't tell the person _how_ to do anything; instead, they should give them an objective and see if they can figure out how to complete it in the application. This helps the team understand what parts of the application are confusing or unintuitive.

**User interface (UI)** - The part of an application that a user looks at and interacts with; or, the work of designing this part of an application, often done by a graphic designer or someone with artistic training.

**User experience (UX)** - The field of study focused on improving the interactions between users and applications. UX designers may build prototypes or design interfaces, but they're generally more concerned with usefulness and user-friendliness than with appearance.

**Value** - A piece of data. If we say something is "passed by value" to a function, then we mean the data itself is provided, not the memory address of the variable that holds it. This way the function can modify it without affecting the rest of the application.

**Variable** - A named piece of data in memory. In the statement `int x = 1`, the variable is `x`.

**Velocity** - A measure of development speed based on estimates. Velocity is generally impossible to measure in a useful way. Incompetent managers often try to increase velocity by making developers work longer hours and meet shorter deadlines; this always results in a worse product and long-term damage to the company.

**Version control system (VCS)** - A system for managing several different versions of a codebase. Usually there is a main or "master" branch which contains the latest and most official version of the code, and then several other branches containing work in progress. These other branches can be merged into the master branch when they're complete.

**Vulnerability** - A weakness or bug in an application that hackers could use to steal user data, crash the application, or gain unauthorized access. Vulnerabilities can be avoided through the use of security best practices, encryption, input sanitization, and penetration testing.

**Waterfall** - A development process for software that is delivered all at once, like on a CD. This was popular in the days before the internet became the primary medium for software distribution. In Waterfall, planning and design are all done at the beginning of the project, which can make the process inflexible and prone to error.

**Whiteboard interview** - A popular but ineffective interview method where candidates are asked to write code on a whiteboard, chalkboard or sheet of paper. This often includes asking them to solve complex mathematical or data structure problems with code. Since this doesn't resemble the work they'd be doing on a day-to-day basis if they were hired, it's almost irrelevant to the task of selecting the most competent candidate.

**Workaround** - A less-than-ideal way to work when some issue makes the normal way impossible. If the "Send" button on your email client is broken, but pressing Ctrl + Enter sends the email, that's a workaround. You can continue to use the software, but it definitely needs to be fixed.

**XY Problem** - When a user has a problem ("X"), thinks they know the solution ("Y"), and asks for help with that solution ("Y") instead of the original problem ("X"). People sometimes do this to avoid looking naive ("I have a problem but no idea how to solve it" can be a hard thing to say), or because they think asking about Y is a smaller or less intrusive question. Sometimes they may not even recognize that X is their real problem. This often results in confusion and frustration, especially when the user's Y isn't a good solution to X (or isn't even related to it). For example, suppose your computer won't turn on and you decide---for good reasons or bad ones---that the problem is the power cord. You might call a friend who's good with computers and ask them where to buy a new cord. If you're lucky, they'll ask some broader questions and find out what's really going on. If not, you may find out the hard way that a new cord doesn't solve the problem, and lose a lot of time and money in the process.
