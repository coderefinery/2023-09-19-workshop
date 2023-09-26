+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 4"
+++  
  
## Icebreaker Day 4

- Computer programs are expected to produce the same output for the same inputs. Is that always true for research software? Can you give some examples?
    - if there is randomness involved, the output might not be the same. the randomness might be obvious or less obvious to the user of the software
    - unfortunately I have seen examples where same software produced different results on different computers. on the positive side: you could get really good results if you find the right computer.
    - Random seeds involved means different path but not different results ... depends on what we do
    - If a computer program gives you different results for the same input, it is only trying to tell you that you need to get smarter at what you are doing, OR, trying to do.
    - Sometimes the computer finds a solution on one day and can't find it on another day, even though everything is the same. Not sure why that happens.

- What do you want to be when you grow up?
    - I want to sit in a cabin, read books, drink coffee, write books +6
    - Someone who likes his job, spend time with family :) +2
    - Maybe I don't want to be a grown up +1
    - I want to have my own "side" hustle and help people to live better lives
    - Somehow teaching/mentoring these topics sound fun

- Do you start this week or did you already attend last week (add an "o")?
    - I have joined last week: oooooooo
    - I just started today: oo
    - Last week was a good week and you guys made it more interesting



# Reproducible research
Materials: https://coderefinery.github.io/reproducible-research/

No problem to ask questions also about past week. +1

## Intro - how it all connects
https://coderefinery.github.io/reproducible-research/intro/

## Motivation
https://coderefinery.github.io/reproducible-research/motivation/


- What are your experiences re-running or adjusting a script or a figure you
  created few months ago?
  - Usually these days I'm aware so try to write conservatively - make it obvious how it works.  So somewhat OK, but still might fail (especially if data can't be found)
  - Issues with compiling which took a lot of time to solve again (settings up all the right environment paths)...
  - Often that makes me not too happy about my past self ("where was that script?")
  - Many issues, learned to used archives of databases (like biomaRt), instead of using standard approach (newest version), as they may be updated from manuscript submission to first revision
  - If I only  worked on it myself it is mostly fine. However, the moment my project is with 2 of more people... Yep, this gets problematic soon.
  - Add some many comments +1
  - Jumping between sub-projects is hard unless fully documented
  - Well, as it goes wrong usually, I learned to put notes ... better too many than too few :)

- Have you continued working from a previous student's
  script/code/plot/notebook? What were the biggest challenges?
  - Yes. I got the code but had to reverse-engineer how to run it from non-existent or outdated documentation.
  - Once someone told me "best projects are tiny things you can write yourself from scratch... trying to use someone else's thing goes badly".  I've mostly done that, but haven't gone very far then.  Trying to use someone else's has usually gone badly
  - Genuinely understand what the code does, had to little comments. What do the acronyms stand for.
  - (share your experience, but constructively)
  - The largest problem for me is figuring out what the other person wanted, this can take weeks.
  - yes, it was a massive code with a lot of modules ... few notes on the code ... I wasted my time trying to find my way in it ... Unfortunately, This code was wery well written but because the documentation was inexistant, I dropped it.
  - In a country where even the postal service does not work ... well, ... what is to be expected ...
  - Pb with libraries that do not exist anymore ... no environment were available so I had to update the script with new libraries
  - Trying to match sample names from different parts of a collaborative project should not be a problem, but people always feel the need to reinvent the wheel.



1. Supposably I want to add my post-processing Inkscape steps, would I write these instructions as comments in the open-sourced code? or README.md? or somewhere else?
    - If it's manual work, I would describe it in the README. But really it's a question of preference.
    - What about "as close to the place it's used, where someone is most likely to see it?"

2. On the organizing part, I looked at your project directory. In my case, my data is over 400GB. So what I typically do is keep my data in another, fully separate folder (or even machine). I will always put a small example data folder in the project folder, but it is not possible to do this for the real research data. (Although we have a separata research data storage solution at my university, especially for reproducability)
   - I definitely agree with this!  Very good idea.
   - This is a good idea. I would add the doi of the data if it is published or source in readme 
       - Yep thanks. I typically also have the input files + software/version with which I ran the simulations in my project folder as well. :+1:
   - this is great practice. it really helps the next person to have small example data close to the rest.


