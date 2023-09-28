+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 6"
+++  

  
## Feedback, day 6

### Today was:
- Too fast:
- just right:
- too slow:
- too easy:
- right level:
- too hard:
- Exercises were good:
- I would recommend today to others:
- I wouldn't recommend today: 

### One thing good about today:
- ...
- ...

### One thing to be improved for next time:
- ...
- ...

### Any other comments:
- ...
- ...


## Icebreakers, day 6

### Which tools are you likely to keep using?:
- git, alone: oooooo
- git, group:oo
- github: ooooooo
- pull requests: oooooo
- workflow automation: oooooo
- Sphinx: oo
- Readmes: ooooo
- Jupyter: ooo
- Automated testing(*): ooo
- Modular code(*): ooo
- hopefully more than one

(*) = not yet taught, teaching today

### What tools do you use for testing code?
- pytest +1+1+1+1
- cargo test
- catch2 +1
- GitHub workflow +1+1 (calling pytest, cmake, ...)
- Julia Testing library
- junit (java code) +1
- testthat
  - great! we will show some examples but we might need your help in improving them 
- vitest (Javascript Frontend)
- None +2
- .

### Tell us some about this course:

How did you attend (alone home/work, small group home/work/online, organized group, watching videos later...):
- from office, alone
- library online
- alone home +1
- small group with people from university +1
- alone from office and homeoffice +1

### How do you celebrate after the course?
- Sleep! (instructor)
- going for a mountain hike this afternoon if weather allows 
- Setting up things for the next one (instructor). Getting more sleep, hopefully :smile:
- Update my documentation step-by-step :smile: 
- Start teaching what was learned, and hope that the listener stays awake ... it takes two hands to clap ...
- Implement some of these lessons over the coming weeks/months, celebration wise not a lot +1
- Start recapping and implementing all the things learned :D going for a celebratory lunch 


---

1. Hi, a bit early perhaps. But how do I email my homework for the certificate to this email?: `scip _at_ aalto.fi`
    - you mean what should be included in that email?
    - I mean its not an email adress, so how can I send an email to it?
    - Replace ` _at_ ` with `@`
    - hahah ofcourse, thanks! (stupid of me)
        - There are no stupid questions! There are probably others wondering but did not ask yet :smile:
    - :smile:
        
2. The screen coul be a little more narrow, a bit of text is cut on the edges. Thanks!
    - Is it better?
    - Yes, better, thanks!

3. Is it possible to test for error handling ?? What about outputing specifc error/warning messages...
    - Many testing frameworks can have tests that expect a specific error or an incorrect output.
    - Or you can test that the output is an error code, for example in C.
    - Testing output is quite a bit more complicated. You would need to capture the output from the system. I would make either capture the error before it's printed (if possible), or have the function also return an error/warning code.

4. The example of 'automated-testing' is a python function which starts with test_ , there are also other possibilities through unit-tests libraries etc. I tried to implement this but it seemed like to much work. How to balance this test-complexity vs functionality?
    - Do you mean writing a unit test for every function is too much work?
    - You can start by testing the most important low level functions and testing larger functions that call many smaller ones to have a test for all of them.
        - So like a hierarchy of tests? sub-level and sub-sub-level and level test functions?
    - In general having some tests is better than none
   

5. How do I know if I have tested which lines of code, especially with tricky workflows with a lot of if else...
    - There are tools for this, but it depends on programming language and testing framework. Search for "test coverage" + you unit testing tool
    - For pytest, there is a tool called "coverage"

## Testing

https://coderefinery.github.io/testing/motivation/

### Is not testing ok?

- Jupyter or R Markdown notebook which produces a plot and you know by looking at the plot whether it worked?
    - probably fine not to automatically test
    - Jupyter is quite easily to debug and often the notebooks are rather small (i.e., not a complete package). I wouldn't think it's necessary.
    - In R, there is an R package called vdiffr that helps to look at the difference between two ggplot2 plot and can be integrated as a unit test.
- Looking at the plot is the 'testing' bit. BUT, with 'looking' one may not necessarily be objectively verifying the so called 'obvious', for better or for worse. Further, in the case of 'looking', there is also the question of reproducibility of 'test results', which in turn shows up the issues of accuracy and precision and so on.
- A short, “obviously correct” Python or R script which you never intend to reuse?
- A simple short, “obviously correct” shell script?
- Can you give other examples?
   - something that produces a figure and I can "see" that is correct.


