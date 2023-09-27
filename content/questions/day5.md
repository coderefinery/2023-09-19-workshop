+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 5"
+++

## Icebreakers, day 5

### What's the best documented project you've seen?
- https://scikit-learn.org/ +1
- https://docs.dask.org/en/stable/
- https://docs.lammps.org/Manual.html (https://github.com/lammps/lammps)
- https://docs.mdanalysis.org/stable/index.html
- https://docs.xarray.dev/en/stable/index.html

### What makes a project particularly hard to use?
- No information, just code
- Too many pages to read to even get started +1
- Documentation does not match reality
- Documentation does not show examples
- Untrue documentation, where it says: This function does A, by default with a1 enabled. While when you use it, you find out it indeed does A, but by default uses a2.
- The people involved, always.

### What tools do you use for writing code?
- VSCode +1+1+1+1+1+1
- Vim
- Helix
- Spyder +1
- Nano
- emacs
- browser (AI)
- co-pilot
- RStudio +1
- Nano
- Pycharm

### What did you have for breakfast?
- Muesli, orange juice, coffee
- bread with cheeeeeese +1
- rice pudding with jam
- coffee (only) +3
- porridge, cottage cheese, salad
- ruisleipä (rye bread)
- Coffee
- Banana
- Salad + sandwich
- Muesli and blueberry soup
- sparkling water with some salt and lemon juice




## Documentation
Overview: https://coderefinery.github.io/reproducible-research/intro/
Lesson material: https://coderefinery.github.io/documentation/


### Motivation and wishlist
https://coderefinery.github.io/documentation/wishlist/

#### Motivation-1

- Is the documentation important? Why?
   - If anyone (including the original author) wants to use it, yes
- How would you describe a useful documentation?
   - Serves a purpose people actually need?
   - Contains a "Let's get started" section and/or a tutorial that can be followed for <30 min.
   - Provides a clear goal of the project/package
   - Contains a troubleshooting section
- How can you motivate your colleagues to contribute to the documentation?
    - Make it easy?  Minimum work for best impact?  Least redudancy?
    - As close to code as possible?
    - Actually asking and talking about it?
    - Have some sort of basic template with the minimum info they have to provide (packages, versions etc)
- Wishlist for how we would like documentation to be. Let's co-draft a wishlist/checklist.
    - copy- pasteable examples
    - version-controlled
    - purpose: general explenation what the code does
    - contribution guidelines
    - available online
    - for each function|class explain inputs, outputs and how it works
    - searchable somehow
    - how to cite
    - how to create a "Back to Top" link back to TOC or top of README page for long README documents.
    - What's the general status?  under develelopment or stable or end-of-life?  Known bugs?
    - License
    - Citations of things that this software uses
    - "see also": other related software

## Exercise

:::info
### Exercise until xx:40
- goal: README-1 and/or README-2 and/or README-3
- link: https://coderefinery.github.io/documentation/writing-readme-files/#exercise-have-fun-testing-some-readme-features
:::

1. For a person not familiar with markdown, it is not clear were to start doing the exercise. I would suggest adding a link or sthg like that.
    - this is a great resource to learn: https://commonmark.org/help/
    - we have more resources here: https://coderefinery.github.io/documentation/tools/#restructuredtext-and-markdown (but we jumped over that section, we should re-arrange material for better flow)
        - Thank you!

2. Nice README examples:
    - https://github.com/plasma-umass/scalene
    - https://github.com/geopandas/geopandas#readme
    - https://github.com/IndrajeetPatil/ggstatsplot (Not sure if it is good example)
    - https://github.com/matiassingers/awesome-readme (For a list of good README examples)

