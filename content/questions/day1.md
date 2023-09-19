+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 1"
+++

## Icebreakers

### What's your favorite fruit?

- (you can write here by clicking pen button on top of page)
- watermelon +1
- guava
- banana +1
- pineapple
- green apple
- tomato
- orange
- passion fruit +1
- melon +1
- the forbidden fruit
- blueberry
- mango +4
- strawberries
- persimmons +1
- Grapes +1
- Nectarines
- avocado
- raspberry
- pear (in the right season)
- kiwi
- Mango +1
- grapefruit


### How do you use computers in your work?

- actively +1
- Genomics +1
- for everything +1
- for almost everything, but mostly data preperation and analysis
- data analysis
- a lot
- image analysis
- programming robots
- For research and writing codes
- pre- and post-processing molecular simulations
- Latex
- for research, modelling, data analysis
- Processing data and making nice graphs, writing
- mostly data analysis and research
- for bayesian analysis
- I put it on a table, mostly
- Clean and harmonise clinical data
- brain imaging, statistics


### If you use Git or version control already, what aspect do you find most confusing/surprising?

- if I run a command, where does it save things
- How to work efficiently with remote repository for example pull, rebase etc.  +1
- I am afraid to do something wrong
- How to use branches
- How to solve conflicts? ditto +1+1
- Forget to commit regularly +1
- Took long time to understand the concept
- How to find open source projects that are not too complicated to collaborate?
- how to avoid conflicts in collaborative branches
- If I make a change does it change it for everyone?
- committing to some other bigger projects on github (how forking and branches work)
- First, loging each time you want to push, and, merging conflicts and divergences
- using github for windows is easyer
- I mainly use git in VScode, so the commands and all the possible flags I don't always understand (force, force-with-lease, etc)
- I butcher git, I use it for filesharing over different clusters (with gitignore, you can easely ignore files you don't need to postprocess :)
- Why should I use git from terminal instead of something like GitHub Desktop?
- Create a repo from a local folder that has already lots of files and subfolders
- Creating an empty repository, especially in cloud services like gitHub and gitLab
- the most surprising thing is how the whole operating system works together with git


## Introduction to the workshop

https://github.com/coderefinery/workshop-intro/blob/master/livestream.md

1. Why are questions numbered?
    - so that we can sometimes refer to an older question

2. What if we lose count?
    - Don't worry, we will follow it (and try to keep it correct, but worst case we will update them in the archive)
    - it is not a big problem if they are off

3. Is audio clipping?
    - There's some slight distortion in RB's voice -MJ
    - and is it balanced?
        - Yes


## Intro to version control

https://coderefinery.github.io/git-intro/motivation/

4. Does the blame/annotate works for other programming codes besides Python ?
   - Yes! It just goes through the files line by line, so it works best with text-like files.
   - If the file is a binary, `git blame` will point to the whole file instead.

5. How can you get the permalink for a specific line? right click in blame?
   - This depends on what user interface you are using. Is the code in a cloud service? (Such as GitHub, GitLab or similar)
     - Yes, through the github interface (or through CLI if that is possible, though mostly through a cloud interface)
        - On GitHub, open a file and click on the line number. Then Click the three dots next to the line number and choose "copy permalink".
          - Got it thank you!!!

6. Most of the nice features of version control only work with text files, right? (i.e. putting a word file into Git is possible, but suboptimal)
    - yes. Any "binary file" is not a really good "target" for this type of version control. But you can still do it to e.g. keep versions in sync, like a doc file describing a tool with the actual code in the tool (even though I would choose a different way of documentation :) ).
        - This will become clearer when we understand how `git diff` works. In a way, though, track changes is already a sort of version control for Word files, for example. Also mind that all files are in fact binary: the distinction is between those who are human-readable "straight away" and those who encode information that you are not supposed to read.

7. we canot see his screen
    - Sorted.


## Git basics

https://coderefinery.github.io/git-intro/basics/