### Discussion: What’s easy and hard to test?

- Give examples of things (from your work) that are easy to test.
    - Mathematical functions such as multiplying arrays that you can easily check by comparing the result with a fixed value
- Give examples of things (from your work) that are hard to test.
    - When making new directories in your program +1
        - I would suggest allowing a base-directory to be set for these kind of tests, and setting it to a temporary folder. A lot of languages do have libraries that allow generating temporary directories in the right location independent of the OS, and that can help. 
    - When the function input is large and complex and requires lots of other functions.
    - I'm not sure if I understand it correctly but I am working with optimization (creating prediction models that should be "the most accurate") and find it hard to come up with a way to test this
        - Tests here could be "the result has to be better than XYZ", e.g. in what we did in linear optimisation in a project was to test that the optimisation result is better than a value that we currently achieve. 
            - I see. I was more thinking of a way to look for coding errors.
                - On a general principle: I would assume, that if I use an external lib (at least if it is anything relatively popular), their code is correct. From this point you could test very small toy-models where you expect a certain result in our optimization and test whether your code achieves this result, try to find edge-cases where you think things might go wrong, and test those.
                    - Thanks!
    - using 3rd party packages or libraries
    - When computation time takes toooo long (more than a day)
        - yes!

6. What is the difference between regression tests and "end to end tests"?
    - Yes the concept is somewhat similar. And in the end any "test" is a regression test, since if a code change breaks the test you notice. 
    - Are all tests "regression tests" then?
    - For me it is the same thing in practice.
    - Essentially: Regression tests are tests that keep your functionality intact based on previous results, while End-To-End can also be tests with previously known information
    - The focus might be on having a correct result or the focus might be on not introducing changes in the results. In practice we want both but sometimes we only have the preserving part.


:::info
## Exercise until xx:40

https://coderefinery.github.io/testing/pytest/#exercise-pytest

Goals:
- run pytest locally
- try to then break the code
- run pytest again and see whether it detects the error
- if you have time left and Python is not your langauge, try to do this in your programming language
:::

7. One of the keypoints is: "pytest collects and runs all test functions starting with test_. If run on a directory, it collects all files matching test_*.py" My question: would you often write test functions within the same file/directory/package or would you make separate file with all the test functions?  
     - good point, you can run pytest on a directory, a package, or a file. Personally I like to keep test functions close to the code in the same file because it helps me "understand" them. I think most people and most projects I see prefer to have test functions in a separate file but then I need to jump between files if I want to change things. I see tests as documentation, not only as safeguard.
    - Depends a lot on whether this is a small script or a package. For a package I would separate them, as it's then a lot easier to ship a smaller bundle. For some small scripts putting them in the same file can be easier.
    - For me: very small tests might go in main module.  Once it gets big enough I usually separate them out.

8. Say I have multiple files, e.g. main and utils1 and utils2. In main I import utils1, utils2. I run somethings from utils1, but I don't use anything from utils2. Does pytest in that case still run the test_.. functions from both utils1 and utils2?
    - In the "auto-detect" mode, it would only find tests from files named `test_*.py` - so would do neither
    - If you do `pytest utils1.py` it would do utils1 - or whatever is exactly on command line
    - But this is configurable.  I'd say test and see what happens, I need to refresh myself every time anyway.

9. About Java, what are the testing tools available?
    - I've heard of jUnit, for example, but a web search will probably get you the best answers.  There are probably better ones.
    - good! thank you!




## Automated testing
https://coderefinery.github.io/testing/continuous-integration/
(Demo, you can try this yourself later!)

- Example repo: https://github.com/bast/testing-example


10. Can I also do this automated testing using a similar script when committing locally?
    - Via git hooks, you can tell it to run commands before committing.  That would be how to do it.
    - General Git hooks (`pre-commit` is probably the one): https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks
    - blog post: https://medium.com/@yagizcemberci/automate-unit-tests-with-git-hooks-e25e8b564c92

11. What are some testing tools for R? 
    - testthat. we have an example on https://coderefinery.github.io/testing/continuous-integration/ but I admit that it is a bit complex because R often assumes that you first implement your code as package before you add testing. if you have a simpler example, it would be great to see.
    - ah ok, thank you, good to know!


