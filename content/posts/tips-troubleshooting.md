+++
title = "10 Tips for troubleshooting"
date = 2021-07-01
author = "Diego Torres Arguedas"
+++

 
Troubleshooting is one of those things you will do a lot as a programmer. Spending hours finding out the root cause of an issue may sound tedious &mdash; and it is &mdash; but that boost of dopamine you get when you find what's causing a specific problem makes the whole thing worthwhile. The following tips are taken from more than 10 years of troubleshooting:

## 1. Check the logs
This is number one for a reason. Always check the logs. If the issue is in a web app then take a look at the logs in the browser and then move to the logs in the backend or other components. If the software isn't a web application, then identify the components involved and choose an order to check out the logs from inner layers to outer layer or viceversa.

Consider using cloud based logging/monitoring tool such as [Sentry](https://www.sentry.io) or [Log Rocket](https://logrocket.com/) &mdash; they will make your life easier.


## 2. Change one thing at a time

Approach troubleshooting as an exercise of the [scientic method](https://www.britannica.com/science/scientific-method). Observe the problem, identify the possible variables involved, make predictions on how those variables value may be causing the issue, and finally test your predictions **changing one thing at a time**. I cannot emphasize enough how important this is, if you change several things at the same time &mdash; for example variables's values &mdash; you might not come to a conclusion as quick as desired since you're practically invalidating your tests. Soren Bjornstad talks about this on his blog [Debugging & the Scientic Method](https://controlaltbackspace.org/debugging/scientific-method/).

## 3. Identify what may have changed

Whether it's a recent bug or an old one, identifying what may have changed around the time the bug started to manifest is a good thing to do. Did someone installed a new library? Did the version of a new libray get updated? Was new code deployed? Did our deployment workflows just changed? Was a server recently updated? Those are some of the questions you need to ask. Make use of the code repositories log to access the history of changes. If there are a lot of changes between the *version that works* and *the one that doesn't* you can apply the next tip.


## 4. Compare, compare, compare
Comparing two or more sets of code is a powerful tool that might save you some precious time. For instance, if a bug is happening in a specific version of your product &mdash; let's say a mobile app &mdash; but not in the latest version, download both branches of the code and analyse the differences between us. Additionally, this can be helpful while developing new requirements, you can compare two components, stored procedures, scripts, etc to find out what's different in one that makes it fail. 

Comparison tools are quite handy for this. Personally, I've used [Beyond Compare](https://www.scootersoftware.com/) for years. You can also rely on the the comparison features that most IDEs offer nowadays or open source solutions.

## 5. Know your tools
Get familiar with the tools you can use to debug. Debugging is supported on [Visual Code](https://code.visualstudio.com/docs/editor/debugging), one of the most popular IDEs right now. For web, get familiar with [Chrome Developer tools](https://developer.chrome.com/docs/devtools/) &mdash; and not just the console but with the memory analyser and performance tools. Look out for extensions such as [React Developer Tools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en#:~:text=React%20Developer%20Tools%20is%20a,in%20the%20Chrome%20Developer%20Tools.&text=This%20extension%20requires%20permissions%20to,not%20transmit%20any%20data%20remotely.). Regardless of the platform or language  there are tools available to you to help you on this.


## 6. Take variable's values to the extreme
Play with the possible values of a variable, taking it to the highest or lowest value, even to a ridiculous value, and see how it behaves. This is quite helpful troubleshooting issues with CSS, playing with the height or width of a div and see how it's rendered. Actually, QAs use this technique during [Boundary value analysis](https://en.wikipedia.org/wiki/Boundary-value_analysis).


## 7. Remove some code
Once you have hands in the code while troubleshooting, start removing code, e.g.: functions, arguments, modules, while you are still reproducing the issue. What this allows us is reducing the problem to the minimum code required to reproduce it and increasing our chances of success.

## 8. Print out to the console, if needed
Printing out to the console can be quite helpful to identify the different execution paths of a program &mdash; especially in legacy programs or programs without good documentation. It can also help you identify whereabouts an error is occurring, for example, if the program is failing silently you can add console prints at different points of the path and check out what gets printed and what does not.

## 9. Consider other factors besides code
Not always can the root cause of a problem be found in the code. Our code runs in a *context*, identify the characteristics of that context and taken them in to account during your troubleshooting. Consider things like RAM memory, a server's IP, cache, processes permissions, among others.


## 10. Ask *Why* 5 times
Sometimes [talking to a rubber duck](https://en.wikipedia.org/wiki/Rubber_duck_debugging) helps having an Eureka  moment, sometimes what it does the trick is asking yourself the same question several times. As explained in [here](https://www.mindtools.com/pages/article/newTMC_5W.htm#:~:text=The%205%20Whys%20strategy%20is,then%20ask%20the%20question%20again.),
the 5 Whys strategy is a tool for uncovering the root of a problem. Start with a problem and ask why it is occurring, find a good answer to that first question and keep asking until you reach the root cause of the problem.