## Discussion: How do you collaborate on writing academic papers?
- Are you using version control for academic papers?
  - I try but most others have resisted.  At least overleaf used to let me pull with git.
    - has the git integration disappeared? I also remember that I could clone. 
    - I think it might be a paid feature now?  Haven't had to use it in a while
  - Google doc as it is good for both biologists and bioinformaticians and you can track changes and get versions from certain dates +2
  - I have been using Overleaf for 5 years now
  - (share your experience)

- How do you handle collaborative issues e.g. conflicting changes?
  - (laughs).  At least overleaf works?  I used to make a branch, send a version to someone, when it comes back put it in that branch again and merge the branch.
  - ...
  - (share your experience)
- What tools are you using when organizing your projects?
  - Files and directories?  git?  Nothing fancy.
  - ...
  - (share your experience)



## Recording computational steps
https://coderefinery.github.io/reproducible-research/workflow-management/

:::info
### Exercise Workflow-1 and Workflow-2, until xx:00 (then break until xx:10)
https://coderefinery.github.io/reproducible-research/workflow-management/#exercise

- Prep: as show, clone the word-count repo as we learned last week
- Make sure you change directory into the word-count directory (`cd word-count`)
- Workflow-1: is doing it manually
- Workflow-2: is doing it automatically.
- Try to do all of them

:::


3. Should we go over the conda env activation in more detail?
   - it was a big quick, especially since we did not use this in week 1
   - The basic idea: by activating it, the software we installed before becomes available to you.  `conda activate coderefinery` should do this.  There is some initial step to be done that should have been covered in [the installation instructions](https://coderefinery.github.io/installation/conda/)

4. Should we clone this into a "coding" folder that was made last week, or just into the main folder?
   - it's up to you!  Into the coding folder would make sense to keep workshop stuff together. 
       - thanks!

5. (I guess you found it!) (I realized it was the group leaders work to help me ;\) )

6. Somebody else get an error using binder? 
   YES
    - Can you paste the error message here?
    ``` Removing intermediate container 47481a3fce60 The command '/bin/sh -c TIMEFORMAT='time: %3R' bash -c 'time ${MAMBA_EXE} env update -p ${NB_PYTHON_PREFIX} --file "environment.yml" && time ${MAMBA_EXE} clean --all -f -y && ${MAMBA_EXE} list -p ${NB_PYTHON_PREFIX} '' returned a non-zero code: 1```
    - I am trying to reproduce the error :)
    - Ok it seems that Binder has some issues running the most recent Python 3.11 since few weeks ago. https://discourse.jupyter.org/t/mybinder-stopped-working-for-repo/21170/3 Right now in the [exercise repository](https://github.com/coderefinery/word-count) we do not restrict the version of python to be smaller than 3.11 and that causes the error. We will comment on this after the break as this is related to the environment.

7. Note about the exercise description: The line `Somebody wrote a script (script.sh) to process all 4 books:` is a bit vague, it could maybe be more explicit? (Create a script file called `script.sh` and copy paste the following shell script there.)
    - good point. bonus points to the person who sends a pull request to improve the text: https://github.com/coderefinery/reproducible-research/edit/main/content/workflow-management.md
    - should the script be included in the repo?
       - but the script is just below that line. maybe I misundestood the question. the script that "somebody wrote" is that Bash script containing the comment "# loop over all books"

8. I can't run the snakefile, "Missing output files: statistics/last.data" ..? 
    * are you sure it is not actually running? Did you get some green text in terminal and do the outputfiles in plot and statistics exist?
    * Snakemake tells you reasons for running each of the jobsteps and what you posted above sounds like one of these reason-texts :thinking:
    * Hm... haven't figured anything out yet.  Any other messages?