8. When instructor said, that the global flag affects everything in the computer, may be better to clarify. For the furture repos everything will take affect, but some settings will not affect how old (before issuing the command) will behave. For example the email used in commits will not change in repos created before the change.
    - It will affect all the Git repositories, unless you have other "local" settings. "Local" settings override "global" settings, which override "system" settings.
        - Good point, the global settings can be overidden by local settings.

9. Do these setting matter when I'm both using (my private) GitHub and (my institution's) GitLab?
   - Yes, all your commits will contain the name and the email you add here.

10. Visibility of the console window is still not perfect, the edges are off the screen
    - better or more?
      - Perfect now ♥

11. I needed to add a --wait after the core.editor to be able to commit changes. Is this depended on the editor? I am using VSCode.
    - It depends on the editor (But I have not had this issue with VSCode)
    - If you scroll down this page, you can find a list of commands to configure various editors: https://swcarpentry.github.io/git-novice/02-setup.html
    - Please also see our install instructions: https://coderefinery.github.io/installation/

12. how do I exit the list after the `git config --list` command
    - press `q` for quit. You will exit the list. Great thanks!

13. How to exit the text file? OR save it?
    - to save it `ctrl+x` -> y -> enter (if you used the `nano` editor)

14. Do you have to save the file before closing?
    -  Yes, if you are happy with what you added there. Otherwise it won't save the changes you did. Nano will ask you "do you want to save?"
    -  ctrl O (stylised as ^O) is the save operation (from write Out); after saving you are asked to confirm the file name; you still are inside nano; to leave nano type ^X for eXit. nano is an old piece of software, so it brings you a bit back in time as to functionality. This is a precursor of the modern graphic user interfaces: note also that when you have nano on the terminal, you don't have the shell.

15. Maybe it's good to show the files you generated in the system file explorer. Just to show people what's happening.
    - Thank your for the feedback.

16. Could you recommend some good code editors at some point of the course? I unfortunately do use nano for a lot of stuff
    - This is very much a personal question. There are several editors specific for a certain language (like e.g. RStudio for R, PyCharm or spyder for python or the Matlab editor for matlab) or general purpose ones like VSCode, eclipse, emacs. But it really depends on what you want.
    - My personal opinion: If you like (or have to) work from the terminal (e.g. on a remote server), vi or emacs have more features. Otherwise VS Code is a great tool.
        - Comment here: vscode has remote plugins that allow usage on a remote system.
    - Thanks!
    - we are considering to maybe in future recommend VScode to start with instead of nano. Advantage of nano is its availability also on clusters.

17. Looking at the `git help commit` command, isn't it much easier to use git commit --help (go to the overall help weppage) or use git commit -h (getting a shorter version in the terminal)?
    - Good input. Indeed, it is easier, but it depends if you find the information you need. It is better to start with a shorter help page and move on to something more elaborate if needed.

18. For now, the repository only exists locally right?
    - Indeed.

19. Is it possible to make RB's audio break a little less?
    - RB: can you please describe how it sounds? trying to trouble-shoot
        - it is distorted and picks up the room quite a lot
            - thanks, working on it
                - there is no easy fix for the room but maybe just try to lower input a bit

20. As a good practice, we are suggested to commit often. I wonder if it does not store (use) lots of my space for example in Github? Each commit is an image of the working dir?
    - Only the changes are stored, so committing often is not an issue.
    - Especially as a beginner, it is recommended to commit often. Later on we're learn how to "squash" several commits into one. This makes the log history shorter, but it should not be used if you shared your local repository with others/GitHub.
        - In this case, do not I get lost in lots of nano commits? Especially, if I am working on a project daily and commit everyday? For exampling, in case, I want to find a bug?
            - I agree it may be tricky, that is why "squashing" (using `git rebase` for example) the last couple of commits may be handy. But if you do have many changes in one commit, it will be harder to debug your code in case you discover an error. You need to find the right balance for your project/style.
            - For us, branches and pull requests are also a nice way to structure your commits and to make things more traceable.
                - Indeed, branches are another good option to structure the project and avoid a large number of commits in the main branch.
     - It is not a problem for the disk. Changes are saved very efficiently.


## Break until xx:05

