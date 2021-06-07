+++
title = "When to repeat yourself"
date = 2021-04-25
author = "Diego Torres Arguedas"
+++

Good practices are methods or techniques that have been generally accepted as the best option to use in a certain field or industry. 
They also faciliate communication between peers - if you bring a common practice in a conversation with your colleague they probably will know what you are talking about.
In programming the *Don't Repeat Yourself (DRY)* is one of most known and common practices.

# 1. Don't Repeat Yourself (DRY)

The main idea behind the *DRY* is to avoid duplication of knowledge in order to reduce the risk of defects appearing when new code is introduced in the future.  This comes with benefits such as having a single source of truth and having less code to maintain. 

*DRY*'s main objective is avoiding __duplication of knowledge__ (business rules or algorithms<sup> [[1]](#ref1)</sup>) but it's not necessarily about __duplication of code__.  The same code can be found several times but if it represents different business rules then there is no duplication of knowledge. 


[Mathias Verraes](#ref2)  elaborates further on this:

> DRY is about knowledge. It’s about cohesion. If two pieces of code represent the exact same knowledge, they will always change together. Having to change them both is risky: you might forget one of them. On the other hand, if two identical pieces of code represent different knowledge, they will change independently. De-duplicating them introduces risk, because changing the knowledge for one object, might accidentally change it for the other object.


# 2. Risk: Wrong abstraction

Generally speaking, abstraction means removing unnecessary detail in order to focus attention on details of greater importance <sup>[[3]](#ref3) </sup> <sup>[[4]](#ref4) </sup>. In programming, this can be achieved by creating classes (generalisation), interfaces (information hiding) or functions (functional abstraction), among others. Abstraction is widely used to simplify things that may be very complex , but it can also be used to achieve other objectives such as __avoiding duplication of code__. But sometimes a __wrong abstraction__ can be introduced. 

Sandi Metz presents a really clear example of this:

> 1. Programmer A sees duplication.
> 2. Programmer A extracts duplication and gives it a name.
> This creates a new abstraction. It could be a new method, or perhaps even a new class.
> 3. Programmer A replaces the duplication with the new abstraction.
> Ah, the code is perfect. Programmer A trots happily away.
> 4. Time passes.
> 5. A new requirement appears for which the current abstraction is almost perfect.
> 6. Programmer B gets tasked to implement this requirement.
> Programmer B feels honor-bound to retain the existing abstraction, but since it isn't exactly the same for every case, they alter the code to take a parameter, and then add logic to conditionally do the right thing based on > the value of that parameter.
> What was once a universal abstraction now behaves differently for different cases.
> 7. Another new requirement arrives.
> Programmer X.
> Another additional parameter.
> Another new conditional.
> Loop until code becomes incomprehensible.
> 8. You appear in the story about here, and your life takes a dramatic turn for the worse.  <sup>[[5]](#ref3)</sup>

In this case, a wrong abstraction has been introduced and making the code difficult to change and to understand. As Metz points out: *duplication is far cheaper than the wrong abstraction*. 


# 3. When to Repeat Yourself
Avoid refactoring the code to remove duplication if:
- You are not familiar with the business logic. You may not identify those cases when the duplication in code doesn't represent duplication in knowledge.
- You don't have enough examples of code to come up with a good abstraction. <sup>[6](#ref6)</sup>
- The risk introduced would be higher than the benefit of removing the duplication. If it's a critical module that has been working for ages, then leave it as it is.
- You don't have enough time to test afterwards. For example: if you are in the middle of fixing a critical bug in production then most likely it's not the best moment to start a refactoring.

Important to mention is that it is also acceptable to repeat yourself if you are moving away from a wrong abstraction. <sup>[4](#ref4)</sup> Refactoring doesn't always mean less code.


# 4. Key Points
* DRY is about duplication of knowledge, not duplication of code. 
* Duplication is far cheaper than the wrong abstraction.
* Be careful about introducing wrong abstractions. If necessary, re-introduce duplication to remove wrong abstractions. 
* Before removing any duplication take into count the context and the __What-When-Who__: what is changing, when it needs to be done and who's making the change (your expertise).
* DRY, as any other principles, are tools to guide you, not rules.


# 5. References

<a id="ref1" href="https://thevaluable.dev/dry-principle-cost-benefit-example/">[1]</a> Cneude, Matthieu. 2018. The DRY Principle: Benefits and Costs with Examples. https://thevaluable.dev/dry-principle-cost-benefit-example/

<a id="ref2" href="https://verraes.net/2014/08/dry-is-about-knowledge/">[2]</a> Verraes, Mathias. 2014. DRY is about Knowledge. https://verraes.net/2014/08/dry-is-about-knowledge/

<a id="ref3" href="https://isaaccomputerscience.org/concepts/dsa_ctm_abstraction">[3]</a> Abstraction and automation. https://https://isaaccomputerscience.org/concepts/dsa_ctm_abstraction

<a id="ref4" href="https://en.wikipedia.org/wiki/Abstraction_(computer_science)">[4]</a> Abstraction (computer science). https://en.wikipedia.org/wiki/Abstraction_(computer_science)

<a id="ref5" href="https://sandimetz.com/blog/2016/1/20/the-wrong-abstraction">[5]</a> Metz, Sandy. 2016. The Wrong Abstraction. https://sandimetz.com/blog/2016/1/20/the-wrong-abstraction

<a id="ref6" href="https://blog.ploeh.dk/2014/08/07/why-dry/">[6]</a> Seemann, Mark. 2014. Why Dry? https://blog.ploeh.dk/2014/08/07/why-dry/
