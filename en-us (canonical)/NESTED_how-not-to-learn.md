# How (not) to learn

_Vlad Levin_

![](images/nested_book.jpg)

_Image licensed by [Pixabay](https://pixabay.com/es/illustrations/narrativa-la-historia-sue%C3%B1o-decir-794978/)_

When I was younger, I remember having some odd ideas about what it meant to learn. In particular, I recall that I thought learning meant reading a textbook very diligently from beginning to end. I would even read the foreword. Maybe that was just me! Now I look back and wonder why I had such strange and unproductive notions.

However, I think the education system at every level does tend to suffer from problems that prevent people from learning effectively: students are shepherded through too many subjects at a time and learn the material in a linear and rote manner. As a result, I think it's not uncommon for people to promptly forget much of what they "learned" in school, including at colleges and universities, as soon as they pass their exams.

The following are some heuristics I've built up over time which have helped me when I'm learning something new. If you have the luxury of learning something on your own, consider trying these out. Even if you're in school, I hope some of these ideas may be of help if you actually care about learning instead of just getting through the classes.

### Build intuition

With almost any technical subject, it's easy to get involved in all of the complicated details. Doing so prematurely can be a bad idea though. If we don't understand the broader context, those technical details can quickly overwhelm us.

When you're first reading about a given topic, try to grasp the big picture. Why is this important or useful? How does it fit with other topics or technologies? What's the problem that it's trying to solve? Is there another way to look at this? Answering questions like these will give you a perspective that will help motivate a deeper understanding as you dig into the more technical details.

Building intuition is a gradual process. Often clues can be found sprinkled through a given book or other source of information. Keep an eye out for the clues and use them to build up a picture in your mind of the high level principles and connections. Always keep asking yourself: "What's the big idea here?"

Intuition is something everyone works on, from novices to experts. As a novice programmer, I remember learning C for the first time. At first I had difficulty understanding the starting and ending conditions of `for` loops, e.g. `for (int i=0; i<length; i++)`. I distinctly remember making notes in a notepad, manually tracking the value of `i`, as well as sketching an array with arrows pointing to the current index during and after each iteration. Eventually it became second-nature, but I still remember that it wasn't obvious to me in the beginning.

Later on, I used similar strategies to get familiar with increasingly complex recursive algorithms. I would work through small examples manually. Again, I drew small sketches, showing everything on the stack before and after each recursive call. This helped me to internalize what was really going on with a given algorithm.

Here's another real-world example of building intuition: fairly recently I needed to look up the formula for standard deviation in statistics. It wasn't my first time using it, but this time I suddenly noticed that part of the formula looked a lot like the Pythagorean theorem. That had never occurred to me before. I was able to work out that the standard deviation can be thought of geometrically, in terms of the distance between two points. This was very exciting for me. Before, I had always taken the formula for granted, as a black box. I knew how to use it, but I didn't know why the equation was what it was. Afterward, I felt that I understood it much better. I could visualize what was happening, and I knew that from now on, it would be easy for me to derive the formula from scratch.

Once something becomes intuitive, you can visualize it, you know when it applies and how it works, without needing to consciously think about it.

### Knowledge debt

In the same way that there's financial debt and technical debt, there's also knowledge debt. If we're faced with something we don't understand, often the temptation is to move ahead anyway, hoping it won't bite us later. In fact, sometimes that's okay. Maybe an in-depth understanding isn't necessary---we just need to get a specific thing done. Or maybe going further into the material will elucidate the point we're stuck on right now.

Both of these things can be true at times, but it's not a good approach to leave behind such gaps as a matter of course. It will cause the foundations of our knowledge to get more and more shaky. Eventually, that's precisely what will stall progress completely. For instance, a lot of people think math is "too hard." I believe the reason is that they kept being pushed along in school to more advanced topics, but all the while they were leaving more and more loose ends behind.

Any technical subject, including math, computer science, and programming, requires effort (at least for us mortals), but if you take it one step at a time, and you make sure to master the individual steps along the way, you can go a lot further than you might think.

### PDL: Problem-Driven Learning

Just as test-driven development (TDD, see below) is about writing code to satisfy a measurable criterion---making a test pass---I like applying the same notion to learning. Learning can seem like a passive process of osmosis. However, we're fooling ourselves if we think we understand that way. It's okay to read something lightly to get a broad overview of a topic, but if we really want to understand how to apply our knowledge, _we should make the learning a result of solving problems_. This is the best way to make the leap from theory to practice.

We can start with a simple problem and learn just enough to solve it, kind of like making a test pass in TDD. Moving on to a similar, maybe slightly harder problem, can we solve it without doing any extra reading? If so, great. Otherwise, we go back over our material to find what we need. This makes our reading much more active and goal-oriented.

The more problems we can solve and the more diverse those problems are, the stronger and more concrete our understanding becomes. This is the only real measure of how well we understand something.

> **What is TDD?** Test-Driven Development, or TDD, is a practice that's used to improve the quality of new code. The idea is to develop functionality in small steps. Each step starts with a _unit test_ (see Appendix A, "Automated test" and "Unit test"). Each test has 3 parts. The first part describes the initial conditions for the test. The second part describes the action to be taken by the test. The third part describes the changes that are expected as a result of the action.
>
> After you've written a test, you start things off by running it. It's good practice to run a test before you actually implement the behavior described in the test. Therefore, a brand new unit test should generally fail when you run it for the very first time. Once you've demonstrated that the test initially fails, you fill in the code that the test is targeting. Having done this, you can confirm your code works correctly by running the test again. This time it should pass. The last step is called _refactoring_. The idea is to look at the code you've written to make the test pass and to clean it up.  This is your opportunity to remove duplicate logic and to clarify the naming of things like classes, functions, variables, etc. Basically you can reorganize your code however you wish as long as the expected behavior doesn't change. Once you're done refactoring, you can run the test once more to make sure that it still passes. Unit tests are helpful when you're initially developing a piece of functionality, but they're also useful in _regression_. That means you can periodically run your entire test suite, say before committing your code to your repository. If anything you've done breaks older tests, that alerts you to the possibility that you've introduced bugs with your latest code, and gives you a chance to fix those bugs first. Making sure all of the tests pass before checking in is a good practice. It gives you additional confidence that your code is still all working properly.

### Multiple sources of truth

Reading a single textbook or article is often a bad idea. Any source of information will be written in a particular context. It will skip some steps and also make assumptions about what you know. If you're confused (and even if you're not!), it's good to look for additional sources.

