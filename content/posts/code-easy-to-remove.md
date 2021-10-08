+++

title = "Code easy to remove"

date = 2021-10-08

author = "Diego Torres Arguedas"

+++


Some time ago I ran into a tweet — one I haven't been able to find since — of someone saying that one of the best lessons they'd learned through the years is to design code that is easy to remove. Initially, that didn't sound natural to me — taking into account the death of our code in our programming process — but now I think that's something we always want to do.


Business needs and context are frequently changing and our code has to adapt to this yet as developers we tend to think of our code as something that will last for a long time — after all we have put our time and creativity into it. We have applied the best practices we know, we've had it readable, scalable and maintainable. Some people might see [throwing away a code base is a sign of failure](https://martinfowler.com/bliki/SacrificialArchitecture.html), but good code is not just easy to understand to others but it's also easy to remove.


[Martin Flower](https://martinfowler.com/bliki/SacrificialArchitecture.html) touches on how in early stages of some systems you might be more focused on delivering features rather than on performance — he says performance is a feature after all, one you need to choose over other features. He calls his trade-off Sacrificial Architecture, which implies accepting that in a few years you'll need to throw away your current code.



The same topic is covered on [How to write disposable code in large systems](https://programmingisterrible.com/post/139222674273/how-to-write-disposable-code-in-large-systems). The author mentions that a way to write easily deletable code is to know when to repeat ourselves to avoid creating dependencies. This is a great application of the [DRY principle](https://www.diegotorres.dev/posts/when-to-repeat-yourself/) and how we should avoid repetition of knowledge — and not necessarily code— in order to ease managing those dependencies in the code.


Another highlight for me of this article is the author's advice on splitting our code by isolating the *hard to write* and the *likely to change* parts from the rest of the code, and each other. He also recommends layering our code, using copy/paste to our favour and breaking our code into pieces.


We could go on and on and name several more good coding practices that will help us write easy to remove code but in the end I think it all comes down to managing **cohesion** and **coupling** in our code and components. I deliberately choose the expression manage cohesion and coupling because even though aiming for a high value in the former and a low value in the latter is the ideal — and to what we aim for — we need to take into account our context; where our business is and what we want to achieve right now. Maintaining a healthy cohesion and coupling levels will help our code be modifiable and removable. After all, good code is also code that can be removed without much pain.