12. I am maintaining a small package (an integrated extension) to a much larger software package, both of them are availlable on github. Can I create a workflow where I automatically run tests with my own small package when a new version of the larger package is pushed to github/master?
    - One option is to run the workflow manually from GitHub. If you set up the test to install the latest version of the larger software.
    - I'm not sure how one repo can run when another is updated (it would be a nice idea though!).  You can schedule a run so that, for example, it runs every week.
        - this is how we do it right now, but it is quite large/expensive too run, so I am searching for a better solution.
    - How about running a script locally to check for updates. So not on GitHub, but on your own system.
        - If there is a new version, it could push a small change to GitHub (version number, for example), to trigger the test there
            - smart, thanks   

13. Can one do automated testing and install a conda environment from .yml file in the workflow? In the example case we only needed to install pytest in python 3.10
    - With Github Actions, yes, you can - you can do almost anything, it gives you a whole virtual system to work with.  It might take a while to resolve and install...
        - the basic python application action already would take a requirements.yml file and install those packages. but there are conda actions as well.

14. If one wants to do automated testing AND sphinx documentation, would they both go in the same file?
    - I'd usually have two separate files that can run on different triggers.  (though documentation testing (does it build without errors?) can be part of normal testing, too!)


## Test design

https://coderefinery.github.io/testing/test-design/

:::info
## Exercise until xx:45
- Anything from Test Design: https://coderefinery.github.io/testing/test-design/
- "Choose your own adventure" - they go from easier to harder, so choose what you'd like
- Ask many questions and we will discuss when we are done.

How's it going:
- done 1-2 exercises: oooooo
- done 3-4 exercises: oooo
- done 5-8 exercises: o
- done all: 
- not trying:
- this was useful: ooO
- this was not so useful: ooo
:::


15. I have seen terms called "snapshot" and "mock" testing. What is the difference between them ?
    - snapshot is essentially a type of end-to-end testing, where you run the code, take the result and use it to verify that any changes didn't alter it. Mocks (at least in the javascript context) are situations, where you want to test a smaller interactive portion of a larger setup by "simulating" (mocking) the surrounding environment, and just testng, whether the correct functions are called with the expected arguments (e.g. you have one function A that updates an Object b by calling that objects update(data) function. You would "mock" the B.update() function and just check, that the value given to it is what you expect.
    - there could be a mock for a database that the test depends on, right? is that "mocking" in testing?
        - yes that could be an example of mock testing. 


16. I have a question unrelated to testing, but I was hoping I could ask about it anyway. I have a project in python where I am making a map and the file becomes to large to push to github. Is there a way to work around this? I guess the best way is to make the code (or the map file yes) smaller
    - Can the map be generated automatically, instead of including it in the repository?
        - Maybe.. 
    - It sounds like that the map is more like "data" than "code". If you need to keep these data under version control, there are better tools like git-annex which can integrate with external data storage systems (e.g. google drive) but not with github due to size limitations. If the map does not change much and you don't need to track its changes, then just treat it as a separate data file outside the repository.
    - the github repo could include a small example map and for the real run it could fetch it from places like Zenodo. is the map "static" or does it also change very frequently?
        - this sounds like a good solution, and I would actually like to make it dynamic, but it is not at the moment. In in way I would also like to add it to a web-page to be able to share it, but maybe I can do that using git-annex also?

17. I have very limited coding knowledge so was quite tricky, but was interesting to go through the solutions and understand it step-by-step. 
     - thanks! I know it can be a bit too much

18. I saw in the documentation of pytest that you could specify fixtures with a decorator. When would you recommend having a "fixture" instead of making the file dependency itself? 
    - Fixtures are things that can run some code to set up something for a test: for example, make a temporary directory with input files used by different tests.  I'd say they are different things? - you could use fixture for file dependency, but is most useful if there is other setup to do.

19. Is there a way to test multiple test files ? The tutorial only has one test file.
    - yes!  Once you get to that point you'd make `test_xxx.py`, `test_yyy.py`, etc.  `pytest .` or `pytest tests/` would detect everything from that directory.  This is what big projects do.