- make sure you walk around some or relax
- you can keep asking questions

21. Sound ok! RB is not quiet.
    - thanks

22. If the repository is only local (for now), how can we use the browser github instructions?
    - for the browser github you would have to start further up when we created the repository and (also) create it there.

23. What does the HASH mean in the additional exercises?
    - it is that long 40 character identifier of each commit

## Exercise: https://coderefinery.github.io/git-intro/basics/#exercise-record-changes

Until xx:29

Goal:
- Basic-1
- But there are optional exercises on the same page (green boxes)o
- You can also try to retrace the steps on github

I am (add "o" to vote):
- done: oooooooooooooooooooooo
- need more time: o
- not trying: o
- it was easy: ooooooooooo
- it was about right: ooo
- it was hard: o
- not so hard, but nano freaked me out - changed to vs code oo
    - I feel ya. We use Nano as example because it is maybe the simplest text editor in command line. I use VSCode usually as well. -MJ
- great exercise!ooo

24. What to do when `git init -b main` does not work?
    - sorry we tested this also on older versions of Git but apparently not thoroughly enough
    - RB: I recommend to go through the exercise then without the "-b main" part and then default branch will be called "master" but the rest will still work
    - You can do `git init`, then `git checkout -b main` right after to get "main" as the name of the current branch, this works on older versions.
        - I would rather show these topic and fix when we deal with branches later on?

25. Why are some commands with two dashes, and others with just one? E.g., `git add --all` or `git add -A`
    - If you use one dash, you may combine several options, each represented by one  letter, an abbreviation to the double dash options.
    - often the double-dash are longer versions and the single dash abbreviations
      - Great thanks :-)

26. Can I edit the commit message of a past commit?
    - Technically yes.  It would make sense right after you did it (use `git commit --amend`).  Don't do this for older commits or after you push (we'll learn this term later), it'll make a big confusion.
         - we might try it tomorrow. more here: https://coderefinery.github.io/git-intro/recovering/

27. Does diff show all differences between versions, or only a part of them if the documents are very long?
    - All (unless you request something else)

28. Optional ex. 3: I get this error message when launching meld: The diff tool meld is not available as 'meld' fatal: external diff died, stopping at instructions.txt. I have activated codereifnery conda env.
    - This is an extra tool which can be added.  Don't worry about it for now - it's just an extra thing to try.
    - note that meld is for Win/Linux and opendiff is for Mac
    - GitHub has visual diffs aand also eg. JupyterLab can have (we demonstrate this next week)

29. Is there an easy way to be able to view mutiple hashes in the terminal at once?
    - do you mean `git log --oneline` ?

30. Why always "add" not just commit directly? +1
    - you can commit directly too!  "add" provides extra ways to check before going on, so we show that first.
    - Using `add` first gives you a control step on what will be commited, it is very usufull if you do not want to commit all of your changes in one commit.
    - we have an episode discussing pros and cons of both ("staging area"). but it is perfectly fine at the beginning to commit files directly.
    - if you make a commit of any little change you do, you get a huge history (the output of `git log`) with a very fragmented (granular) meaning. `git add` can also work as a sort of back-up copy you can fall back to before you make a commit (unsure whether this is covered here)

31. Optional ex. 2: I can't have a look on `git show HASH` because it gets an error: ambiguous argument 'HASH': unknown revision or path not in the working tree.
     - replace "HASH" by the actual identifier (it is different on each computer; use `git log --oneline` to see them)
       - oh thank you, I got it!
     - TOFIX: please explain what a HASH is in the exercise explanation
       - thanks! https://github.com/coderefinery/git-intro/issues/427

32. How do I create a new file, I missed that bit. I am getting this error
    ```
    $ git add ingredients.txt
    fatal: pathspec 'ingredients.txt' did not match any files
    ```
    - You can use `nano` for example for the editor to make a file in the git directory.
    - eg: `nano ingredients.txt`, Then you edit the file and `ctrl+x` and `Y` to save it.

