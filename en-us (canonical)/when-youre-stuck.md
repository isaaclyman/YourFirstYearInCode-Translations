# What to do when you're stuck

_Isaac Lyman_

Part of a programmer's job is chasing down missing semicolons and complex caching issues, scrutinizing and head-scratching over every line of code in an application. This is one of the most frustrating things about code: we use it to offload complexity from our brains, but the inverse of this benefit is that any useful program will be too complex for us to wrap our minds around completely. Complexity creates unknowns, and every unknown is a bug waiting to happen.

Another frustrating thing about code is that it has to be learned by rote. You're unlikely to discover the keyword or API you need by blind experimentation. And every language and library has gotchas, which may or may not be described in the documentation. There's no substitute for experience in situations like this.

Most programmers (I'd guess) are acquainted with the deep, hot, crushing frustration that ensues after hours of being stuck on a problem and not knowing how to progress. On that subject, here's a tweet from the guy who created Stack Overflow:

![](images/jeff-atwood-code-head-wall.png)

_Source: [https://twitter.com/codinghorror/status/695143348521140225](https://twitter.com/codinghorror/status/695143348521140225)_

This particular usage of my head has probably shortened my life expectancy by a few years. If you're a new programmer, you can avoid some of that by following a process similar to the one I'll recommend here. Each step builds on and escalates the one before it, and most of the time you'll get un-stuck long before you reach the last step.

### 1. Be self-aware

This will all go a lot better if you're taking care of yourself and paying attention to the way you feel. Sleep deprivation, hunger, a hostile work environment, or stressors in your personal life can directly affect your ability to solve problems. Ideally, you should be in a peaceful frame of mind when you start working. Then when you get frustrated, you can label the problem ("I'm stuck"), take a deep breath, and start on the path to resolving it.

To get off on the right foot, consider a morning routine that includes meditation and/or journaling. These can help you be more aware of your feelings.

### 2. Timebox your frustration

Once you've determined that you're stuck, set a timer for 20 minutes. Turn off Slack and email, put on your headphones, politely postpone questions and conversations with coworkers, and start Googling the problem. Read as much as you can about it. Try several different search queries. You may be surprised at how many other people have had your specific problem, even if it seems unique or proprietary. If you're lucky enough to have an error message, search it in quotes. Consider all the systems (libraries, packages, frameworks, APIs, services, etc.) that interact with the faulty part of the application, and ask yourself if the problem may be in a different place than you thought it was.

### 3. Rubber-duck it

Explain the problem to an imaginary coworker. Got a rubber duck or stuffed animal handy? Even better. I have a stuffed animal on my desk at all times. Describe the issue in as much detail as you can, and assume that your coworker isn't intimately familiar with the code you're talking about.

If this is hard for you, try composing an email or Slack message to a coworker that might be able to help. Don't send the message yet---just write it out and revise until you're satisfied that you've covered the problem in clear terms. Make sure to mention the research you've done and anything you've ruled out as the possible cause.

### 4. Draw it

On a piece of paper or a whiteboard, sketch out a basic diagram of the methods, classes and files that are interacting in the problem area. No fancy murals here---a bunch of circles and lines should be fine. Draw a piece of data traveling through this system as well. If you need to dig through the code a little to make sure your drawing is correct, take a minute to do so.

### 5. Take five

By now you should understand the problem pretty well (or know what you don't understand about it). At this point, put your computer to sleep and give your brain a rest. Anything that isn't mentally demanding will do. Strike up some light conversation with a friend or coworker, take a nap, go for a walk, get some lunch, watch a funny video, hit the gym, or take a shower. The solution may occur to you while you're doing something else entirely.

### 6. Ask for help

By now, you're reaching the limit of what you can do alone; you've probably spent 30-90 minutes on this problem. It's time to bring in reinforcements. Find a coworker who has relevant experience and ask for help. If you have no coworkers or none are available, reach out to your mentor. If you don't have a mentor, now's a good time to put that on your to-do list.

Don't worry about wasting their time. You've researched and thought through the problem, so you can describe it completely and succinctly. And for you to keep trying on your own could turn into a much more serious waste of time.

### 7. Isolate the problem

If you're still stuck, it's time to start from scratch. Create a small repository or use an online tool (like [Codepen](https://codepen.io/), [Repl.it](https://repl.it/), or [Stackblitz](https://stackblitz.com/)) and see if you can add _just enough_ code to reproduce the problem. One piece at a time, replicate the environment and code around the issue until you see it happen. Then try to remove various pieces, in turn, to make sure you haven't included anything unnecessary. What you'll end up with is the smallest possible example of the problem (an [MCVE](https://stackoverflow.com/help/mcve)), which will make it easier for someone to help you solve it. Review this with the person you asked for help in the previous step.

### 8. Write it up

Write a full description of the problem. Include code samples, a link to your repository or online code sample, screenshots (if applicable), and a summary of the things you've tried and the research you've done. Don't include anything that would pose a security risk to your company if it were posted publicly, because that's the next step.

### 9. Get a buddy and ask the internet

Find a buddy (possibly the person from step 6) and ask them to read through your writeup from step 8 to make sure it makes sense. Then post it on the internet. Stack Overflow and other Stack Exchange sites (like Server Fault, Software Engineering, or Database Administrators) are your best bet for getting a timely answer to your question, but their communities can be hostile to question askers, so don't go in alone---ask your buddy to upvote your question and help you defend against rude commenters or votes to close the question. With any luck, you'll get some good feedback and ideas within a day or two.

### 10. Find a workaround

If you still haven't solved your problem, it's time for Plan B. You might consider altering the affected functionality, adding some fallback code, or switching to a different software library. This sounds a lot like giving up, but compromises are at the heart of all software, so don't beat yourself up over it.

### Finally, document the solution

Once you've solved the problem, consider writing some documentation about it in order to alleviate someone else's frustration. This might be a comment in the code, a page on your company's internal docs, an email, a post on your blog or [dev.to](https://dev.to/), or a self-answered Stack Overflow question.

And once again, keep an eye on your mental health. Programming is inherently frustrating. We all need breaks. If you're constantly getting burned out, it's time to take a day off, change your routine, or look for another job.