:::info
## Lunch until xx:00 (12:00 CEST, 13:00 EEST)
- Then "modular code development": https://coderefinery.github.io/modular-type-along/
:::

20. I happen to have a Java code that outputs some results in txt file and then a Python code that does some machine learning analysis. For the purpose of testing (hence code maintenance etc.), is it a good practise to keep them in different sources of code? Or should I combine them in just one piece of code?
    - If the two codes are clearly connected and you would not use them separately, it makes sense to have them in the same repository.

21. Sorry if this is obvious, but in the example where you use monkey-patching, shouldn't the 'monkeypatch' be defined first in order to call `monkeypatch.setattr()` ?
    - thanks! I will look later (now preparing for next lesson)
        - *defined or imported from somewhere? Thanks :) 
    - So pytest has some magic behind the scenes.  When it runs a `test_` function, some arguments are *automatically* added (fixtures), if it detects something of that name.  `monkeypatch` is one of them.  It basically does work as it is, but you won't know what `monkeypatch` does without the reference: https://docs.pytest.org/en/6.2.x/monkeypatch.html
        - thanks :) 



## Modular code development

https://coderefinery.github.io/modular-type-along/
:::info
- Despite the name, this is a demo - sit back, relax, and ask questions!
- You'll see a little script developed from Jupyter to something that is very reusable.
:::


