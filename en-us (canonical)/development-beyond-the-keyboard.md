# Software development beyond the keyboard

_Isaac Lyman_

One of the greatest paradoxes of software development is the relative unimportance of code. As engineers we study code, we teach about code, we agonize over code, we go to conferences and debate each other and dream vivid dreams about code. Yet there is no line of code in any programming language that will make a company profitable or an idea successful. Applications are of course valuable, and largely responsible for the experiences that shape the modern world, but most applications could be equally useful if they were written in a different programming language, under a different paradigm, using different techniques and algorithms. There are infinite ways to write a program. Sometimes one way is faster than another, sometimes more readable, sometimes more error-resistant. But usually it's just different.

In many people's minds, then, the difference between a good developer and a great developer isn't about how quickly or correctly they write code. It's about skills beyond the keyboard: communication, leadership, reasoning. Following are a few skills you can learn to raise your value in the workplace.

### Asking hard questions

Code hates ambiguity, which is one of the main reasons coding is hard. If you want to code an _idea_, you have to convert it to an _algorithm_, which requires imagining it on a deep level: what are the steps from beginning to end? How will you accommodate different users, different privileges, different devices? How will the application know what it needs to know? What if something goes wrong? What if the user does something unexpected? What if a hacker is trying to get in?

CEOs and managers usually think about products and features on a high level (and they should). They'll say something like "we need a button that lets people export their data as an Excel spreadsheet." They see this feature as if it were under a spotlight in a dark room; it seems so simple. Your job as a programmer is to listen to them, stand in the spotlight with them and understand their vision, and then grab a flashlight and explore the dark, dusty corners of the room. What should the spreadsheet be called? What columns should it have? Does it need access controls? Should the application warn the user if their data is empty, or corrupt, or larger than 100 megabytes? Is Excel even the best way to handle this kind of data? Would a CSV file be acceptable instead, since it's easier to generate?

Sometimes the questions need to dig even deeper. Is this feature worth two months of our team's time and effort? What problem are we actually trying to solve (see Appendix A, "XY Problem")? Are we sure this will solve it? Are customers asking for this? What problem are _they_ trying to solve? And so on. Some questions you can answer on your own, but many will need to be discussed by management. Sometimes you'll have to explain your question several times before anyone understands it. Sometimes they never will, and you'll need to ask a different one.

This may not be coding, but it's software development in the truest sense. It's part of the painful but necessary process of making software _real_, and it's something that can only be done by people like us: people who are methodical and thoughtful, people who see the smallest details and sense problems before they happen. It's a talent that runs strong among coders, and one you can develop if you haven't yet.

As a new programmer, you may feel nervous about asking questions that risk putting your lack of experience on display. It's normal to feel that way, but don't let it silence you. If you prefer, you can take the questions you're most insecure about to your dev lead, mentor, or manager, one-on-one. But keep in mind that your inexperience is in many ways an asset---you have a fresh perspective and haven't developed the same blind spots that many of your senior colleagues may have. And even the most senior of programmers asks a dumb question now and then.

### Contributing to UX and feature discussions

Some managers see developers as nothing more than code-producing machines, relegating them to the last step in a lengthy design process. This often backfires. Without a developer in the room, it's difficult to know what is easy and what is impossible, what adds complexity and what reduces it, what it costs to build something _good enough_ versus _perfect_.

Developers are master problem-solvers. Coding is, after all, an exercise in working with constraints, tradeoffs, and outcomes. The best companies recognize this skill and ask for developers' input throughout the entire product development process, from design to delivery.

If you can, take the opportunity to sit in on high-level product discussions. If you pitch in now and then with "that's an expensive feature---could we do it like this instead?" or "that's a great idea, but it will take some effort. Could we validate it with a few users first?" or "that's simple, I can build it in an afternoon," you'll quickly find yourself indispensable in the process. This is perhaps the place where your skills make the biggest difference: not hunched over a keyboard, staring at an IDE until your eyes blur, but at the table with product managers and executives, representing the possibilities and limitations of code as everyone plans ways to improve customers' lives.

### Talking to users

A famous moment in the tech world occurred in 2001, when a group of 17 software professionals gathered in Utah, USA, and agreed on a set of core principles to guide the development of software in the Internet Age.