9. I had another possible improvement to the code/assignment. From a reprodusability point of view, having all code snippets in their respective folder is somewhat frustrating and unclear. It might be better to have them at the same location (count.py, plot.py ect.) and make them write their results to the folders that the folders dat they are in right now. (of course with comments stating where you will make it read/write from/to). 
     - thanks! yes, I agree, I would probably also put them all in the same folder (but to be fair I also might have created that exercise example but I am now unsure why it was split into several folders)

10. How often should one use snakemake? is it recommended to have it for every step of a project and the entire project?
     - it is a useful tool for a project that requires multiple steps run on multiple similar input data

11. Does anyone have any reccomendations for workflow platforms in neuroscience? Does snakemake work well there too?
     - Snakemake is a good one to start with. It also depends on the scale of the project, if the same script has to be run for many subjects for example. I have also seen people coding their workflow with https://pydoit.org/ and some excellent neuroscience papers have released full containers with pipelines to get insipration from, for example: https://www.nature.com/articles/s41586-020-2314-9

How did the exercise go?
- I'm a bit confused on how the workfflow in snakemake goes, its is a bit hard to follow on what the environment variables are and in what order instructions are done.

### Recording dependencies
https://coderefinery.github.io/reproducible-research/dependencies/

12. Can't one generate such an enviroment.yml file automatically using tools? (which ones again?)
     - yes you can! have a look at "(optional) Dependencies-2: Create a time-capsule for the future" box on the same page below.

:::info
### Discussion: [Dependencies](https://coderefinery.github.io/reproducible-research/dependencies/#exercises)
A: couble of libs in code: 
     - trial and error?
     - This is always quite annoying.
B: README list: 
     - Manual work but at least there
     - High chance that it isn't kept up-to-date in the future.
C: environment.yml: 
     - works but might change in the future?
     - Is changing good since you get automatic updates?  Or break things?
D: environment.yml with ...:
     - I like this one since it specifies which packages are required, including the version. Also, it signifies the dependency on other (GitHub) packages with the version it was 3 years ago. However, you assume that the user has tagged the right commit. 
E: environment.yml with ...
     - Seems to have everything.  Requires sub-projects to be released *and* added to conda?
     - Maybe doing full release for everything is too much to expect, too?
::: 

13. How can you make a package? like student E?
    - depends on the language. would this be a Python project? if yes, I personally use https://flit.pypa.io/ to package and upload to PyPI. To publish on Conda I would look at conda-forge. They have excellent documentation.
    - For Python, I like to use the [Python](https://packaging.python.org/en/latest/tutorials/packaging-projects/) documentation that explains each step
    - A follow up course we might advertise is "Python for SciComp" and we have a mini-tutorial there: https://aaltoscicomp.github.io/python-for-scicomp/packaging/
    - In general, it can take a bit to learn how to do this, but it's really useful!  even if you don't release officially, being able to do `pip install https://github.com/YOU/YOURPROJECT/archives/main.zip` is pretty useful!


14. Are conda-forge and PyPi equivalent? Which one is recommended for package publishing?
    - similar idea but PyPI is more for projects that are meant to be included in other Python projects. Conda is more general and also used for projects that have nothing to do with Python. but similar concept.
    - conda was made for complex libraries that also needed compiled code, but is now common in science in general.
    - Usually things go to PyPI first and then conda.  PyPI may be a bit easier (and also usable from conda), so start there I guess?

15. Doesn't pip also have versions? As far as I understood, a good practice is to define versions of python libraries in the environment.yml file. Should we also mention pip versions, if there are such?
    - yes it has. but can you please clarify your question? (I got distracted and did not hear the stream so I am unsure what statement this question refers to)

16. what is the difference between conda and container(Docker)?
    - conda is a way to track, isolate, and document dependencies of a project. but sometimes dependencies go beyond the library dependencies. some codes depend on the actual operating system and have system dependencies. in this case the conda environment might not even be enough. so a container goes beyond that and not only tracks the code dependencies, but packages the entire operating system with all system dependencies also.


## Recording environments
https://coderefinery.github.io/reproducible-research/environments/

Discussion: Have you ever come across containers? Docker? Singularity? Apptainer? Podman?
- I started coming across them when deploying web services.  At first I didn't quite like the idea, now I see they have some good uses.
- Yes and I found that there is a big difference between Docker and Singularity. On HPC systems usually they won't let you use Docker, while you can usually work with Singularity. The difference is I suppose that the first one touches on OS, while the other is fully isolated.
- I have heard it multiple times, but didnt know what it was up until now (sort of)!!

:::info
### Exercise: Containers-1 (here) and 2 (at home), until xx:00
https://coderefinery.github.io/reproducible-research/environments/#exercises
- You don't need to use the container yourself (that's a lot of install and setup), but you review the existing container
- Wrap up at xx:00, then lunch.