A. What does "modular code development" mean for you?
- ROS is a very used environment for development in robotics :), smalls pieces of code that can be shared and piped together to make a whole system
- Code that can be reused for different projects
- using object oriented programming following SOLID principles so every class and method is usable individually and easily changed without breaking the entire package.
    - [SOLID](https://en.wikipedia.org/wiki/SOLID):
    - Single-responsibility principle: "There should never be more than one reason for a class to change." In other words, every class (and method) should have only one responsibility.
    - Open–closed principle: "Software entities ... should be open for extension, but closed for modification."
    - Liskov substitution principle: "Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it."
    - Interface segregation principle: "Clients should not be forced to depend upon interfaces that they do not use."
    - Dependency inversion principle: "Depend upon abstractions, [not] concretions."
- simplicity
- reusability of code snippits for future projects
- I can copy-paste a part of a code into a different place and it still works
- functions and modules
- Modular programming is a software design concept focussed on separating the functionality of a program into independent, interchangeable modules, which then are the building blocks, and each block contains all the parts to execute one aspect of the functionality. These blocks, aka modules, when put together make up the executable program. The code has smaller, independent, and coherent units that can be easily understood, tested, and modified as required.


B. What best practices can you recommend to arrive at well structured, modular code in your favourite programming language?
- start small and get better.  make it easy to split later, since everything starts small. +1
- DRY (don't repeat yourself)
- Think first jump later

C. What do you know now about programming that you wish somebody told you earlier?
- that I will have to run my code multiple times even for the same project and I will save time and energy by making it modular
- Not particularly "earlier", but "put more emphasis", being first write out like on paper what you want to program instead of starting programming immediately.
- When to use classes and functions (this case in python)
- Less is more
- The huge importance of writing good documentation, as you do your programming
- IDEs (such as VSCode) can be incredibly helpful for writing consistent code according to guidelines of a particular language, with type checking, importing linting, check function definition, git support, and so much more. 
- Follow coding guidlines: like PEP-8, just for readability.
- Go to church on Sunday, and during the fellowship chat with fellow programmers. This will ensure you don't feel you have been the biggest sinner of them all. hahaha +1

D. Do you design a new code project on paper before coding? Discuss pros and cons.
- Not the code, but I do draw algorithm diagrams on paper (or digitally) first. (History learns that I always change it later on, but it helps getting started).

E. Do you build your code top-down (starting from the big picture) or bottom-up (starting from components)? Discuss pros and cons.
- Both, but usually I try to make it do something as soon as possible - whether top-down or bottom-up is easier depends I guess?
- Bottom-up always, to check I am not doing something wrong at each step
- Think global, act local

F. Would you prefer your code to be 2x slower if it was easier to read and understand?
- Depends on how long it runs :)  For some things, yes.
- Yes because I don't work with big data
- absolutely, for my future self and to not be needed for explanations if I share the code
- Processors are designed to run faster, the human brain is designed to read and understand better


22. Could you show the structure of temperature.csv? For thinking of ideas for various implementation or additions
    - there, shown.  I'll make a copy here:
    - Github can preview csv nicely: https://github.com/coderefinery/modular-type-along/blob/main/data/temperatures.csv
    - Year,m,d,Time,Time zone,Air temperature (degC)
    - 2022,1,1,00:00,UTC,-2.1
    - Thanks!

23. Suggestions:
    - [ ] Plot the temperatures of each hour in a day for each day in a month. Each day may have a different color or a different opacity
    - [ ] Write a table that includes the mean temperature value of one year for each year in the dataset 
        - good idea. here we recompute known data few times. 
        - Yes! This actually requires what we've been doing so far since you need a flexible plot function
    - [x] Add x axis label and y axis label. 
    - [ ] Write a function to visualize and save the image, with the flag 'save_plot', if True, then save to the uniform filename and path.
        - This does not work, because after savefig must be plt.show() executed.
        - Moreover, it is better to write a vis function as follow: fig = plt.figure(); ax = plt.add_subplots(111); ax.plot(); ax.set_xlabel(); ...; fig.savefig(); fig.show();
    - [ ] Store all plots under ./images directory.
        - good idea! we might postpone this this time
    - [x] Good pracitce in jupyter notebook is keep all imports in separated cell, to not import over and over again. (By deafult it's ofcourse store in cache, but for more heavier packages it can be annoyin)
    - [x] read the data before the for loop, no need to read for every temp
    - [x] Specify the type of data which function take and return. "def add(a: int, b: int) -> int:"
        - This can be very powerful when using linting extensions in IDEs that already show errors in types before run time ("static type checking")
    - [x] maybe you could make your read_data function sensitive for different headers when reading from pandas. You can add something like `def read_data(nrows, file_name='temperatures.csv', header='Air temperature (degC)')`. To default to the temperature measurement, but make it more adaptable for later use.
    - Better practice is indeed to pass mean as an argument. Otherwise, you would let plot_temperatures depend on `compute_statistics`, introducing coupling that is (in my opinion) not necessary. 
    - [x] should read_data_from_File still return temperatures?
    - [ ] When working with scripts, good practice is to use `if __name__ == "__main__":` directive. All functions should be defiend before, and also function `main()` should be defined. under directive, only `main()` execution and arguments parses should be performed.
        - thanks! we might but it might also be confusing for those who don't write Python but for Python scripts this is good practice
    - [x] Create test functions 
        - that checks whether the mean is calculated correctly (specify a array and check the known mean value?)
            - yes we will do, thanks
    - [x] Add the "requirements.txt" file to improve reproducibility? +1
        - thanks! yes. in a moment
    - [ ] I think that it is included in the pandas code already, but you might want to add a custom `try and except` for the existense of the file and or header. (probably redundant in this case at it is caputred in Pandas already, but this might be good practice for other code parts)
    - [ ] This example is too small, but when to split up the functions and the execution part of the code into different files?


24. JupyterNotebook tips:
    - 'Escape + a' create cell above
    - 'Escape + b' create cell below 

24. Could you also make a function that takes num_measurements as input?
    - thanks! good idea. working on it.

25. could it be savefig() after show() ?  Not sure...
    - +1 show may not be needed

26. yes, .clf() probably clears to prepare for the next plot.
    - thanks


27. Is it possible to add all files ending in ".png" to gitignore?
    - thanks
        - was this now done for all "remaining files" or in general based on the ending of the file? e.g. if I would run it again with a different num input I'd like ti to automatically be ignored
            - I don't remember but ideally the file should contain `*.png` to ignore all PNG files which in this case we consider generated
 
 :::info
 ### Break until xx:05
 - then looking at command line interfaces and modularity outside Python
 :::
 
 Suggestions from after the break - focusing on making it reusable from outside of this one script: as a module, command line, etc:
- [x] Splitting functions into another module
- [ ] (from above): `if __name__ == "__main__"`
    - this would be a good thing to do but we might not to not confuse those who are not using Python. it is a bit Python specific.
        - could you nevertheless explain why/when this would be a good thing? 
        - I'll explain below
- [x] command line interface
    - [x] specify input and output
        - (should these be positional arguments instead of --options)?
    - [x] help arguments
    - [x] options to select date range, averaging, etc.
- [x] make a part of that reusable somewhere else
- [ ] script to run on multiple input files?
    - Better to have it run one thing at a time and script outside (e.g. Snakemake?)
- [ ] Can we have it change to a different colour depending on the mean temps? Eg: cooler temps would be blue, warmer yellow, and hot red
    - oh that would be cool. do you know how?
    - unfortunately not, but I did find this which might be helpful? https://www.freecodecamp.org/news/how-to-change-color-in-matplotlib/ perhaps there's a way to make it dependent on the mean temp
        - You could add a function that takes the mean, and compares the mean to a certain range of temperatures, e.g., 0-10 green, 10-20 yellow, 20-30 orange, 30+ red. It returns the colour. Then you could pass the colour to the plot function.  
        - It would be cool to see if it works!
- [ ] end-to-end test? (yes just running without errors is enough of a test!)
- [ ] Instead of making an integer mandatory at the input, you can also convert all integers of floats to integers (still you need to reject text in some way).
- [ ] Running in parallel?
- [ ] Run on computer cluster? (overkill here but discuss how it's now possible?)
 

28. I didn't know there was a statitics standard lib!
    - I also either forgot or never knew.

29. Comments on Python environments and vscode?  Like how to specify run environment / how it detects the interperter?

30. In Python: `if __name__ == "__main__":` - why?
    - If you `import plot_temperatures.py`, it'll define the functions in it but also *run the script that's in there* - that's probably not wanted when you import something!
    - `__name__` is name of current module, and it is `"__main__"` when you run `python that_scrit.py`.  So you can detect if it's `import`:ed or run as a script
    - So usually you'd do something like:
    - `if __name__ == "__main__":`
      `    main()`
    - and define the script function in `main()`.  Now you can both import this and run it as a script
    - THANKS!

31. How does click compare to argparse?
    - click is sort of nicer since you can define things straight on functions like this.  It's less work and easier to read
        - those arguments are only defined for the function right below the click.command() or can be used for other functions as well? 
    - But argparse is built-in, so doesn't require any extra dependency management
    - So take your pick.
    - both are basically equivalent. if you want to compose libraries that have CLI into something bigger, then click is nice
     
32. Could you share the code that you wrote now?
    - We'll probably post it after the workshop - stay tuned.
    - (next time we should push to Github so that you all can see each time we commit+push)
    - Can see a model from the instructor guide (we didn't exactly follow this): https://coderefinery.github.io/modular-type-along/instructor-guide/
        - Great thanks!

33. How often do you use git from the command line and from VSCode?
    - most of the time from vscode these days

34. Great session after lunch! Really interactive and helpful to see how to approach writing software.
    - thanks!


## Example result

https://github.com/rantahar/plot_temperatures_example


## Outro
https://github.com/coderefinery/workshop-outro/blob/master/README.md



## Feedback, day 6

### Today was:
- Too fast:
- just right: ooooooo
- too slow:
- too easy:
- right level:oo
- too hard:
- Exercises were good: ooo
- I would recommend today to others: oooooo
- I wouldn't recommend today: 

### One thing good about today:
- Loved the interactive coding session in the afternoon, it was very nice to see how others approach a problem and problem solve together :) 
- ...
- Fully coding up a problem and pair programming with comments was great. 

### One thing to be improved for next time:
- I think it would be good to take more time for more complex subjects, e.g., automated testing went by quite quickly. 
- Many threads to follow up on in the future adds a bit to cognitive load, so introducing these later would be great. 
    - yes. I believe the main focus was opinionated in a very appropriate way, covering the majority use cases. Hence completing things is great. 
- Keeping interactivity is probably most engaging.
- Day 3 dropped from being very practical with Git to much higher level, which was a hard change of pace to follow. 
- ...

### Any other comments:
- This was the best workshop I've attended so far. Thanks everyone!
- ...

## Q&A

:::info
- Thanks to everyone who attended!
- Our website and the outro contains follow-ups for the future
- Now we can answer questions about anything
- Instructor Zoom posted for "meet the instructors" after we are done.
  - **Zoom, meet instructors:** https://aalto.zoom.us/j/65754790415?pwd=U3k4UHBod1dpK1g1S0RreXE5ZjVZdz09

### Thank you to all!
:::