> ...we have come to value:
>
> **Individuals and interactions** over processes and tools
>
> **Working software** over comprehensive documentation
>
> **Customer collaboration** over contract negotiation
>
> **Responding to change** over following a plan
>
> *~ Manifesto for Agile Software Development*

The last two values, "customer collaboration" and "responding to change," point to one of the most important processes a software company can adopt: regularly speaking to customers about their needs, then updating priorities and plans to accommodate them better. Companies that fail to do this may produce high-quality software but most of the time it won't be very useful. Developers spend a lot of time worried about "building things wrong"---writing bugs or misunderstanding specifications, for example---but an even bigger problem is "building the wrong things." If your app doesn't solve my problem, I don't care if it's the most beautiful and bug-free app in the universe.

As a developer, you could argue that it's not your job to speak to users and gather feedback. The problem is that in too many organizations, _nobody_ thinks it's their job (although good UX designers or product owners will usually take it on). In reality it should be everyone's job: every part of the process exists to provide a better experience for users, so everyone has a stake in understanding them. For a deeper discussion of this topic, see Edaqa's chapter "You are an interpreter".

### Writing documentation

Poor, out-of-date or nonexistent documentation is the status quo for much of the tech industry. This causes endless headaches for managers. When a developer leaves after a long employment, they take knowledge with them that no one else has. When a new developer joins the team, it takes them months to get up to speed. When two teams work together, they end up spending tens of hours sharing knowledge face to face. Even in a small company with low turnover, "mental turnover" is still expensive---I don't remember the details of what I was working on a year ago, do you? It might as well have been another life.

If you know how to write clear and organized documentation, you can reduce these expenses dramatically. Documenting the setup process for new developers can help a recently-hired teammate contribute much sooner. Documenting the architecture of a system and its core assumptions and constraints can create an invaluable roadmap for developers tackling complex issues. Creating an FAQ for bugs or error messages that frequently appear can save your teammates days of unnecessary debugging. Whenever you or one of your teammates asks "how does that work again?" that's a sure sign documentation is needed.

Writing is hard, so don't be afraid to take the easy route: use lots of bullet points, throw in a drawing or diagram here and there, overexplain things a little, and ask your team to review and edit what you've written.

One of the most powerful and respectful ways to leave your job is with a digital stockpile of excellent documentation behind you. Once you give notice, insist on taking the time to write things down: everything you built alone, everything you were the expert on, everything people asked you to explain on a regular basis. Your coworkers will be thanking you until long after you're gone.

### Code design

Speaking of documentation, one of the best ways to develop both faster and smarter is to plan out your solutions ahead of time. At a previous job, we called this a "dev design." The developer assigned to a task would write a summary of the code they planned to write, including a breakdown of sub-tasks, a list of every file they planned to change, method signatures, class and field names, table schemas, and---for especially tricky situations---even a few lines of pseudocode (see Appendix A for definitions of these terms). Then they would take 20 minutes to review it with the team. This was the most productive meeting of our day. More often than not, we'd save each other _hours_ of development time by saying things like "we already have a class that does that, we can reuse it" or "that's a tricky procedure, watch out for race conditions" or "I don't think that's what was intended with that feature, let's talk to our manager and clarify it."

At that company, we further justified the time spent on dev designs by doing away with formal code reviews. If our dev design turned out to be inadequate once we started coding, we would update it and notify the team. This way, the actual code being written was never a surprise---it was "pre-approved." Replacing code reviews may not make sense for most teams, but when building new products and features, I tend to believe that code design ahead of time is more valuable than code review after the fact. Of course, it doesn't have to be an either/or situation. On my current team we do both.

Even if your team isn't friendly to the idea, doing code design on your own has compelling benefits. It helps you avoid rewrites by making sure all the parts of your solution work together conceptually. It helps you find blockers sooner, so you can stay productive while they're being resolved. It gives you a record of why you coded things the way you did, so in six months when you're refactoring or extending a feature, you can remember the constraints you were working with.

### Development isn't just code

To call yourself a software developer is to claim the whole development process as your own. Don't forget that code is only one step of many in that process, and it's near the end. Becoming proficient in the other steps will make you a more well-rounded and valuable asset at every job you take.