:::

16. If containers also allow other operating systems, is it fair to compare them to something like a virtual machine?
    - Purists would say "different", but yeah, practically somewhat similar.  (it shares a lot more than a virtual machine: the kernel, filesystem mounts, and a lot more of the basic operating system services.)

17. At what point do you stop using the container? Eg: a project was created 5+ years ago with specific conditions, but when would it be time to move to updated versions of everything?
    - it's time to update the environment as soon as I start changing also the code. or to take advantage of updated libraries and dependencies that offer better/faster/... functionality.
    - If it is code that you plan to reuse often, keep it up to date across versions of other libraries. 
    - Containers are also useful about carrying the code around various systems, sometimes we are not allowed to install anything in some systems but we can bring the container with us.
    - This is actually a good phisolophical point: is the purpose of containers so that you don't ever have to update the environment?  Or so that you can re-create it easily?  Both are done... and too many containers do last so long and can't be reproduced anymore

18. Is image another word for container?
    - Oh yes.  Good point.
    - at least docker uses this specific terminology: "image" = the data of it.  "container" = one instance of the container actually running.  But I tend to use them interchangably, which might not be the best.
    - And are they both interchangable with "environment"?
    - "environment" is more a term we are using here for the general idea of "where the code runs".  It can mean many things: conda environment, virtual environment, I guess even "running in the container's Python environment".
    - This makes sense, thank you! :D

19. Are containers usually used to "publish" code rather than during development, if not, how are they usually used during development?
    - Sometimes yes, they are used to publish code.  I'm not sure if it's a good idea, but it is effective and solves some certain problems.

::: info
# Lunch until xx:00
:::

## Social coding and open software

https://coderefinery.github.io/social-coding/


20. Has anyone watching ever *not* distributed one of their own codes, because you realized you didn't have rights to?

### Social coding
https://coderefinery.github.io/social-coding/social-coding/

## Question 1: Why would I want to share my scripts/code/data?

**Choose many**. Vote by adding an `o` character:

- A: Easier to find and reproduce (scientific reproducibility)
  - votes: ooooooooooooooooo
- B: More trustworthy: others can verify correctness and find and report bugs
  - votes:ooo0oooo
- C: Enables others to build on top of your code
     (derivative work, provided the license allows it)
  - votes:oooooooooo
- D: Others can submit features/improvements
  - votes:oooooooooo
- E: Others can help fixing bugs
  - votes:ooooooooooo
- F: Many tools and apps are free for open source, so no financial cost for this
     (GitHub, GitLab, Appveyor, Read the Docs)
  - votes:ooooo
- G: Good for your CV: you can show what you have built
  - votes:oooooooooooo
- H: Discourages competitors. If others can't build on your work,
     they will make competing work
  - votes: o
- I: When publicly shared, usually we time-stamp or set a version,
     so it is easier to refer to a specific version
  - votes:ooo
- J: You can reuse your own code later after change of job or affiliation
  - votes: ooooooo
- K: It encourages me to code properly from the start
  - votes: ooooooooooo


## Question 2: The most concerning thing for me, If I share my software now

**Choose one**. Vote by adding an `o` character:

- A: It will be scooped (stolen) by someone else
  - votes: ooooo
- B: It will expose my "ugly code"
  - votes:ooooooooooooooooooo
- C: Others may find bugs and mistakes. What if the algorithm is wrong?
  - votes:ooooooooo
