# A coder's code of ethics

_Isaac Lyman_

Code can do amazing things. We're all the beneficiaries of it: computers, cell phones, the internet, MRI machines---it's hard to imagine a world without software.

Code can also do bad things. It can lie, steal, murder, surveil and discriminate. In fact it's done all of these things, wielded by programmers like you and me, programmers who sometimes didn't understand what they were being asked to do and other times didn't care. Unless you're very lucky, at some point in your career you'll be asked to develop a feature that seems questionable or even just plain wrong. What will you do?

Will you rationalize it to yourself? It's not like the feature was your idea. Your bosses sign the paychecks, so they call the shots. It would be them in trouble, not you. Right?

Or will you take a stand? You're not some mindless soldier.

The decision is up to you, but you may find that "I was just following orders" isn't a very good defense in a courtroom, much less against your own conscience.

Several writers have considered the need for a code of ethics in programming. In my research for this chapter I studied the Hippocratic Oath, perhaps the most famous ethical code in any profession. Its ideals include knowledge-sharing, humility, and good citizenship. (If you're interested, check it out [on Wikipedia](https://en.wikipedia.org/wiki/Hippocratic_Oath#Modern_versions_and_relevance).) These are great things to start with, but there is much more to discuss. Following are some of the things to watch out for as you strive to be an ethical programmer.

### Privacy

Privacy advocates have been railing against Facebook [since the beginning](https://www.nbcnews.com/tech/social-media/timeline-facebook-s-privacy-issues-its-responses-n859651). Even the News Feed, which we now take for granted, was once seen as invasive---and one reason we take it for granted is because much bigger problems are rocking the social media platform on a regular basis, like the still-fresh [Cambridge Analytica scandal](https://en.wikipedia.org/wiki/Facebook%E2%80%93Cambridge_Analytica_data_scandal). And Facebook isn't the only company in the doghouse: [Google](https://en.wikipedia.org/wiki/Privacy_concerns_regarding_Google), [Amazon](https://www.washingtonpost.com/technology/2018/12/20/amazon-alexa-user-receives-audio-recordings-stranger-through-human-error/?noredirect=on), [Uber](https://www.theverge.com/2017/8/15/16150902/uber-ftc-complaint-mishandle-privacy-data) and many others have spent time in the news for failing to protect user data.

How did they go so wrong? There are a few factors at work here.

First, collecting user data is incredibly easy---you can collect a user's name, phone number, home address, government ID number or anything else they're willing to give you in only a few lines of code. Storing and retrieving data is so essential to computer applications that enormous sums of money have been spent engineering APIs and platforms to make it easier. It's almost the default thing to do in most cases, only a couple steps behind displaying words on a screen.

Second, protecting user data is much harder, requiring both expertise and intent. In order to prevent a password from being stolen, you have to know at least a few things about databases, cryptography, one-way hashes, and secure transmission. And then you have to apply them consistently across an entire system, no matter how large or complex it becomes. An application's security is only as strong as its weakest point, so this requires continuous investment. And security is generally inconvenient; if a customer calls in because they forgot their password, it may seem easier to just tell it to them rather than making them follow a password reset process over email. But no secure system will ever allow you to _see_ their password, let alone tell it to them.

Third, for businesses, "hard" and "expensive" are synonyms. And if no one in leadership is willing to make a principled stand, a corporation will always choose money over human rights. This is exacerbated by the fact that user data is worth a lot on the open market. Advertisers will do almost anything to obtain people's private information, and much of the software we use (especially free software) is wholly dependent on advertising.

These factors in combination make a perfect storm: it's cheap, easy, convenient, and profitable to collect oodles of user data and store it practically in the open. And the consequences, although certain, are never immediate. It's easy to forget that there are consequences at all.

Ethics demands more of us. As programmers, we should refuse to collect more data than our applications need. We should take users' trust seriously and protect what they give us. We should be sensitive to the kinds of data that are especially private and be especially diligent in protecting them. We should educate ourselves in security best practices. When hackers come looking for easy pickings (and they will) we should be confident that they'll leave empty-handed.

### Preventing bugs and outages

Most software is "line of business" software: applications people use on a daily basis to do their jobs. When you write this kind of application, you're holding a workforce's productivity in your hands. A bug, outage, or unnecessarily slow algorithm can cost someone several working days. That's a lot of responsibility.

Additionally, you probably know the frustration of buying an app or video game only to find that it doesn't work very well---maybe there are tons of bugs, or the servers go down a lot, or it loses all your data for no reason. You feel cheated, and rightly so. The developer made you an unspoken promise when they sold you the software, and now you're left to deal with their carelessness.

Some software does damage when it works. Most software does damage when it's broken. There are many things we can do to avoid shipping broken software, but in general we should test every release ahead of time with the assumption that it's broken in some way. Then we should fix it before releasing. Automated tests, quality assurance, redundancy, monitoring, and automated rollbacks can help reduce the frequency and impact of severe bugs (see Appendix A for definitions of these terms).

There's a huge difference between teams that take this seriously and teams that don't. And it isn't always the developers' fault; if your boss is setting impossibly tight deadlines, making you work overtime, or demanding you ship new features as quickly as possible, everything is going to be broken every day. You simply won't have the time or energy to keep your software bug-free. A company that runs like this is in serious trouble. But in most situations, you can make a difference by advocating for quality assurance and testing best practices. And this helps you keep your promises to your users.

### Avoiding [dark patterns](https://www.darkpatterns.org/)

A "dark pattern" is any feature of a user interface (UI) intended to trick users into doing (or not doing) something. Many dark patterns rely on users not paying close attention to every detail and every block of text in an application---and seriously, who does? If you've ever opted into something you didn't want because there was a "big green button," or accidentally clicked an ad when you were trying to make it go away, you're the victim of a dark pattern.

The first rule of UI design is "users don't read" (or, alternately, ["users don't think"](http://sensible.com/dmmt.html)). This can be an inconvenience---we can't just use paragraphs of text to tell users exactly what to do. We have to make it _obvious_ what the user should do through the careful use of color, contrast, sizing, positioning, and iconography (and yes, text, but usually only a word or two at a time). This is hard, which is one reason why designers are so valuable. But generally a dark pattern isn't the result of a simple oversight or design mistake. It's an intentional attempt to take advantage of users' trust in order to hijack their time, attention, or wallet. And it's incredibly common.

File sharing and download sites are full of dark patterns. Sometimes there are so many "Download" buttons it's nearly impossible to figure out which ones are ads in disguise and which one is real. And many news and media sites are almost as bad, with so many ads and newsletter signup forms you can't see the content you came for. But even the most well-known sites on the web---Facebook, LinkedIn, and TurboTax, for example---are notorious for their use of dark patterns to get users to give up personal information, share contact lists, or pay for a service advertised as free.

Another kind of dark pattern relies not on tricking the user into doing something they don't mean to, but on making it difficult to do something they _do_ mean to. Several major brands---like Blue Apron, Marriott Hotels, and the New York Times---have recently been called out for making it incredibly hard to unsubscribe from their emails or services, often requiring a lengthy phone call and identity verification even though they allow you to sign up online with only a few clicks. If that isn't bad enough, most advertisers and data brokers will collect information about your internet browsing habits without your permission or knowledge, effectively "signing you up" for a service you didn't even know existed---and you usually can't close your account with them, regardless of how much you may want to.

We may not be designing the apps we write, but we should still insist on ethical design standards. There's no excuse for employing underhanded tactics to trick our users or trap them into an arrangement they want to leave.

### Impartiality and accessibility

We're tempted to think of computers as completely unbiased and objective, but this assumption is problematic: it leads to systems that perpetuate our own biases and those of the world around us. Computers may not be born with an understanding of racism, sexism, ableism, or classism, but unfortunately, you can't avoid bias just by being ignorant of it.

Our default approach to algorithms that deal with people may be to treat each of them as a data point, completely equal in the eyes of the code. But this lofty ideal falls apart as soon as we introduce a user interface, business logic, or artificial intelligence. Technical equality is not the same as fairness.

A blind user and a sighted user might be treated as equal data points by our code, but if we don't build accessibility into our UI, the blind user will be unable to use the software. Our equality is their disadvantage. This isn't the computer's bias, it's ours, manifested in code.

An application's database might not store information about sexual identity, race, or social class, but due to differences and biases in the real world, the software can effectively discriminate on any of these bases by making assumptions about the user's physical size, sexual preference, skin contrast, living arrangements, or access to a cell phone.

Artificial intelligence is especially prone to bias. Amazon [learned this the hard way](https://www.aclu.org/blog/womens-rights/womens-rights-workplace/why-amazons-automated-hiring-tool-discriminated-against) in 2018, when it tried teaching an AI to select job candidates similar to the people they had already hired. The AI quickly learned that most of their employees were men, so it started discounting resumes with the word "women" or the names of certain women's colleges on them. This was an egregious case of sexual discrimination. But AI can be even more insidious, using much less obvious data points as proxies for race and sex. Something as innocuous as a zip code can enable discrimination unless careful controls are in place.

It's our job to watch for and avoid these issues. And we're likely to fail unless we have people on our development teams who don't look like us---people of other races, sexes, levels of ability, and socioeconomic backgrounds. A combination of awareness, diversity, and broad user testing is the best way to ensure our applications are truly impartial and accessible to all kinds of users.

### Do no harm

The famous phrase _primum non nocere_ ("first do no harm") is a core tenet of the medical profession. It should also be a tenet of ours. It's important to consider the human cost of every development project. Some software, whether by design or by lack of foresight, does harm in real and immediate ways.

Weapons are a case in point. No modern missile takes flight without a team of engineers behind it. That's a heavy responsibility, to write code knowing that it will end lives. No one would blame you for refusing to be part of such a project. The ethics of military force are a topic of debate, but wherever human casualties are involved, we'd better be prepared to account for our decisions.

Malware is a more clear-cut example: few of us would attempt an ethical argument to justify the creation of viruses and ransomware. Yet malware is a fixture in the modern world, a constant threat to our digital well-being. [WannaCry](https://en.wikipedia.org/wiki/WannaCry_ransomware_attack), a piece of ransomware that made headlines in 2017, infected thousands of computers throughout Great Britain's National Health Service and forced hospitals to turn some patients away. It also halted production at certain factories and automotive plants. Thanks to some high-quality security research and a few lucky breaks, the impact of WannaCry was relatively low. But it's easy to imagine a much worse scenario: unusable MRI machines, hundreds dead from health complications, frozen supply chains, mass layoffs, abrupt economic collapse in some sectors, and so on. The creators of WannaCry appeared to be spreading it for their own financial gain, requesting a few hundred dollars per victim. But there are credible allegations that they were agents of the North Korean government, which makes the attack a potential act of war.

Make no mistake, you don't need to be programming a ballistic missile to be dealing with life and death.

Of a less catastrophic nature (but still decidedly bad) is software that uses your computer's resources in ways you wouldn't appreciate, like 2018's spate of [cryptojacking](https://www.nbcnews.com/tech/tech-news/your-computer-could-be-quietly-mining-bitcoin-someone-else-n922101)---a word describing applications that secretly use your processor to mine Bitcoin, enriching their creator while leaving you with an inflated electricity bill, wear and tear on your hardware, and a slower computer. This is more petty theft than high crime, but that doesn't make it victimless.

Perhaps the trickiest time to apply "do no harm" is when we're making tools that rely on user-generated content. Twitter and Facebook, for example, are irreplaceable parts of many peoples' personal and professional lives. The amount of good-natured media and humor generated daily on the sites is impressive. But they're also used daily to harass women, LGBT people, and people of color. They're used to encourage acts of group violence and suicide. They're [depressing and addictive](https://www.marketwatch.com/story/new-study-claims-facebook-instagram-and-snapchat-are-linked-to-depression-2018-11-09) to users. There are tools that allow users to report the worst cases of abuse, but moderation is spotty at best---and the people who do it suffer [severe mental and emotional consequences](https://www.cnet.com/news/facebook-content-moderation-is-an-ugly-business-heres-who-does-it/). In these circumstances, we'd be justified in asking if social media should exist at all.

Even in the simplest of situations "do no harm" is an essential standard. Any software that helps a doctor do their job, even something as innocuous as a file-sharing server or document editor, can become urgently important in a patient's life during a medical crisis. A bug or bad UX could lead to injury or death. The same goes for air traffic controllers, taxi drivers, manufacturers---even small-time retailers stand to lose a great deal if their software is broken. Regardless of what you're building, the user's worst case scenario may only be a few lines of code away.

These are concerns you should take with you to each job interview and each project. We should insist on writing applications that are reliable, make the world better, earn users' trust, and are thoughtful about the ways they allow people to interact.

### The golden user story

I often hear stories of CEOs who refuse to let their kids use software produced by _their own companies_. And this illustrates perhaps the most essential principle of all: if you wouldn't want an app to do something to your child or significant other or friend, then don't make that app.

We have the ability to make software that enriches lives and creates opportunities. And as Marc Andreessen famously said, software is eating the world. We, the next generation of programmers, can decide what the future looks like. It all depends on the code we write today.