If the material you're reading seems too advanced, look for more beginner-friendly treatments. If you're reading about something in a particular programming language and it is not making sense, try to find the same topic addressed in a language you're more familiar with. Maybe what you're currently reading is too technical. In that case, look for high level descriptions to build intuition about the subject. In that regard, I really like the idea of [ExplainLikeImFive](https://dev.to/t/explainlikeimfive), a tag used online for articles that explain complex topics very simply.

### Fewer subjects at a time

I've talked to a lot of graduates from schools in many fields about their experiences, including math, science, medicine, dentistry, etc. Often enough, it's the same story: Learn by memorization, pass the exam, forget most of it, and repeat. I don't think it's the students' fault either. Students are loaded with so many classes to take each semester that it's very hard to do even a halfway decent job of learning. I think this is true in pretty much every field of study, and it's certainly true in computer science.

For most people, I think that cutting down the number of courses and focussing on fundamentals would be much better. When a student completes a class, it should mean they have mastered the material. The same idea applies for people learning on their own: Pick one or two subjects to work on at a time, and pay careful attention to really figure them out.

### Ask your own questions

While solving pre-defined problems and exercises is very useful, it can get monotonous. There's also something a bit passive about it. It's better than merely reading, but we're still leaving it up to someone else to test our knowledge.

How about coming up with our own problems? When you're learning something new, ask yourself questions about it. What does this imply? Is there a more general way of looking at it? Is it similar to something else? Can it be applied like so?

With programming, you can write small programs to test your ideas. I highly recommend creating a coding playground folder. Any time you are trying to understand something, create a small example program to test it out in your playground. You can also come up with larger projects to work on. Such larger projects will force you out of the tidy confines of well-defined exercises. You'll need to integrate disparate areas of knowledge and think creatively to make your way around roadblocks.

Often questions will arise naturally when you're learning something new. It's easy to let those questions drift by and to forget about them. Or, a question may occur to you, but you'll dismiss it with negative self-talk, "oh that's a dumb question." That's really a disservice to yourself though. Being curious and making connections is a good thing. Censoring yourself, on the other hand, will just slow down your learning process.

> There are naive questions, tedious questions, ill-phrased questions, questions put after inadequate self-criticism. But every question is a cry to understand the world. There is no such thing as a dumb question. 
>  
> *~ Carl Sagan*

You may find it helpful to have a notebook (or note app on your phone) always nearby. As soon as a question comes up, make a note of it. Then see if you can figure out the answer yourself. If so, great. If not, that's okay too. It's still good that you thought of your own brand new question! Now you can practice your research skills to get an answer.

As an example, a while ago I was writing some JavaScript code using async functions. As I was working, it occurred to me that it would be nice to combine a generator function and an async function together. I didn't know whether that was possible. After doing a bit of research, I found out that asynchronous iterators and generators had been proposed as a new feature for JavaScript. As of 2019, the new syntax is part of the ECMAScript 2020 Language Specification. It's also already supported by Node.js and by several major browsers.

When you take a hands-on approach to learning, I think you'll find that questions will naturally come up. If you want to practice though, try thinking about ways that an existing concept can be extended or combined with something else. Asking yourself questions is like exercising a muscle. The more you practice, the easier it will get.

### Challenge your material

Whenever you're learning something, challenge the  material and look for mistakes. Don't just take everything as gospel. Even when there aren't mistakes, this kind of active learning will ensure that you really do get it. When you challenge the material, it makes you explore edge cases and counter-intuitive possibilities. Doing so will make your understanding robust. You'll know how something works, and you'll also know in a hands-on, concrete way, the limitations and exceptions that go along with it.

A friend of mine told me a story from when she was in high school. She was learning special relativity in physics, and kept pestering her teacher with examples that seemed to defy the principles of relativity. I think her teacher was not equipped to answer those questions properly. It's actually well-known that there are a lot of scenarios in special relativity that initially seem to violate the rules. Understanding those edge cases is essential to have a proper understanding of the subject. I think what my friend was doing was great, and it's too bad that her teacher didn't understand the material well enough to encourage her properly.

### Go back and review

Sometimes we don't realize that we missed something in our study until later. We start a new topic and suddenly things we thought we understood become confusing. That's a good time to stop and go back to review that earlier subject matter. Don't just re-read it passively though. Go hunting for insights relative to the new information you're grappling with. _Real understanding is not a linear process. It's iterative._ There is a continual need to go back and shore up gaps in our learning that maybe we didn't know were there, or that reappear over time as we forget things.

When I am studying something new myself, I find that I will regularly return to the same material several times. The first time I may struggle with completely new concepts. The next time around, I will start to get it. The third time, I begin to focus in on a smaller number of things that stand out as being harder than the rest.  As time goes on I come up with more of my own questions and sometimes push the material in directions that are not mentioned in the book, article, or tutorial that I've been reading.

It can also be okay to study something up to a point, put it away, and return to it later on. Often we can acquire background knowledge in the meantime that makes us more prepared to tackle the material again once we come back to it.

### Fundamentals are important

Often, especially in the field of technology, there tends to be a bit of an obsession with specifics, like a particular programming language, library, or framework. I think this is a tendency we should resist, especially since technologies go through such incredible turnover. The darling of the moment may be all but forgotten in a couple of years.

If you start your education with overly specific technologies, I believe it will limit your ability to adapt, or to switch from one area to another. In addition, when we learn a particular technology in isolation, it often makes our level of understanding more superficial. It means that as soon as we leave the comfort zone of the context in which we learned the technology, we can quickly become lost.

Focussing on fundamentals means trying to identify the core concepts and building blocks underlying any technology or paradigm. Doing so is like having a good understanding of how to build things using lego blocks. It gives you the power to imagine any structure and build that from scratch rather than having to follow the blueprint that comes with a pre-packaged set.

Here's one possible example: Let's say you've learned how to use several frameworks and libraries for a front-end application. Perhaps you've used a CSS library like Bootstrap or a JavaScript framework like React, Vue, or Angular. _Do you know what problems these frameworks are trying to solve?_ It can be helpful to develop a small browser application using only HTML, CSS, and plain Javascript---no CSS framework, no JavaScript framework, nothing else. You'd be responsible for updating the page yourself whenever something changes. You'd also be responsible for making sure your JavaScript works properly for every browser that you want to support. Doing something like this can provide insight into why we use certain technologies. It also tends to make it easier to learn a new technology in the same general category, because you understand the underlying motivation of its developers.

More generally, it's always good to delve into the basics of computer science. You can consider investing some time learning about boolean logic, electronics, data structures, algorithms, operating systems, networking protocols, databases, computer graphics, AI and machine learning, bioinformatics and genomics, discrete math, linear and abstract algebra, probability and statistics, calculus, etc. There are so many fascinating fields that computer programming touches or relies on. Building up the depth of your knowledge in such fundamental areas will enrich your understanding and appreciation. Don't worry about trying to do this all at once though! (Unless you're doing a C.S. degree, that is.) If you can pick one or two areas at a time, and just build up your knowledge gradually, that's great. Over time, every small step will add up.

Any specific technology can be seen as some combination of fundamental ideas applied in a particular way. Looking at things in this way is very powerful. It's like a superpower, allowing you to pick up new things quickly and leaving your colleagues wondering how you did it!