- D: I will get too many questions, I do not have time for that
  - votes:oooooooooo
- E: Losing control over the direction of the project
  - votes: oooo
- F: Low quality copies will appear
  - votes: 
- G: I won't be able to sell this later. Someone else will make money from it
  - votes:
- H: It is too early, I am just prototyping, I will write version to distribute later
  - votes:oooooooooooooo
- I: Worried about licensing and legal matters, as they are very complicated
  - votes:oooooooooo


## Question 3: Why is software often treated differently from papers?

Free-form answers:
- Not counted as citation or proper output.
- In EU law scientific findings are patentable, while it is more tricky or impossible to patent software/code.
- Slightly harder to grasp the purpose of the source code
- The hiring committee maybe looks at my papers but not at my code +1
- Harder to be acknowledged for it.
- ...


## Question 4: When you find a repository with code/library you would like to reuse, what are the things you look at to decide whether you use it?

Free-form answers:
- Is there documentation available? Any examples to see if I can use it for my project?
- Tutorial
- Does it fit my intended purpose?
- Quality of documentation
- Good README file, do they answer to new issues? 
- The quality and structure of the code
- References to the papers based on using this code
- If I can actually run it
- code style / quality
- The example files + the licence + I make a small testcase for myself.
- good comments that I can actually make sense out of the code
- It should be very easy to use and updates should be very recent, then I know that project is maintained.
- Does it generally look like it uses good practices? (gives me confidence in the rest)
- Is it using tools that I can understand?