3. This link: ![picture uploaded about Sphinx link in the lesson material](https://notes.coderefinery.org/uploads/c2ee6aaa-a140-4f25-b7dd-06ab115e01e6.png)
is not working at least on my PC
    - Weird, it used to be correct.  https://www.sphinx-doc.org works though. (extra www)
    - Lesson updated

4. The functions (Note, warning etc) isn't working for me. It seems to render markdown, just not these functions. I even tried to copy and paste it. I'm using the github website.
    - example:
        - https://github.com/bast/experiment
        - source: https://raw.githubusercontent.com/bast/experiment/main/README.md
    - You need to commit it and then you see it on the github project-site in the preview. Otherwise it doesn't work
    - ~~note/warning/etc are Sphinx (MyST-markdown) specific things, and Github markdown rendering doesn't generally know about them so they look weird.~~ never mind, I was thinking of something else.

5. The warning and note functions don't work for me - I think it is because I'm using gitlab? Do they have a different markdown format?
    - Oh yes, Gitlab probably has a different Markdown renderer (It uses Github Flavoured Markdown GFM).  Markdown (beyond basic HTML formatting) isn't standardized at all and generally isn't compatible(!).
    - GitLab has its own flavoured markdown called GitLab Flavoured Markdown GLFM (https://docs.gitlab.com/ee/user/markdown.html)

6. In the GeoPandas example it says "Tests failing" on one of the badges. What does that mean (in general and for us if we want to use it)?
    - We'll see about automatic tests tomorrow morning!  And it will be more precise
    - It means that one of their automatic tests to verify correctness isn't working.
    - If you ask me: I'd still probably use it.  At least they track what works and doesn't, probably every big project has many things that aren't working and we don't know about it.


### Sphinx and Markdown

https://coderefinery.github.io/documentation/sphinx/

We type along with Radovan now: https://coderefinery.github.io/documentation/sphinx/#exercise-sphinx-quickstart
-> In preparation for the exercise

7. The index file can be MyST-markdown also, but by default it's made in ReST so it's easier for this lesson to keep it like that.
    - please show how :-) that's interesting
    - basically a straight translation of the directives.  You'll probably see in lessons, but it becomes `{toctree}` in triple-backquote block.

8. Please slow down :D
    - thanks for informing!
    - (this was also pre-intro, you'll have time during the exercise time!)

:::info
### Break until xx:12
(then return for exercise intro)
### Then: Exercise until xx:40 (we will fill this in after break)
- Sphinx-1 is a good goal
- Optional if you have time left: Sphinx-2, Sphinx-3, GH-Pages-1
- Link: https://coderefinery.github.io/documentation/sphinx/#exercise-sphinx-quickstart
- this isn't needed for the next exercise (but you *could* combine if you wanted)
:::

9. A unrelated question. When trying to set up the whole conda environment initially I couldn't switch into it using VSCode. After experimenting for a bit I noticed I can do it with the normal Windows CMD, rechecking VSCode the default terminal is Powershell, after switching it CMD prompt it works. What is the difference between the two? Why does it not work with Powershell?
    - Hm... so these are the different ways of taking commands and running them in the operating system.  They have different startup methods that can learn about conda and so on
    - Maybe miniconda was originally set up for CMD, so it sets up CMD so that future CMD:s will work for it.  So switching to CMD then worked.
    - It's something we'd need to keep investigating

10. On the website (after using `xdr-..`), it says that my somefeature.md and anotherfeature.md are not found, any ideas? (they show themselves, but when clicked I get the file not found error)
    - just checking (this might not be the reason): you have `myst_parser` installed (you are in the `coderefinery` conda environment)? the `python -c "import myst_parser"` worked for you?
    - I didn't have myst_parser installed it seems, need to check if things work.
         - because plain Sphinx does not know what to do with markdown files and it needs that extension to parse and render them. default for Sphinx are .rst files. But we prefer to show it with markdown. we believe this is easier and this is also what we use in our work.
    - Okay so I am in the (coderefinery) and have ran `pip install myst_parser` and checked with `python -c "import myst_parser"`; but doesn't seem to solve the rendering problem...
        - I would in this case try to remove the "_build" directory and re-run `sphinx-build . _build` again.
    - (thanks for the help ^^) It didn't work unfortunately tho
    - and the files are in the same folder as the `index.rst`? and you have activated the extension in `conf.py`?
    - They are in the same folder yes, and `some-feature.md` and `another-feature.md` are mentioned in the `index.rst` and in the `conf.py` the extension line has been altered to `extensions = ['myst_parser']` ?


11. For the excercise *Sphinx autodoc*, what if the `example.py` is in a subfolder (e.g. `src`)? Somehow Sphinx only creates the autodoc if the file is in the same folder as `index.rst`.
    - good question. we will find a solution (possibly later today) and show an example on how to do that.
        - Thanks!
    - You could try `PYTHONPATH=src:$PYTHONPATH sphinx-build ...`.  This sets PYTHONPATH so it's importable
    - Other things people might do is make it installable and install the code in the conda environment itself.  Really depends a lot.

12. How are those tools (e.g. Sphinx) compared to MkDocs?
    - we will answer on stream but in short: it's the same idea. there are a number of similar tools: https://coderefinery.github.io/documentation/tools/#html-static-site-generators
    - same idea: read markdown, produce HTML

13. Excercise GH-Pages-1: when I clone the `documentation-example` repository, I can't find the `.github/workflows/` folder. I have a `.git` folder, but no `workflows` inside. Shall we create it?
    - yes the folder is created when you create the file `.github/workflows/documentation.yml`, you do not have to create it separately


14. What does the part in the square brackets do: `![alt text](image.png)` ? (not sure how to format it as text. Sorry.)
    - It sets the text that is shown when the mouse hovers over the image, or if the browser cannot show the image.
    - The alt text is originally intended for automatic readers, for example for visually impaired. It should describe the image.
    - (after `0` and `+` there's a button for `´` but with `SHIFT` it starts a code block in markdown)
        - Great!
            - Thanks!

15. I managed to link to a external python file and that worked fine! How can I refer to only one specific python function?
    - Where it says `automodule`, I think you can do specific functions and so on.  I don't know off the top of my head but (surprise) Sphinx documentation is usually pretty good about it.
    - https://www.sphinx-doc.org/en/master/usage/extensions/autodoc.html#directive-autofunction

16. Can I create a Sphinx webpage without making it a public website? For example, if I want to create a tutorial for my colleagues, can I have a webpage like this that is "local"?
    - Yes, in this exercise we build .html and it's not shared anywhere.  you could share it on a private web server - but you need to figure outwhat that web server is and the rest is probably easy-ish.



:::info
### Exercise until xx:40, see above for info
Exercise feedback - how did it go?

- I didn't try: o
- I got stuck: oo
- Completed Sphinx-1: ooooooo
- Completed Sphinx-2 (optional): ooooo
- Completed Sphinx-3 (optional): ooo
- Completed Sphinx-4 (optional): oo
- Completed GH-Pages-1 (optional): oo
:::

17. At TU Delft it went well, there is interest to look at Git pages
    - great!

18. I managed to make it but got the error "Users/myname/code/doc-example/new-feature.md: WARNING: document isn't included in any toctree" and then got a bit stuck after that.
    - Is the new-feature.md in the same folder as index.rst?
    - A typo in filename can also give that error
    - If it's a warning, the rest works.  What it means: it made the page `new-feature.md` but it isn't included in the Table of Contents.  Maybe this is expected but maybe it could be added to a `toctree` directive somewhere

19. The Github Actions part, I just copy and paste but I don't really know much about the commands. Not sure what it is used for.
    - We'll explain now.  It is rather short and direct, it shows the outcome but there is plenty more to learn
    - (but also, many of us go copying around working Actions files rather than understand every bit of them...)

20. I am confused abnout what `sphinx-build . -W -b linkcheck _build` does. From what I understand it should create a local web server, but I can't find where or how to find this.
    - It reads all documents and checks all links: does the URL still exist and return data?  It's used to keep stuff up to date
    - sphinx-autobuild is an extension that *does* make a local web server and shows updates live as you write and save.

21. Is it possible to create Github web pages without Github Action code, should I be unlucky that copy and paste does not work ?
    - yes!  Sphinx works locally (like the first exercise).  But you need to know where you'll be sharing it.  The action builds + uses the Github Pages web server.  Deploying this is a bit tricky... a different set of skills, I'd recommend asking it it doesn't work or trying to copy again something that works
    - (did I answer the right question?) Err ok. I thought maybe I can create Github pages using a click buttons approach (a shortcut/lazy way...) rather than typing complicated command lines (based on trial and error)...
    - Oh I see.  Yeah, you basically need to program it to do things and deploy.  It's good in the end.
    - (you *could* bulid locally and push to a gh-pages branch, and it would deploy that.)

22. How often does Github Actions work the first time? yeah, like you don't need to go debugging it.
    - If you mean, first time after I write one, the answer is rarely. Maybe it's just me, but I always need to debug them for a while :smile:

23. When using GitHub pages, it will also be available online for everyone right? Or is their a way to create a non-local private GitHub page?
    - yes, Github Pages (free version) is public for everyone.  If you get one of the advanced plans, I think they can do authentication.
    - Or you can put it on your own web server and add whatever access control you want (that the server supports).  This would be pretty common, too.
    - (remember we first build the Sphinx project locally, where no one else could see it.  From that stage you can do what you'd like)

25. How did you change the theme?
    - inside conf.py
    - You can find many awesome themes that could be used instead here: https://sphinx-themes.org/

26. The link in the first step of exercise GH-Pages-1 doesn't work for me. How can I then get access to the template?
    - Are yo ulogged in to Github?  The `/generate` part goes straight to a form that needs to be logged in
    - The project itself is here: https://github.com/coderefinery/documentation-example/ (after login there should be a Generate button, that goes to the `/generate` URL)
    - Thanks. Now it works. I was logged in with a different browser than I use for the notes.

27. Thank you for a great morning!
    - thanks!


:::info
### Lunch until xx:00 (12 CEST)
- Then Jupyter
- It's not just basics, but we see how to take it to the next level for reproducibility and
:::

28. I know that it is a little off-topic but does anybody know how we can include code from a file in ***mkdocs*** such as in the example given for sphinx where we used:
    ```{literalinclude} example.py
    :language: python
    :emphasize-lines: 2-3
    ```
    - I don't know, but one of the big advantages of Sphinx is it's extreme extensibility and directive-based nature that allows this.  mkdocs might have this, but there's much more that might be harder.  (the complexity of Sphinx is also probably why it's not used as much as it should be...)

29. How would I add code (with docstring) to the `src` folder now and make it appear in an API section on the documentation page?
    - The exercise Sphinx-4 goes over the basics
    - When there are new files, you might need to re-run sphinx-apidoc to regenerate the template files.
    - And make sure that the right autodoc directives are in the apidoc files
    - And make sure that the code is importable to generate the auto stuff
    - (can give more after lunch)+1 (struggling here as well)


30. Instead of showing code blocks is it also possible to show the output of the code? I'm wondering if it is possible to use this approach to create an online tool of sorts (taking an input and generating an ouput based on that).
    - then the documentation would have to run some code in the background. that is possible. one approach are notebooks. I will look for some examples that do that ...

31. Should I have made a new branch when I added the documentation.yml-file?
    - when I demonstrated it on stream, I committed directly to "main" but creating a new branch and adding on branch and creating pull request would be nicer in a collaborative setting

32. Could you explain a bit the last part of the code to deploy Sphinx documentation to github pages? Specifically what those lines of code mean/do:
  1.`uses: peaceiris/actions-gh-pages@v3`
  2.`github.ref == 'refs/heads/main'`
  3.`github_token: ${{ secrets.GITHUB_TOKEN }}`
  4.`force_orphan: true`
    - (we will explain/reply later, now prepping for next lesson ...)
    - (1) says "use this other action to do some stuff for us": (this one: https://github.com/peaceiris/actions-gh-pages).
    - (2) says "if this is the main branch, do the deployment"  (you don't want other pull requests deployed as the main documentation).
    - (3) tells the action (in (1)) to use the automatically included token to give permission to push (to the branch gh-pages).
    - (4) says "don't keep history of the gh-pages branch".

33. A follow-up question to question 15: I am able to make autodoc API for my functions, but I fail to create hyperlinks to one specific function. I tried the :func:`pythonmodule.func` method, and also \.. autofunction:: pythonmodule.func\. Can please someone help me? Please see [My Doc](https://siebelede.github.io/doc-example/get-started.html#code-explanation) for the code example.
    - `.. autofunction::` is the ReST syntax, not MyST. Try this: `{autofunction} mandelbrot.mandelbrot_set`
    - This is the equivalent MyST syntax, they can be always be translated between the two.  Sometimes you see docs in only one or the other.  (also, it's the main point of MyST-markdown: other markdowns don't generally have this power)
    - Thanks! I will try

35. I have now used the tutorial here: https://sphinx-autoapi.readthedocs.io/en/latest/tutorials.html to generate an autoapi that points to the `src`. Would that be a good solution rather than making manual api.md?
    - ah that is even better! good find.


## Jupyter notebooks

A tool to write and share executable notebooks and data visualization

https://coderefinery.github.io/jupyter/

- That's great! (the intro music) +1

36. Is it possible to change folder viewer to a parent directory?
    - Part of the design of Jupyter is it captures the view in the directory it's started.  You should restart in the higher directory
    - (this doesn't stop the Python processes inside from accessing stuff outside, though!  it's just usability, not security)

37. I think it is basically a table of contents, headings shows up there
    - ah thanks!

38. How do I create a markdown cell again ? I miss it.
    - we will show again in a moment
    - `m` in command mode, there is also a drop down at the top

39. Is there a link to these keyboard shortcut, I will later forget what to press to create/run cells ?
    - https://coderefinery.github.io/jupyter/interface/#keyboard-shortcuts

40. Is there a way to increase the (code/markdown) font for my own notebook ? The one in my computer is a bit small for me to see.
    - Settings -> Theme has options for code/editor/UI adjustments seprately.  You can also try adjusting font of whole web browser (control + or control -)

41. How did you copy the table? When I try it just looks like text.
    - The shorcuts table? I used the [raw text version of the lesson material](https://raw.githubusercontent.com/coderefinery/jupyter/main/content/interface.md) and copy-pasted the table from there. It has Markdown syntax for tables.
        - Thanks!

:::info
# Exercise until xx:45
- Goal: activate coderefinery environment, start jupyter lab, do these:
- "A first computational notebook"

https://coderefinery.github.io/jupyter/first-notebook/#an-example-computational-notebook

How did the exercise go?
- didn't try: o
- went well: oooooooooooo
- too much to do: o
- too little to do: oo
- not clear what to do: o
:::

42. I understand that press ESCAPE goes to "command" mode but is there a way for me to know if I am in command mode ?
    - If it shows you a cursor inside a cell then you are editing that cell.
    - You can try arrowkeys up and down to see whether it moves cursor or code selection (the blue vertical bar)

43. Is there a way to go to command mode by mouse clicking ?
    - Yup! Click between hte blue vertical bar and the cell

44. I cant seem to run the code cells. Instead of a number like this [1], I have a [*] and if I write print('hello') I do not see a result under the cell
    - please tell us what you see instead
    - Markdown cells and "raw" cells don't have the number next to them. Maybe your cell is not a code cell actually?
        - It seems like it was just very slow

45. Is there a way to see what the python variable x, num_points are, like an "environment/variable tab" in MATLAB or RStudio ?  Maybe a way to identify string list, pandas series vs dataframe.
    - There are differen "variable inspectors", let me see what I'd recommend...
    - Help -> Show Contextual Help.  Then you click on anything and it shows the value + help.  (there are others)
    - Under the extensions search "Variable Inspector"


## Notebooks and version control

https://coderefinery.github.io/jupyter/version-control/


46. Sorry, I have just joined the course today. I wonder whether we are going to cover/have covered pushing the Jupyter notebook to github without the outputs?
    - I'm not sure it's mentioned, but there is a git hook for clearing outputs: https://pypi.org/project/nbstripout/
    - By the various `install` things towards the bottom, git will remove output before committing.  warning: it might be easy to forget on a new computer/clone.

47. Is nbdime automatically installed when I download Jupyter
    - I think not. (How do I know if I have it ? Is it a python package ?)
      - how to know whether you have it: in your notebook you can try `import nbdime` - if you see an error, it is not there
    - It is not by default there as far as I know
    - Python package `nbdime`: `pip install nbdime`, `conda install nbdime`, or however you manage packages. it's included as part of the CodeRefinery conda environment

48. When do you prefer using jupyter over just using github?
    - I think they serve different purposes.  Github hosts static files, Jupyter lets you do computing.  They can work well together.

49. Is there a way to export Jupyter notebook as (PDF, .py file. HTML) using the kernel ? I am not so good with command lines...
    - Yep: File> Save and export notebook as.  It should export it how it is here.
        - For PDF I think this is needed: https://nbconvert.readthedocs.io/en/latest/install.html#installing-tex
        - downloading $\LaTeX$ file and HTML file did work

:::info
## Break until xx:07
:::

:::info
## Exercise until xx:30

- Sharing dynamic notebooks on Binder: https://coderefinery.github.io/jupyter/sharing/#sharing-dynamic-notebooks-on-binder

:::


## Feedback, day 5

:::info
### News for day 6
- The last day (day 6) covers testing and modular code development.  These really pull everything together
    - Testing: git is useful and serves as a great summary
    - Modular Code: pulls together all the reproducibility and reusability parts
- The Conda environment is important for Testing.  Modular Code is mostly watching and discussing, so you can relax.
- It's a good time to invite your friends.
- Our credit/certificate instructions have been updated: You can get 1 ECTS Credit OR certificate depending on your situation, if you have followed along and do some follow-up:
  - We have updated instructions at: https://coderefinery.github.io/2023-09-19-workshop/certificates/
  - Deadline to submit your homework: 01/12/2023
:::

### How was today for you?
- too fast: o
- just right: oooooo
- too slow:
- too easy: o
- right level: oo
- too advanced:
- I would recommend this course to others: ooo
- It was good.

### Do you see value in the [CodeRefinery video production (for youtube)](https://www.youtube.com/watch?v=QUAZELOioUY&list=PLpLblYHCzJADyLxv8GRyxFiRJBhQ-G0NQ):
- yes, during the week:oooo
- yes, for future reference: ooooooo
- yes, for taking the course without watching live: oo
- a bit:
- not really, I wouldn't use:

Comments on videos:
- I did not know it existed...
- I would prefer to have the livestream on youtube as well, as there you can rewind live if you missed something you said and want to go back just a few seconds (but I really like that they are uploaded to youtube for future reference)
  - good point!  I should check again if the vertical format works well there.  Last time it didn't that well (lots of borders we can't get rid of)

### One good thing about today:
- music! +5
    - Thanks! 🎶
- exercises were engaging +1
- Yes, engaging and they were usefull. I liked today more than tomorrow.
- Jupyter explanation was very clear
- Another great day! this is one of the best courses I've taken, thank you :)
- Was nice to see how coding can be done collaboratively in projects

### One thing to be improved for next time:
- A demonstration on the Binder exercise, maybe. I didn't get it to work and don't really know what was supposed to happen and what use it would be.
- For the Navigation of the Jupyter notebook is a bit hard for me to follow as I am looking at it at the first time. In https://coderefinery.github.io/jupyter/interface/#navigation for example, is it possible to add some pictures on how "Command palette" or "Cell inspector" look like. Overview picture will be helpful
    - Great suggestion!
- In https://coderefinery.github.io/jupyter/sharing/, maybe will be helpful to include the mouse clicking way to export/share Jupyter file to HTML, PDF, etc. Most of us may just want to export quickly and send the results to their manager by email.
    - There could be a screenshot 🤔
    - in question 49:
        - For PDF I think this is needed: https://nbconvert.readthedocs.io/en/latest/install.html#installing-tex
        - downloading $\LaTeX$ file and HTML file did work

### Any other comments:
- I could not make last exercise, I have no idea how to copy notebook to github/binder, I was lost there... Probably my fault, not the tutors :)
  - thanks for feedback. to get a notebook on github you can use the "add file" button on github. once it is on github, you visit binder page and place the link to github repository.
  - Ok, thanks I understand that I have to copy all the code from notebook and could not find the option to copy raw code.
    - Not sure if there is a way inside Jupyter.
    - The easiest way propably is in github to use this "add file" button. There you can add any file directly to the repo. You will find the notebook file inside the folder that you launched Jupyter in command line in the very beginning
    - Not sure if it works for you. Click File -> Download will output the json one. Click File -> Save export notebook as -> Markdown will output code as well...
        - I think it's then not in .ipynb format (at least not if it is markdown ie .md) and then Binder cannot open it as notebook.


50. I've seen jupyter notebook being used in coding courses as material, so that the markdown parts and some code parts are fixed, non-editable, but students can edit certain code cells to do exercises and try out things. How is that done?
    - There's some metadata that can tell the editor "don't let this be editable".  https://stackoverflow.com/questions/18162970/read-only-cells-in-ipython-jupyter-notebook
    - (but it's just a user interface thing.  the user of course has access to the raw file so can do anything they want that way - this doesn't make it more secure.)

