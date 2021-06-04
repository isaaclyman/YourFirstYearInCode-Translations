# The DevOps introduction I wish I had

_Periklis Gkolias_

Buzzwords are common in this industry. They're used everywhere (sometimes in the wrong way) and because of that, people are often afraid to ask 101-level questions as they don't want to sound ignorant.

Some years ago, my manager asked me if I wanted to do some DevOps work as part of my software engineer job. Of course, I was young and afraid to ask what that meant so I just said "yeah, let's give it a try. Worst case scenario, I will die and you can take a day off to grieve."

Thank God, I am still alive, as you have probably noticed. So now I want to give you a nice round overview of the terms I encountered in my initial foray into DevOps and wish I knew back then.

### Till not many years ago...

As software engineers, we write software on our computers for other people. And that is problem number one. The software will eventually have to run on someone else's computer because the end user doesn't have access to our computer. And this is a good thing; imagine the security implications if anyone could access your computer.

But the end user doesn't care how well the software works on our computer. They care how it works on theirs. If we want to do something meaningful and maybe make some money, *we have to put our software out in public*.

But who will do this job? Till not many years ago, it was up to the "operations people" of the company. I might be oversimplifying here, but you can think of them as colleagues from the IT department that had a technical background but weren't coders or managers. For example, [server administrators](https://en.wikipedia.org/wiki/Server_administrator) and [database experts](https://en.wikipedia.org/wiki/Database_administrator).

Can you see a problem here? Think about that and I'll explain in a moment.

### DevOps

The DevOps discipline was created to bridge the gap between developers and operations people, the groups discussed above. The goal is for the transition from a developer's computer to the public to be mostly quick, flawless, trackable, and repeatable, with as little as possible manual work. You may hear this transition referred to as the *deployment* of the application.

Before that, deployments caused constant disagreement and blame between the two tribes. They were slow and painful and required lots of working hours. This is the problem I mentioned in the previous section.

The operations people often had no clue why the app couldn't be deployed even though they were doing everything they were supposed to do; after all, they didn't write it or understand the internals. And the developers were blaming the operations people because "it works on my computer."

Starting in 2001 there was huge movement (called the [Agile manifesto](https://agilemanifesto.org/principles.html)) to improve the way we produce software and provide it to the public. The DevOps discipline was born as a side effect of that.

### The public

What is this terrifying "public" that led all those poor operations people to exhaust themselves working overtime? At the time of writing, when people are speaking about deployments, they usually mean deploying an application to a cloud server so that anyone with a URL (more or less) can access it.

The cloud? What is the cloud?

When it comes to software engineering, it basically means "another company's computer." Giant companies like Microsoft (with [Azure](https://azure.microsoft.com)), Amazon (with [AWS](https://aws.amazon.com/)) and Google (with [Google Cloud](https://cloud.google.com/)) have thousands of servers running to support their business, as do some smaller companies.

Some of those computers are rented out for others to use and the users (usually companies that don't have such high-quality infrastructure and don't want to buy it) are charged accordingly, *based on how much time they occupy it for*. This offers a few advantages and disadvantages, but those are outside the scope of this chapter.

### What is the main problem when deploying to the cloud?

A major problem, as mentioned before, was that there was no guarantee that if a feature was running on the computer of the original developer then it would run equally well on the cloud.

This can happen because of missing libraries, different library versions between the two machines, or even because the local computer runs on a different operating system than the server, to name a few examples.

### Running an application in various operating systems

This is actually very common. Let's say you're at a company where the CTO used to work for Microsoft, so having Windows workstations is something they are not willing to negotiate.

Let's also say one of your major customers is a giant Linux software company. As you can imagine, they're guaranteed to have Linux servers on their infrastructure.

What do you do? Do you switch to Linux or make them switch to Windows? _Neither scenario is viable._ What if you had hundreds of customers which all had different operating systems in their infrastructure? How do you make your applications run well for all of them?

There are various approaches to solve this problem. It's one of the main concerns of not only a DevOps engineer but also the whole team.

### Docker and containers in general

The most popular solution goes by the name "containerization." Containerization is an approach where you enclose everything you need (literally everything) in a software "box" (or container) in order for the software to run smoothly.

The container, for the sake of simplicity, can be thought of like a tiny operating system that runs on top of your existing one and is completely portable.

You can move a container from computer to computer (and of course to a cloud server). If it works on one computer, it will also work on another, equally well, with no strings attached. The only prerequisite is to have the appropriate container technology like [Docker](https://www.docker.com/) installed.

So for example, in order to solve the aforementioned issue, we could follow this approach (which is very common):

- Create a container using your preferred operating system.
- Include the source code of our app in the container.
- Include the libraries our application needs, along with any other piece of software our app relies on.
- Configure the container so that when it is accessed, the app starts automatically.
- Test the application thoroughly from inside the container.
- Once happy, send it to the customer(s). You are now confident that it will work on their side too, regardless of the operating system they use.

*Note:* When it comes to Docker, we distinguish between a container and the file that runs inside of it with the terms "Docker container" and "Docker image."

Another famous solution is [Packer](https://www.packer.io/) by [Hashicorp](https://www.hashicorp.com/). Feel free to read about them and see what works best for you when the time comes.

### Docker vs. virtual machines

A virtual machine or VM is a standalone operating system that is treated as a normal application by the host operating system. You can interact with it as if it were your actual environment and forget about the host.

Yes, [Docker](https://www.docker.com/) and VMs solve similar problems. They don't work in the same way though, and Docker is often the preferred approach nowadays.

The most important differences lie in their size and the way they utilize the host operating system. For example, Docker is usually much more lightweight and tends to share more functionality with the host operating system than a VM.

### Provisioning

"Provisioning" is another term you might encounter and be too afraid to ask what it is.

In the DevOps context, it means to set up the infrastructure needed for an application to work. This work is often automated and done in the cloud.

So if someone wants to provision a test environment, they probably have to allocate some server space in order to put the containers inside and run them. If done manually, this can be a tedious process.

Thankfully, there are provisioning tools on the market that do the job for you fairly easily, or at least with minimal input (apart from the initial configuration).

### Continuous Integration and Continuous Delivery (CI/CD)

Those two terms refer to an organization's need to know if newly-written code has problems and if not, to be able to send it to the customer in an automated way, whenever they want. It's a common practice and you should have a high-level understanding of it.

Here is how this works:

- You create a new feature requested by a customer.
- Your code gets reviewed and tested by members of your team.
- You add your changes to the code that will be delivered to the customer (the "release branch," as devs call it).
- An automated process notices what you did and starts doing various things with the new version of the app, like trying to compile it, run any automated tests, and (you guessed it) prepare your Docker image. This is the "Continuous Integration" step.
- If everything works, the process sends this image to the customer's servers. This is the "Continuous Delivery" step.

Some of the most well-known CI/CD tools are [Jenkins](https://jenkins.io/), [Travis](https://travis-ci.org/), and [Bamboo](https://www.atlassian.com/software/bamboo).

### Tips for the future

Before closing this chapter, I would like to give you a couple of tips that you might find helpful during your first years in tech.

- If you don't understand something, Google it. If you can't figure it out easily, ask. No one expects you to know everything and you never have to. If someone has told you otherwise, you're in the wrong company.
- Automate as much as you can. Anything that has to be done manually is error-prone and far more time consuming.
- Never stop learning. DevOps is a great field and is evolving rapidly. You need to keep your knowledge up to avoid becoming outdated or obsolete.