21. Does anyone have experiences of hiring committes think of code quality and reusability?  (what if it's a big famous code used by everyone?)
    - When hiring for the bioinformatician position I was at least looking at github account, if it existed and had some codes there it was a big plus.

22. I guess there is "derivitive work by using ideas" and "derivitive work as specified by copyright law" ?  I guess that's next lesson.



## Question 5: Which of these are derivative works?

**Choose many**. Vote by adding an `o` character:

- A. Download some code from a website and add on to it
  - votes:oooooooooooooo
- B. Download some code and use one of the functions in your code
  - votes:ooooooo
- C. Changing code you got from somewhere
  - votes:oooooooooooooooooo
- D. Extending code you got from somewhere
  - votes:ooooooooooooooooooo
- E. Completely rewriting code you got from somewhere
  - votes:oooooo
- F. Rewriting code to a different programming language
  - votes:ooooooooo
- G. Linking to libraries (static or dynamic), plug-ins, and drivers
  - votes:oo
- H. Clean room design (somebody explains you the code but you have never seen it)
  - votes:oo
- I. You read a paper, understand algorithm, write own code
  - votes:oooo
- J. I copied code from generative AI and use it as part of my own code
  - votes:ooooo



23. for poll above: what kind of derivative work?  copyright or ...?

24. Could you mention once more which kind of license if often used in an academic context? 
    - instructors often use MIT (permissive) or EUPL (share-alike, improvements must also be published).

25. Is EUPL the only license with share-alike?
    - also MPL and LGPL are very similar. GPL is also share-alike but "stong" in the sense than not only modifications but the combined work

26. We are talking about licensing and modifications, do the (some) licenses protect you against modifications that decrease the code quality or prevent harmful modifications? 
    - Usually they don't cover this, since it's rather arbitrary, and can't actually hurt the original code.  Some have "no advertising" concept which says that original author's names can't be used to publicize derivatives and so on.
    - The ethical considerations are a good point!

27. Is rewriting code derivative work? What does it mean in practice for me?
    - Very good (and difficult) question.  It might be or might now.  Is your re-write using the creative expression of the original (like if you copy line-by-line)?  Or are you deriving from the general ideas.  Relevant wikipedia for info, it's a big thing: https://en.wikipedia.org/wiki/Clean_room_design
    - "Clean room design is usually employed as best practice, but not strictly required by law."
    - In practice: most of the stuff we do is so small it won't matter.  But try to break down to the ideas and re-create without referring to original design.

28. What license does the code generated with ChatGPT have? I am not expecting an answer :) 
    - In EU and US, (I need to double check, I'm not a lawyer) it's not possible to copyright something produced by an AI. So it's public domain. If you want to license it you need to make a significant modification.
    - If the model happens to output some of its training data, the original developer own the copyright. It's up to you to check...
    - And what if you use AI to help translate between coding languages???
      - I think (not a lawyer) that would be derivative work of the original code. The AI is not doing clean room design :smile: But if the original code has a license you can use, the AI would not change that.
      - But the AI output might infringe another code, so you need to check

29. What is wrong with derivative work? As long as you are citing correctly?
    - nothing!
    - copyright derivative work: you have to follow the license of the original.  As long as it's open-source, this isn't a problem.  It's good to build off of others.
    - scientific intellectual derivative work: like you say, you should cite (but this isn't related to copyright)

30. Ethical use of code and licenses?
    - Most open-source licenses don't restrict field of use, and in fact isn't possible under most free software/open source definitions
    - (link incoming) (no link but this is what I wrote before, still looking for link):
        - about "ethical licenses": the relevant term from open-source license discussion is "discrimination against fields of endeavor" - search this to see related discusison.
          It was long ago established that discriminating against certain types of use was incompatible with the open source philosophy for reasons that you can read about. While it sounds good to discriminate against unethical things, it seems practical problems in actually doing that were decided to be too great and thus "discrimination against field of endeavor" is not allowed by any of the major open source/free software definitions
    - point 6 here: https://opensource.org/definition-annotated/
    - (I'm not fully happy with these links)

### Software citation
https://coderefinery.github.io/social-coding/software-citation/

31. Any services for publishing models with DOI/citeability? e.g. LLMs.
    - does huggingface help with this?  (I really don't know)
    - https://huggingface.co/docs/hub/doi#digital-object-identifier-doi 

32. .
33. .
34. .


### Feedback, day 4
:::info
- Tomorrow we talk about documentatation
- Also Jupyter notebooks (you could say this is a form of documentation) 
- The CodeRefinery conda environment is used again tomorrow - along with git at the same time.  It's important that you can use git + conda from the same directory.
:::

#### Today was:
- Too fast:
- just right: oooooooooo
- too slow:oooooo
- too easy:oo
- right level:ooooooo
- too hard:oo
- Exercises were good:ooooo
- I would recommend today to others: ooooooooo
- I wouldn't recommend today: 

#### One good thing about today
- Very nice intro to FAIR princinples, they are more and more important even in classical grant application they more ofte ask how we are going to be following FAIR principles.
- I liked how it was emphasised how we can slowly incorporate these principles over time
- I liked the emphasis on how to share your code environment of a project. I encounter these reproducibility issues regularly.
- It was nice to see how collaborating can work in practice, and how to make sure to keep making reproducible work. Was also nice to hear more about the licenses since that has been quite intimidating - now a bit less so!
    - thanks!

#### One thing to be improved for future days:
- There should be more in-depth/interactive assignments during this day. Now it was a little too passive. +1
- I would make it in a bit faster pace.
- I wish there were more exercises, compared to last week there was not much benefit being part of a group
    - we're sorry about this, but it'll get better tomorrow!
- I would like to know how Singularity could work an the HPC cluster. 
    - See two points below - sort of similar.  Would a demonstration be exciting enough?  (also it depends a lot on the cluster!)
- Maybe additional information about the difference between setup.py, requirements.yml, toml files etc. to specify dependencies for packages. However, this may be out of scope for this course +1
- It could have been fun to try making an environment/image
    - thanks!  We have tried this in the past, but there were so many setup requirements that most people couldn't do it.  Any ideas for how to make it possible?
    - Is environment-ception possible..? Making an environment, within the coderefinery one? :D

### Any other comments?
- I feel like I have a better understanding overall of how everything comes together - thank you for today!
- Thanks! I really appreciate how self-contained the written docs for the course are, it's hard to follow an online course with 100% attention so it's really great to follow when I can and know where I can look to fill in the gaps and find the links to follow up for deeper understanding in the future.
- .
- .