33. Is it safe to keep a git repository in cloud storage such as Dropbox or OneDrive?
    - I would rather place them on GitHub/GitLab/Bitbucket. Otherwise the could storage with its own version tracking might start tracking the ".git" part also and the one versioning might confuse the other (that's my experience when trying this with one of them 10 years ago)
    - I'd add that it depends how "safe" the cloud is. Also, the big advantage with putting it on GitHub or GitLab is that you can use the web interface to inspect commits, files, and do some other tasks that are similar to the git commands in the terminal.

34. In MacOS opendiff is installed but not showing the diff?
    - you might need to set it as the diff tool for git (https://git-scm.com/docs/git-difftool)
    - https://coderefinery.github.io/installation/difftools/

35. Can you maybe give an example about a good comment? (informative, short, specific, how to do that?)
    - ":bugfix: Corrected the calculation in the add function - => +"
    - Good commit messages is art: https://cbea.ms/git-commit/
        - like any writing imo :D
    - some good references are listed in https://coderefinery.github.io/git-intro/basics/#writing-useful-commit-messages - it can be good to also browse few of the example projects that are very popular to see how they do it
    - A good comment provides a context and explains why something was done (this might not be needed for trivial changes)

36. In this case:
    ```
    Date:   Tue Sep 19 10:12:33 2023 +0200

        added enjoy message

    diff --git a/instructions.txt b/instructions.txt
    index 7811273..2b11074 100644
    --- a/instructions.txt
    +++ b/instructions.txt
    @@ -4,3 +4,4 @@
     * squeeze lime
     * add salt
     * and mix well
    +* enjoy!
    ```
    What is my HASH1 and HASH2 ?
    - I understand, I found it following right now, taking ids from: `git log --oneline`
        - ah good - I wanted to answer but then got distracted


## Git log history and commit messages

https://coderefinery.github.io/git-intro/basics/#git-history-and-log

37. How can I see the `git diff` output in the vs code?
    - either you do it in a terminal (just open a terminal in vscode), or you can click on the "version control" tab (left side, looks a bit like a graph), and then look at changes. But that's already an interpretation of the git diff output.
    - note also that "git diff" will give no output if you have `git add`-ed a change. it compares working directory with commit or staging area.

38. What does this error mean - warning: in the working copy of 'instructions.txt', LF will be replaced by CRLF the next time Git touches it
    - Linefeeds (newlines) are encoded differently between windows and linux, and git can be set up to use one of them (https://docs.github.com/en/get-started/getting-started-with-git/configuring-git-to-handle-line-endings), this message tells you which type it will use.
    - CRLF = carriage return, line feed. From the usage of typewriter to move on in a sheet of paper (now visible from inkjet printers)
    - https://coderefinery.github.io/installation/shell-and-git/#troubleshooting

39. git difftool does not work, I am using Mac, git difftool --tool=opendiff HASH, this does not show me any thing but no error message either
    - is that the latest commit and are there any changes since then?
        - yes, it is the latest commit, no change. Is that the problem?
            - No, not a problem but it simply cannot show anything as there are no changes :smile:
            - Ok, thanks. I used another hash, now it gave me an error message: xcode-select: error: tool 'opendiff' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance. I have XQuartz installed and opened.
                - That's a problem with the setup on your mac. I'll see if I find something, but I'm not a mac user myself, so not sure if I can help you there
                - thanks anyway, I will figure it out :-)
                - Do you have Xcode installed?

40. Any reference for installing opendiff on Linux (Ubuntu)? `apt search opendiff` gives no results.
      - You may try `meld` on linux. https://coderefinery.github.io/installation/difftools/
          - Thanks, that already tried and works perfectly.

41. Should I always remove with `git rm` instead of bash `rm`?
    - `git rm` removes file + stages removal
    - `rm` + `git add DELETED_FILE` (or `git rm DELETED_FILE`) is the same
        - As you can see here, the command `git add` is not always about adding a document to the index, but to record a change in the index/stage. Note that `git stage` is an alias of `git add`, that is, you can use both names to the same effect

42. Is there a convention for adding additional .gitignore files in subdirectories and when not to?
    - Not sure if there is one. Personally I would keep .gitignore files in the main folder. if you really need a specific -gitignore for a subfolder, maybe you actually want to have a submodule instead of a folder i.e. the folder actually represents it's own entity in some way?
    - use one if one is enough but sometimes it is useful to have several. problem with several is that sometimes your colleagues will overlook them and be surprised that there are more than one.

43. I have a problem with `difftool` in mac os. I got the following error
    ```
    xcode-select: error: tool `opendiff` requires Xcode, but active developer directory `/Library/Developer/CommandLineTools` is a command line tools instance
    ```
     - This problem usually happens when `xcode-select` developer directory is pointing to `/Library/Developer/CommandLineTools` when regular xcode is required.
     - you can try to change the active directory `sudo xcode-select -switch /Library/Developer/CommandLineTools`
     - But, I would suggest to try it after the workshop. Otherwise you may loose your focus on `git`. For the time being, you can use `git diff` on command line.

44. General question. I always have a problem to decide how to structure the
    folders which are under control of Git, especially when I work on Python
    Notebook to code in an explorative way. I start with creating a new project
    folder as a git private repo. After some coding, I realise I would like to
    divide the project into two projects, because one specific part becomes
    important, or because I only want to publish one part of the project for
    public. There is also a need to maintain two very similar code (i.e.
    seperate the private version of code from the public version). If you have
    many projects like this, GitHub structure becomes messy. Is there a good
    practice to organise GitHub repo/folder structure?
    - What you can do is create a new repo for the "important" part and include it as a submodule in your original, removing the code you exported. That way, your "private" keeps intact but you can continue developing on the exported functionality.
    - But also it is often impossible and "unreasonable" to try to get it right and perfect right from the start. It is an iterative process of projects splitting or joining. As soon as a project becomes difficult to name, it might signal that it tries to do too many things. Common code used in other project can then be split off into a separate library that can be included either by git (as submodule, answer above) or by pip as Python package.
    - What do you mean with *GitHub folders*?
        - It just means folder under control of GitHub (question text already modified)
            - Perhaps, an option is to maintain two long-living branches of the same repository and share with others only a public branch. This makes it simpler to overview the differences between what you *develop privately* and *release publicly*. Look up around for tips about "Git workflows" and stay tuned with the rest of the course!

45. When I began with git some years ago, I was in a similar course. Then I
    generated a .git folder in my personal /user directory. This led to a lot
    of mess since the underlying .git(s) made under this folder (which is
    basically everything) is then connected in ways I don't quite understand.
    Deleting the most "top" or "parent" positioned .git then helped on this
    issue and the underlying "child" git folders are fine, but it first led to
    some confusion. So, not so much a question here, but a story and a reminder
    to try and avoid making such a mistake. I would also suggest that we would
    have made a /CodeRefineryWorkshop folder first and then dived into that and
    made the /recipe folder there. At least if I had done that back then, I
    would have not mistakenly made a .git before I knew what I was doing
    (although I should have done that in what today is this /recipe folder, but
    mistakes were made and we learn hehe). Today, the story ends happily with a
    much cleaner directory and I am a very happy user of git `<3`
     - thanks for the suggestion. we will adjust our material to first create a workshop directory and then everything underneath: https://github.com/coderefinery/git-intro/issues/424
     - adding here as explanation for others: git repositories can be nested with git submodules or git subtrees, but nesting them by placing one under the other on the hard drive can lead to confusion since when you type commands like "git status", Git only sees the closest git repository, but nothing "above".


## Branching and merging

https://coderefinery.github.io/git-intro/branches/

46. Is there a way to list down my alias for my git commands ? Asking this because I will forget what graph does later...
    - `git config --list` will not only list the configuration, but also all the configured aliases. You can also ask for `git config alias.graph` specifically

47. Warning. Some people still have `master` instead of `main`
    - yes. in this case replace all command to use "master" instead of "main"

48. Is `switch` exactly the same as `checkout`?
    - No. `switch` is more specific and does only one thing of many that `checkout` does. So it is a safer option because with a single outcome there is no way things can go wrong. In other words, you can get checkout to make a switch, but it is a more error-prone avenue
    - for the purpose of branching it does the same
    - see question 61 too

49. How do I remove an git alias?
    - easy: `git config --global --edit` to open in editor.
    - There is also `git config --global --unset alias.graph` if you prefer the command line
    - alternatively you can edit the file `~/.gitconfig` where all the `git config` settings get saved
        - more fragile option: if you break things there, repairing will be more troublesome. Better to have a focused git command to make a specific intervention
          - good point

### Exercises Branch-1 and Branch-2

https://coderefinery.github.io/git-intro/branches/#exercise-create-and-commit-to-branches

Until xx:43

- The exercise does what we just did together, but again
- Go on and do the merge during the exercise session.
- At the end, yous should have an "experiment" branch and a "less-salt" branch and merged them back
- Branch-1 and Branch-2


50. I seemed to have closed the window and cannot open the repository back again. How does one open a repository? ...
    - You need to change directory (`cd`) to the right place.  `ls` should tell you what's there.  e.g. `cd recipe`
    - worked thanks !

51. General question. Using zsh terminal on a mac, the tab autocomplete doesn't fill in in a git command. e.g. you can't tab to autocomplete less-salt.
    - here are some hints on how to customize this: https://coderefinery.github.io/git-intro/customizing/
        - will read through it thank you!
    - Yup the autocompletion of git commands is not by default in any shell/terminal

52. I accidentally started adding cilantro in main and because of that made some other changes in experiment. Now experiment is "behind" main and I got a merge conflict. How can I fix this?

    - recommended recovery:
      - create a new directory
      - cd into the new directory
      - follow "if you got stuck ..." blue box in https://coderefinery.github.io/git-intro/branches/#exercise-merging-branches
    - tomorrow we will learn to recover from such sitiations: https://coderefinery.github.io/git-intro/recovering/
    - but also no problem if it is "messed up", for the rest of today you will not need it and rest can be demonstration from us and then later you can try to retrace the steps. also tomorrow we can start from the "if you got stuck"

53. In the solutions, it is said: "This was possible since one branch is the ancestor of the other and their developments did not diverge." I don't understand, how this was different?
    - Quick answer: There are not changes in branch "main" that don't exist in branch "experiment". So git can just take the new changes and apply them to branch "main".
        - Oh I see. So if, lets say, another person had modified the main while I was working on the branch, this would not have worked?
    - We'll get back to this in the stream

Question to audience: How is the speed so far (add an "o")?
- too fast: o
- too slow: o
- just right: oooooooooo
- confused where we are:

54. I made my own bean 🫘 recipe and created two branches from main. In one branch I added one new ingredient and in the other branch another ingredient. I successfully merged one branch into main, but when trying to merge the other it said I had a conflict: differing bottom lines in the ingredients file. However, it did not allow me to choose which version to keep or to keep both lines.
    - Also, we will cover conflicts later. To get back to where everyone else is, you can follow
    - https://coderefinery.github.io/git-intro/conflicts/

55. I am a bit confused about the fast-forward. I create 2 branches (test1 and
    2). Swith to test1. Change README. Swith to main. Merge, I was expecting
    usual merging but is fast forwaded. Not sure I get this, as the changes are
    in the branch test1 not main.
    - Merging can be automatic or manual.
      In case of automatic merge, Git decides which merging strategy is the
      most suitable to the case, based on prior expertise of the Git
      developers.  In the case of manual merge, you decide with appropriate
      option to the `git merge` command.  You have ultimately control on
      which merging strategy will be used. However, as a matter of default,
      Git will ask you to resolve a conflict when none of its automatic
      strategies appear suited to tackle the file differences at hand.  In
      your case, Git has used a so-called fast forward strategy because the
      changes you made in the source branch are simple enough that they can
      be seen as if you had changed the document in the target branch. (Of
      course when you make a branch, you cannot take it for granted that your
      changes will be simple all the way, barring exceptions.) A bit of a
      mouthful, I know.
    - Fast-forward means: if Git can merge without creating a merge commit, by only moving one branch label "forward",
      then it will try to do that. In your case `test1` was one commit ahead of `main`. Merging `test1` into `main` could
      be done by moving `main` one commit forward, without creating a merge commit.

56. what if you didn't get this comment after merging to main?
     - It's possible there were no changes in the main branch, so that the merge was done using "fast forward".
     - some editors or older git versions create the merge commit automatically without giving you the chance to edit them

57. What does it mean that the merge was made using the "'ort' strategy"?
    - This is the default merge strategy. More info [here](https://git-scm.com/docs/merge-strategies#Documentation/merge-strategies.txt-ort)

58.  Is `git switch` and `git branch` encouraged over the more general (but maybe ambigious) `git checkout`
     - Yes, because it is more clear what the command does from its name

59. Can you delete the current branch with `git branch -d main`   when in branch `main`?
    - No, you cannot remove the branch you're currently on. You need to switch to a different one first.

60. Is it possible to merge any branch without a message/update? Because when I was doing the fast-forward exercise I followed the exact workflow but it did not ask for any message while previously in 'less-salt' and others it did.
     - A fast forward merge does not necessarily have a message.
     - Otherwise, the merge will create a new commit, and require a commit message
     - you can also configure git to not ask you and just put a default commit message for merge commit (since personally I never modify that message)

61. Does it make sense have multiple branches for different type of pipelines? Or is the ultimate goal always to merge?
    - can you please define what "pipeline" is?
        - I often have cases where I need to handle different files and these different files need some changes in the code. My approach is to have pipeline_1.py and pipeline_2.py. But if I could branch the pipeline_1.py and make modifications to that, then I don't need to create a new file and I see, where the pipelines "diverge". Now as I am thinking about this, maybe it is not a good idea, because this is about version controlling, not for these type of tricks.
        - Looks like pipeline is a file for you. Pipeline can have several meanings in software development. Mind that a branch keeps track of changes in multiple files. The branches may have different versions of a file with the same name, if this helps. When you switch branches, the content of that file will change. So you cannot have two versions of the same file at the same time in your working directory (aka working tree).
    - Sometimes I do have long-running branches which never converge.  It's possible and if you don't edit the same stuff, it's not too bad.  But you might want to see if you can define the differences as configurations rather than different code.
    - Some open source programs have branches meant for different use cases, and these branches will never be merged to main. For example, there are versions of the Linux kernel for different architectures. (I did not check if they are actually git branches, but they could be)
        - Oh okay! Good to know. Would love to have some examples.
            - Typical is to have a public branch for releases and a private branch for development. A celebrated model is https://nvie.com/posts/a-successful-git-branching-model/ by Vincent Driessen
    - Most projects only have one or two long-lived branches and most other branches are meant to be merged back at some point.

62. Is it possible to change the commit message afterwards (e.g. if there is a typo or another mistake)?
    - Yes it is possible: `git commit --amend`.  Only do this if you just made the commit (you can in fact do more, but it can get confusing very quickly)
    - https://coderefinery.github.io/git-intro/recovering/#adding-to-the-previous-commit-modifies-history (tomorrow more)

63. Is `git switch` recommended over `git checkout` to switch branches?
    - we demonstrate here `git switch` because it better communicates the intent. `git checkout` can switch branches, undo unstaged modifications, and also navigate to a past commit and we found it confusing in past workshops to explain that the same cousmmand can do so different thing
    - see question 46 too
    - `git switch` is a newer command compared to `git checkout` and it may not work if you have an old `git` installation. `git switch` only works with branches as arguments, while `git checkout` can do different things depending on the arguments and options, which can make it more confusing as well. That is why, for clarity of the command, we recommend `git switch`. But you may use any command that you are comfortable with.
        - https://www.git-scm.com/docs/git-switch shows that git switch has been introduced with git version 2.27 (click on the version list just above in the page to find that out)


## Conflicts and confict resolution

https://coderefinery.github.io/git-intro/conflicts/

64. I am getting the error message `fatal: cannot do a partial commit during a merge.` +1
     - I found the problem. I for got the -m in `git commit -m "Let people decide themselves how much cilantro they want"`

65. What if I start a merge, see a conflict, and decide I don't want to merge yet? Is there a way to "stop" the current merge?
    - git merge --abort

66. I was following you guys, but then I merged I got `Already up-to-date.`Is this because I was on the main branch. Not sure I follow what happened.
    - This is probably because you did not change anything at all the branch you are trying to merge now. Did you edit and commit files on another branch rather? Please double check.
        - I got a conflict and then I fixed following the tutorial. Then I moved into main and corrected the conflict. Then wehn I merged, basically did not merge, as there was nothing to do.
            - If you are using the terminal, the shell command `history` will list you the commands you have typed. Then you can try to revisit what you did and make sense of it. I cannot give you a precise answer based on your description. (Others may well do.)
            - Sure, thank you

67. I used mergetool and integrated it with vscode (similar to (optional) Basic-3: Visual diff tools assignment). Afterwards you can just commit again and solving the conflict. (it works nicely visually, however is probably limited to easy conflicts)

68. A changed 1 lime to 2 limes, at the same time, B changed from 1/2 onion to 1 onion. This can work for each branch, but it may not work together. How about that? Is there any warning about that?
    - do mean the recipe doesn't work together, or about getting a conflict when there shouldn't be one?

59. Another thing to note (correct me if I'm wrong). There are only merge conflicts, no commit conflicts. This means that if several people work on the main branch, everyone will always overwrite any changes made (with no warnings etc.). So you need branches when working together in the majority of cases.
    - In this case, there actually are different branches on different comp
    - We will clarify this on day 3 but when working together on one branch, that one branch is typically on a central repository on GitHub. And locally we have our own local versions (clones). Even though the local branch might have the same name, Git will not let us accidentally overwrite work of others. If you try to push changes from your local "main" branch and Git detects that the remote "main" branch has commits that you don't have locally, it will stop with an error.


## Feedback of day 1

:::info
Notes: Twitch will have videos immediately, I'll try to get them YouTube:ed by tonight, check installation/configuration for tomorrow, check course webpage for any other news we can think of.

Tomorrow is more git basics, trying to see more of the full power. see you then!
:::

Overall, today was (choose all that apply):

too fast:ooooo
just right: ooooooooooooooooοoooooooooo
too basic: o
too advanced:
recommendable to others: ooocoooooooooooooοooooooooo
I am coming back tomorrow: oocooooooooooooooooooooooooooοoooo
I'm not coming back tomorrow:

How was the collaborative document (this document):

felt responsive: oooooooooooooo
slow/sluggish at times:oo

One good thing about today:
- good amount of work/breaks +6
- enough time for local teams to work on exercises and have additional discussions +3
- I worked in git in the past already, however this course gives a nice connected guide in the basic commands.+2

One thing to be improved for next time:

- slow down a bit. it is not possible to follow unless you already know how to do it.
- it takes w
- it was a bit fast towards the end, when steps were getting more complicated
- could be nice to see more code history from the terminal in the share screen, in case we miss a command +2
- No complaints, everything was super smooth. +1
- I worked well for us, we're just three and already know a bit about how to use git. We've learned good practices, excited for the next days.
- Show the files that are created in the file explorer (at least once in the beginning). And it would be helpful to add a visualization on where all the files are (saved on hard disk, staged, commited etc.)
    - Thank you for the suggestion, created an [issue in the course repo](https://github.com/coderefinery/git-intro/issues/426).
- A bit fast at the start, but smoothed out middle and end
- Interesting to follow the basic steps. Got me to understand a lot. But I think I will go on using GitHub for Windows, and not all the commands.

Any other comments:
- Super interesting!! Feeling motivated to learn more
- Finger's crossed for a visit from the cat! +1
- For the remote SSH connection on github ->  to use a *deploy key* it HAS to be called `id_rsa.pub` or `id_ed25519.pub` (and be located in `~/.ssh`) it will otherwise ignore your keys even if added explicetely. You can make a symlink if you have many keys. This is not needed in gitlab.
