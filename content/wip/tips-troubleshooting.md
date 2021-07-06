+++
title = "10 Tips for troubleshooting"
date = 2021-07-01
author = "Diego Torres Arguedas"
+++

 
Troubleshooting is one of those things you will do a lot as a programmer. Spending hours finding out the root cause of an issue may sound tedious - and it is - but that boost of dopamine you get when you find what's causing a specific problem, makes the whole thing worthy. The following is a list of tips I usually take when troubleshooting:

## 1. Check the logs
This one is number one for a reason. Always check the logs. If the issue is in a web app then take a look at the logs in the in the browser and then move to the logs in the backend or other components. If the software isn't a web application then identify the components involved and choose an order to check out the logs - from inner layers to outer layer or viceversa.

Consider having in place cloud based logging/monitoring tool such as [Sentry](https://www.sentry.io) or [Log Rocket](https://logrocket.com/) they will make your life easier.


## 2. Change one thing at the time.

Approach troubleshooting as an exercise of the scientic method. Observe the problem, identify the possible variables involved, make predictions on how those variables value may be the causing the issue and finally test your predictions *changing one thing at the time*. I cannot emphasize enough how important this is, if you change several things - variables's values - at the same time you might not come to conclusion as quick as desired since you're practically invaliding your tests. Soren Bjornstad also talks about his blog post on his post on [Debugging & the Scientic Method](https://controlaltbackspace.org/debugging/scientific-method/).



## 3. Identify what may have changed

Whether it's a recent bug or an old one, identifying what changed around the time the bug started to manifest is a good thing to do. Did someone installed a new library? Did the version of a new libray get updated? Did the server was just updated? Did new code was deployed? Those are some of the question you'd need to ask. Make use of the code repositores log to access the history of changes. If there are a lot of changes you can apply the next tip.



## 4. Compare, compare, compare.
Comparing two or more sets of code is a powerful tool that might save you some precious time. For instance, if a bug is happening in a specific version of your product  - let's say a mobile app - but not in the latest version, download both branches of the code and analyse the differences. Additionally, this can helpful while developing new requirements, you can compare two components, stored procedures, scripts, etc to find out what's different in one that makes it fail. 

Comparison tools are quite handy for this. Personally, I've used [Beyond Compare](https://www.scootersoftware.com/) for years. You can also rely on the the comparison features that most IDEs offer nowadays.

## 5. Know your tools
Get familiar with the tools you can use to debug. Check out Debugging is supported on [Visual Code](https://code.visualstudio.com/docs/editor/debugging). For web, get familiar with [Chrome Developer tools](https://developer.chrome.com/docs/devtools/) - and not just the console but the memory analyser and performance tools, look out for extensions such as [React Developer Tools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en#:~:text=React%20Developer%20Tools%20is%20a,in%20the%20Chrome%20Developer%20Tools.&text=This%20extension%20requires%20permissions%20to,not%20transmit%20any%20data%20remotely.). Regarless of the platform or language most likely there will be tools available to you to help you on this.


## 6. Take variable's values to the extreme
Play with the possible values of a variable taking it to the highest or lowest, even to a ridiculous value, and see how it behaves. This is quite helpful troubleshooting issues with CSS, play with the height or width of a div and see what happens. Actually, QAs use this technique during [Boundary value analysis](https://en.wikipedia.org/wiki/Boundary-value_analysis).


## 7. Remove code




## 5. Binary search.



## Bonus. Did I just copy




## 1.4 5 Whys.

https://kanbanize.com/lean-management/improvement/5-whys-analysis-tool


## 1.6. Consider other factors besides code.
Infrastructure.



## 2.2 Do a Binary search using console logs.


## 2.3 Eliminate code

Recude the problem down to the minimum of code required to reproduce it.


In a React component or a method, if it receives 8 inputs or props, try leaving all of them fixed but one and check the outcome. Repeat.


## 2.5 Start again
Delete the code, install libraries again. Believe sometime it just happens.

## 2.6 Try things more than once.


Remember that memory is a factor




Any comments? Please let me know