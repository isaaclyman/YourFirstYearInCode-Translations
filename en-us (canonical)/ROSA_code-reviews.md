# Code reviews

_Rosalind Thuy Pham_

### What is a code review?

Code Review is an activity performed by developers after finishing a feature or bug fix. A developer requests a review from their peers. Depending on the impact of the code to the current code base, it may require more than one developer to review. 

### Why do we do code reviews?

In software development, an application is broken down by features. A feature can be isolated or depend on another feature. To ensure each feature is added without defects or side effects, developers request a code review from their peers or voluntarily review each other's code.

In most cases, reviewing code means validating and checking for code quality violations. However, in many collaborative companies, code review is also seen as a way to share domain knowledge within a team. Through code review, senior developers can share high-level understanding with junior developers to avoid duplicate code and improve performance. Junior developers can also review others' code. It's an excellent chance to see how others have applied code guidelines and to learn best practices.

### Who should review a junior developer's code?

Any developer on their team. If the code is implementing a new feature, the junior developer should pick a senior developer who recently worked on a related area of the code. Early involvement of a senior developer can make the code review go more smoothly. If the code is a bug fix or improvement, like a typo, missing variable, or wrong type, the reviewer can be any available team member.

### How should you review someone's code?

Ideally, the developer who wrote the code and their peers should have discussed the feature or bug fix and designed the overall solution before the code was written. Understanding the context and conceptualizing the solution are far more important than making the code pretty. Good planning helps to avoid wasted time and effort if the requirements change or a solution already exists.

There are many possible solutions to most problems. At this point, reviewers and code authors should feel that they both understand and agree on the chosen solution. Next, they should both agree on the logic of that solution.

When viewing the code for the first time, reviewers refer back to the written product requirements to get some context around the code and use a diff tool to identify the logic of the solution. For example, say the solution is an input field for a user to type their name. The logic could be a function which captures each key press and its value. This is a simple example, but the logic of a solution can span multiple functions in different files. Reviewers should ask questions or leave comments based on their impression of the code.

For many junior developers, this might be their first time receiving feedback on their work. Therefore, some questions and comments may sound more sarcastic and offensive than they are. Here are some example questions:

- "Why do you need these?"
- "I don't think it makes sense to add this line."
- "I don't understand what this function is trying to do."

Discussing someone else's work is not easy, and not all developers are excellent communicators. My best advice for junior developers is to focus on what you've learned at the end of the day, not what people might think about you. The fact is the more feedback you receive, the more you learn, and the better you figure things out. It's hard to take criticism, but it's better than no feedback at all.

The developer who submitted the pull request (the author) should read and respond to each question and comment. If necessary, the author and reviewers can have a discussion in person, over the phone, or while pair programming to explain the solution to reviewers.

At the end of this step, the author and reviewers should agree on the logic for the solution. With the logic-first approach, the reviewers may remember some existing logic and suggest that the author reuse it. In a smaller code base where there isn't much existing logic, the reviewers might suggest making a piece of code more generic so other developers can reuse it in the future. Everything other than logic, such as typos and naming conventions, reviewers should note and save for later.

After reviewing the logic, reviewers should pull the code, run tests, and check for errors. After resolving errors, the author should write new tests to cover those error cases. Reviewers should double-check for basic mistakes such as syntax errors and infinite loops. After all tests are passing, the author should revisit earlier feedback for any refactoring suggestions and improvements, such as removing dead code or adding documentation. Before asking for another round of review, the author should also validate their code with the team's code guidelines. Here are some standard things to check:

- Are function and method names clear and descriptive?
- Is the code consistent across different files?
- Do functions accept the same types of parameters and behave the same every time they execute?

At this point, authors who are junior developers might ask their reviewers about ways to optimize and improve code performance if needed.

Once each step has been completed---planning, reviewing logic, fixing bugs, and refactoring---the process is complete and the code is ready to merge.
