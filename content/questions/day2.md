+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 2"
+++

## Please continue asking questions about content from day 1?

To find questions and answers from yesterday, please follow link above

1. RB: Oh no, did we forget to mention tags?
    - Answering my own question: yes! But they are important: https://coderefinery.github.io/git-intro/branches/#tags
    - They are like branches but don't move and can be used as milestone markers along the Git history
        - this sounds intenresting, do we do exercise on this today?
            - No, but please refer to the link above for more info.

2. Sorry for this question but I guess I missed sth. So these changes/merges/branches are local. How to sync with local and web? Is it possible? I mean when I create a project from terminal, may I have an ability to modify from web interface or vice versa? 
    - great question. everything so far was local. today we will give a preview on how to share with web and tomorrow we will do that in depth.
    - thanks for the clear answer :)


## Icebreaker questions, day 2

### I am watching:

- by myself: oooooooooo
- in an organized group: ooooooooo
- group is online: ooooo
- group is in-person: oooooooooo
- by myself


### What should the mascot of this month's workshop be? (vote for ideas by adding "o", multiple votes OK):
- cat: oooooooo
- gopher: oooo
- tree of souls from Avatar (symbolising git): o
- git goat: oo
- ...: 
- A hedgehog (HedgeDoc) oooo
- Shiba inu: o
- not sure if one is necessary o


### What has been your most collaborative project so far (tech or not)? How many people and how did you work? Do not put names or identifying information on this page.

- a project for my PhD thesis but we were only two persons
- have to say CodeRefinery lessons and web page :D
- A lab project as a pair
- A paper with several labs collaborating 
- A course on R programming where we had two shared notebook for the code alongs and the exercises. It was super nice to have that all in a shared repository.
- raising children ;-) it takes a village <3 well said:))
-
- I am working on a git project with the HCP centre at my university. My research group has a tool which works fine for our goals, but can be improved for other research projects. Our HPC centre is supporting us in this improvement.
- Continuous work on an online tool called the "MarINvaders" that connects and harmonizes data from different databases. This has been going on for a while on Gitlab and is currently being simply maintained although some projects will build on top of this repository.

## Introduction to version control (continued)
https://coderefinery.github.io/git-intro/remotes/

3. From twitch: for this random question, but I tried to learn git from different ressouces, but I think the best way is to learn while working on big projects, but unfortunately its not a given to be a part of big projects for beginners, what do you think?
    - Open source projects are often happy to receive contributions no?
        - At least they often have contribution guidelines to make contributions easier and to keep them in the project's style

4. Is using GitHub for sharing and synchronizing the codes across the machines good practice? Not for version controling?
   - You mean you wouldn't try to version control using it or ... ?
   - It is a viable way to sync your code eg. between a local computer and a remote computer. The version control kind'a just happens there also

5. Is creating a private git repository on the web safe? 
    - I'd say it's not "API-key safe" ie. don't put personal/sensitive information there

6. Are GitHub and GitLab similar and how to choose where to store your projects?
    - Pretty similar in general spirit.  GitLab can be self-hosted so for example you can use one run by your own organization.
    - Some differences in terminology but general functionality is about the same

7. Can one use GitHub not only for code but also to collaboratively work on datasets? To share with colleagues and multiple people modifying it.
    - Not for big datasets or images or videos. Such media should be stored in other places such as cloud storage and the code or collaborative documents can be stored on GitHub. 
    - I've sometimes done that for small things.  It's not really designed for large data.

8. A third authotication method would be using Personal access tokens right? Is there like a tier list for access methods?
   - Yeah, you could.  If you're askng that question, you probably know how to do it :)
   - Though it's a bit less secure since it's basically a reusable password so we don't give it as an examlpe.

9. Can I use my own recipe repository even though I didn't quite finish yesterday?
    - Yes.
    - the main point here is that we are able to push a repository. in this case does not matter so much what is in the repository. but please still compare histories locally and on the web.

10. I am bit confused, weren't we creating online github repository (recipe) yesterday ?
    - We only worked on our local computers, at least if you follow the lesson. Maybe you were part of a group that create a remote repository as an extra exercise?
        - But wasn't it one of extra excercises?
            - Do you have a link to the exercise you have in mind?
            - https://coderefinery.github.io/git-intro/basics/
            - Part Creating a repository Browser (github)
                - I stand corrected. Indeed you could do the same steps in the exercise on GitHub instead of your local computer. That is useful especially if you do some minor changes to your repo.
                - Ok, understood, I was thinking I confused sthg
    - RB: sorry for confusion here. Indeed we offered parts of yesterday to do on the web as alternative. in this case you have a repo on GitHub already. What I would try now is:
       - clone it and push it to a new repo that you create on github
       - create a mini repo locally from the command line and try to push that one
       - My problem is that I am new to github and I cannot find option to add ssh authenthication now as it was not the part of yesterday exercise


:::info
## Exercise: until xx:45
https://coderefinery.github.io/git-intro/remotes/#authenticating-to-github-ssh-or-https
- Check the sections there
- Goals (pushing from your computer to Github, if you did on your computer yesterday):
  - create empty repository on Github
  - push your Git repository from your computer to the GitHub repository
  - also experiment with cloning a repository (you might then need to clone it to a different directory)
  - compare histories locally and on the web
  - inspect "git log" after the clone

Exercise feedback:
- I am done: ooooooo
- I need more time: 
- I not trying: 
- it was easy: 
- it was just right: o
- it was hard: 
- I am confused :) o
    - There will be a demo before we resume with the lesson, so hopefully there will be no more confusion.
:::


:::info
## Exercise: until xx:45
https://coderefinery.github.io/git-intro/remotes/#authenticating-to-github-ssh-or-https
- Check the sections there
- Goals (pushing from your computer to Github, if you did on your computer yesterday):
  - create empty repository on Github
  - push your Git repository from your computer to the GitHub repository
  - also experiment with cloning a repository (you might then need to clone it to a different directory)
  - compare histories locally and on the web
  - inspect "git log" after the clone

Exercise feedback:
- I am done: ooooooo
- I need more time: 
- I not trying: 
- it was easy: 
- it was just right: o
- it was hard: 
- I am confused :) o
    - There will be a demo before we resume with the lesson, so hopefully there will be no more confusion.
:::


11. After setting up an ssh token for gitlab, the command ssh -T git@gitlab.com works in command prompt, but it does not work in git bash.
EDIT: turns out bash home is set to a university remote drive, so its looking for the key in the wrong place I think. changing the home variable to the proper drive doesn't seem to work though and it resets after rebooting. So anyway to change the bash home variable permanently? (I tried export HOME=/c/users/me, but this doesn't help at first and it switches back to a different drive on reboot)
    - hmm .... (thinking)
This is my problem (using VDI, Helsinki University): 'Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
git@github.com: Permission denied (publickey).'
    - This is something we recommend to check with your local organisation's IT-support



12. When we create the remote on command line, does it become public or private on github?
    - on the command line a remote is a placeholder for a web address. but it does not know whether the web address is private or public. only thing the local git cares about is whether it has write permissions to it so that's why we need to authenticate.
    - When made on command line, it's not online at all.  Decision is made when you "make new repository" on github/gitlab.
       - correct, the remote is actually only a file that exists locally and it has a name, typically "origin" and contains a web address. that's it.
       - okay, thanks! I just wanted to avoid publishing something by accident :D

13. Could you explain these lines a bit more: Add a remote reference with the name “origin”, Rename current branch to “main”, Push branch “main” to “origin”? Specifically, what is meant by "remote reference" and why did we have to rename the branch if it was already called main (from yesterday)?
    - OK, the "Add a remote reference with the name origin" is the explanation for the command `git remote add origin git@github.com:USER/recipe.git`. Explanation: remote is a git repository somewhere else, behind some web address. in this case the web address is the github address. "origin" is a name to that address. then from here on we can refer to "origin" and git will know we mean github.
    - the renaming part has no effect here. we added it here because:
      - github shows it anyway so we wanted to explain what it would do
      - it is a safety net for those who created "master" yesterday (github has by default "main" as default branch)
      - no effect and no harm for those who have "main" already 

14. All went well, but now I ask myself whether by cloning the recipe folder locally I will be able to see my change history from yesterday. In other words is the info in `.git` also pushed on GitHUb and can been seen/cloned?
    - In git, every copy has all history.  If you pushed to Github, and made a new clone, you'd have all the same history.
        - ok, thank you. However, if I compare the two folders (old vs newly cloned) I can see that the history is very similar but some branches are not there in the newly cloned. Is there a reason for that? ah ok this is maybe becuase I only pushed Main? Now I pushed the branch `like-cilantro` and there is a new branch in my online version. Ok, so I guess this is the reason. Can one push all branches at once? Like the whole project on the local machine?
           - we pushed only the main branch. try also pushing the other branches. you can also `push --all` (all branches). after that you should see identical histories.

15. After pushing the repository to github all branches are gone in the online version. I am only left with the main branch.
    - You mean locally, or on Github?  `push` by default only pushes the branch you say - the remote wont' have the others.  Unless you push them, which is also normal to do if you want.
        - Locally it is still in the state from before. The version on GitHub only has the main branch. In that case I see why thanks!
          As a follow up is there a possibilty to push all branches at once?

16. I cloned your repository despite having a local one. Now I am getting an error message when I try to push. How can I resolve this? 
    - Hm.  It depends on where you cloned and where you are now.  Are you in the original or second one?
    - ~/recipe/recipe (main)
    - I deleted the cloned recipe and it worked thanks! 

17. What is the difference between SSH and HTTPS? I there a preferable one to use?
    - shh known as Secure shell protocol, used to secure services over the network. It uses the key pair (public and private). Using the shh protocol, you can connect and authenticate to remote servers. You can connect to Github/Gitlab without your username and personal token each time 
    - ssh is more secure than https option. 

18. Can I think of origin as the remotes HEAD, or what is origin?
    - You should think of origin as a reference for the remote repository.
    - remote is a reference to a web address
    - HEAD is reference to a branch or a commit
    - there is a HEAD in your local repo and also a HEAD in the remote repo

19. Where can I see the history on Github, similar to if I type "git graph"? It seems like now all of the history is gone.
    - It should be basically the same.  The git basic history view doesn't show the graph connections, but Insights > Network shows a similar network view.

20. I find some parts confusing when setting a remote repo. 
    1. git remote add origin git@github.com:USER/recipe.git 
    So "git remote add" is the command, and is "origin" just a name we are giving to the remote repo? 
    - Yes, "origin" is just a name.
    2. `git branch -M main` why do I need o create a new branch called main? I already have the main branch locally. 
    - The command rename the branch you're on to main. It's an extra step we added to make sure everyone has the same name for the branch.
    3. `git push -u origin main` "u" indicates upstream according to the documentation, what does that mean? And why am I pushing from origin to main, shouldn't it be the other way around?
    - This command means: push the commit changes in my local branch called main to a remote branch with the same name. `-u` means: create a correspondence between the two branches so that next time you push this branch, it's enough you type `git push` instead of `git push -u origin main`. 
        - Perfect, thanks!

21. Do you always call it "origin"? in this part: Add a remote reference with the name “origin”
    - The default name is origin, but you can give it [almost] any name.


22. I accidentally cloned my repository to the wrong folder. Can I move it somehow?
    - You can move the whole repository somewhere else, no problem. Just make sure you do not move it inside another existing Git repository.
    - How would I do that? 
    - in the Bash shell, `mv` moves it.  If you can find it by the file browser on your computer, that works too (and is probably simpler)
    - Thanks! :)

23. SSH keys. I had to remove the deploy keys from yesterday's and add to the new. Any way to do it more elegantly? 
    - Ah.  You set your SSH key as a deploy key to a single repository?
    - Try going to "Your settings" and then "SSH and GPG keys", and you can set keys for your whole user - it works for all of your repositories then.

24. As I was pushing from github online to my local version I received following error:  
	```
	! [rejected]        main -> main (fetch first)
	error: failed to push some refs to 'github.com:USER/recipe.git'
	hint: Updates were rejected because the remote contains work that you do not
	hint: have locally. This is usually caused by another repository pushing to
	hint: the same ref. If you want to integrate the remote changes, use
	hint: 'git pull' before pushing again.
	hint: See the 'Note about fast-forwards' in 'git push --help' for details.
	```
    - see troubleshooting box, it explains and shows how to recover, it's the error with "contains work that you do not have"
       Or the problem is that I have README as I prepared online github following yesterdays excersise
    - Search for "trobleshooting" on this page: https://coderefinery.github.io/git-intro/remotes/. The solution you need is under "remote contains work that you do not have".


25. If I want to clone the repository with this command: `$ git clone git@github.com:USER/recipe.git`, should I be at the main directory or in the recipe directory? 
    - Main directory.  It gets put as a new directory where you are - and you probably don't want sub-repositories.

26. Can you explain the aim of setting an SSH key? (Sorry for this silly question). Months ago I set it for my UiO Git account. When I tried to run the command `ssh -T for my personal Git account` (because I do the exercises on my personal account), it asks me to write:
    ```
    Enter passphrase for key '/Users/myusername/.ssh/id_rsa':
    ```
    I wrote and 
    ```
    Hi USERNAME! You've successfully authenticated, …
    ```
    What did I do during this process :))

    - The command `ssh -T` is used for testing in this case. So you just tested that you can log in.
    - Since the test was succesful, it means you should be able to clone from and push to the UiO Git system.

27. Why do we run `git branch -M main`?
    - This names the first branch you create "main".
      - The default name for your first brach used to be "master", but many systems are moving to the name "main" and expect that to be the first branch

28. Why are we calling 'repository'? and not just 'local' or 'remote' folders or projects? Do we mean some specific meaning to emphasize?
    - A project can have multiple repositories. A repository can have multiple folders.
        - Here, 'recipe' is a repository or project?
            - I would say it is both in this case, a project with a single repository. I don't think we need to be too strict with the semantics in the end, depending on the case one can guess if a project is a collection of repositories or if a project equals a repository. Github offers "GitHub projects" which is a tool to manage various repositories part of the same project (out of the scope of this course).

29. So "push" and "pull" basically just means uploading and downloading to/from GitHub?
      - Yes
      - to/from a (web) address of our choice. one can even clone and pull/push on the same computer between two repositories.

30. On GitLab I can use `git push --set-upstream git@gitlab.com:username/repo_name.git main` to create a repository named repo_name without needing to create it manually like we do in the exercise. Is this a gitlab specific thing? 
    - The remote repository needs to exist only on GitHub or GitLab before you push, but it can be empty before you `push`.
    - 100% something I have done on GitLab, so the answer: you can't is not very satisfactory


31. I get the following error, after the push command (`git push -u origin main`)
    ```
    ERROR: Repository not found. fatal: Could not read from remote   repository. Please make sure you have the correct access rights and the repository exists.
    ```
    - Is the `git remote add` command correct?
    - I used: `git remote add origin git@github.com:USER/recipe.git` (with the correct USER), which gives back: `error: remote origin already exists.`
    - ?

32. Is 'origin' an arbitrary name that we can change or is it Github-specific?
    - "Origin" is the default name for the remote, but it can be changed as you wish.
    - if you clone a repo, it will set origin as the place where you cloned from. you can rename to a different name and also define additional remotes (more tomorrow)

33. It would make more sense to have git push [source]  [target]..., right?
    - Yeah, but not everyone thinks the same way. :)
    - I think it is better, so that we don't need to type the entire URL all the time :)

34. I get this error git: 'graph' is not a git command. See 'git --help'.
     - This is an alias we defined yesterday, see below
     - you can type this `git config --global alias.graph "log --all --graph --decorate --oneline"` +1

35. Where was the insights part in Github where you saw a graphical display of the branches?
      - Insights -> Network
      - Top bar where "Code, Issues, Pull requests..." (it may be hidden) > Insights

36. When I pull from remote repository to update my local repository, if my local file A is different from the remote file A, will it be merged or overwrite, or will it give me a conflict message?
    - It goes to the conflict resolution process we practiced yesterday.
    - great question. when we `git pull`, we always also implicitly merge. Most of the time there won't be a conflict. if the same portion was modified differently locally and on remote, there will be a conflict during the `git pull` step (`git pull` is `git fetch` followed by `git merge`; we did not explain that yet -> tomorrow)

37. what if I merge a branch into the main branch and then I realize I shouldnt have done that. Can I still go back to the version that they were not merged? In that case what will happen to the other mergings and progressions that I made later on (after the wrong merging)?
    - This is a bit more complicated, but you can. 
    - You need the HASH of the commit before the merge. You can find it using `git log`.
    - Then to move the main brach to that commit, use `git reset --hard HASH`. 
    - If you have already pushed the changes to another repository, this will not undo the changes there.
    - we will discuss recovering from mistakes later today. one command we will show is `git revert` and one can revert also merge commits. the difference between `revert` and `reset` is that the first adds a new commit that undoes something that happened previously, the latter modifies history. morale of the story: use `git revert` if you need to undo something that other people already depend on since `git revert` will not change the history in the past for other people.

38. I deleted a branch yesterday. It is not on the github web now, clearly. Is it still possible to restore it?
     - yes one can create a branch and let it point again to a past commit. in the next episode we will learn how. but if you want to try: `git branch BRANCHNAME HASH` (where HASH is the identifier of the commit where you want your branch to point to)
     - if you want to find out "where did the branch that I deleted point to?", use `git reflog` (we did not explain or show reflog at all)

39. Why do we only see the main branch in the remote? Where are the other branches we created yesterday?
     - we pushed only "main", try pushing also the others or try `git push --all origin`

40. Instead of doing `git remote add origin git@github.com:USER/recipe.git` and ‘git push -u origin main’ could you also do `git push -u git@github.com:USER/recipe.git main`? Or do you need to define the address as something remote?
    - I think that yes, you can!  I rarely do it.
    - yes! I use this sometimes. "origin" is only a placeholder and instead you can always use the full web address.

41. Is there a way of enabling `ctrl+v` in your terminal?
    - Which operating system? In Ubuntu (and many other Linuxes), `ctrl+shift+v` works.
    - Awesome, works in Fedora as well, thanks!

42. Wow, good idea, is there a hotkey for Windows as well ? (copy paste hotkey)

    - `Ctrl+C` for copy and `Ctrl+V` for paste
43. Sorry, I wasn't clear. I meant a way to use copy paste inside the git bash terminal
    - In windows maybe try painting text (left click drag) and then right click
    - In Windows, there is a setting you need to enable in the terminal settings. After that `ctrl+shift+c` and `ctrl+shift+v`
        - right-click on the title bar of the terminal window, and select Properties.
        - select "Enable ctrl shortcuts" and "Use ctrl+shift+C/V for copy/paste"

44. Nice trick! +1 (My only challenge is that I cannot use shift + arrows to highlight. But it is indeed neat to be able to copy and paste!)



:::info
### Break until xx:05
:::

## Inspecting history

https://coderefinery.github.io/git-intro/archaeology/


45. the `grep -i fixme` command is taking forever for me, can I exit from it?
    - ctrl+c might help, "grep -i fixme" got me stuck as well but "git grep -i fixme" works
    - Thanks that helped, I made the same mistake
    - I think that if you would write `grep -r -i 'fixme'`, things will work out using default grep (non-git) as well. But I assume it depends as you might have no grep availlable in your terminal.

46. Can we create a branch from a tagged version instead of a committed version?
    - yep! that `HASH` can actually be anything that identifies a version.


:::info
## Exercise until xx:55
https://coderefinery.github.io/git-intro/archaeology/#exercise-basic-archaeology-commands
- Try to do those five parts in History-1
- There is an optional "git bisect" exercise below (History-2)
- If you want, try some on your own projects

Status:
- I'm done: ooooooooo
- I'm not trying: 
- I want more time: 
- Was easy:
- Was just right: oooooooooo
- Was hard: ooo
:::


47. How can we find the HASH for older brances?
    - (you can use the branch name directly also)
    - `git log branch_name` should show the commits in that branch

48. I accidently cloned the new repository to the recipe folder, can I just remove it and then clone it again to the upper folder?
    - You can
    - You can also move the newly cloned folder to a different place


49. I have an unrelated question: I have a meeting tomorrow from 10-11. Would you still recommend that I join the workshop tomorrow? I am a "individual learner"
    - Do join for the afternoon
    - You can do parts of the morning exercises on your own (watching the video later or just reading the material). There is an interactive part that you might miss.

50. I wonder whether the command "git annotate ...py" would also work for Jupyter notebooks?
    - Jupyter notebooks are text files, but the content is not what you see in Jupyter. `git annote` would show you the actual text file. So it works, but it's not the same.

51. If I want to make all my directories in a folder called git, how should I make this folder and make sure the new directory is within this folder?
    - If you are using a terminal with bash:
        - `mkdir git`
        - `cd git`
        - `git clone ...` (which will create a new subfolder under your "git" folder)

52. If my git bash does not use ```less``` for scrolling long outputs, how can I activate it?
    - you can try `git config --global core.pager less` but I haven't tested this
    - thanks, it worked!
    - (this was because at some times, using the pager broke it and made no output.  Maybe that  happens next week?)
        - but then we have a recovery: https://coderefinery.github.io/installation/shell-and-git/#troubleshooting
    - If next week, the pager doesn't work from the anaconda prompt, go back to here: https://coderefinery.github.io/installation/shell-and-git/#on-windows-git-log-git-diff-git-branch-or-other-git-commands-show-no-output-at-all

53. Any idea how to do a search using Git Bash in Windows on its own command output. I tried to print the log using the git annotate function on threshold.py and it gives a lot of things ?  
    - See answer in qustion above
    - (this is a bit more advanced) you can try to also "pipe" the output from annotate into grep: `git annotate SOMEFILE | grep SOMETEXT` (this will run "git annotate" on a file and then in that output, in one step, you can search for SOMETEXT)

54. I created the branch `past-code` (90544b4fa)and then the one `just-before` (90544b4fa~1). Then I switched to the `just-before`. Now here I was not expecting to see commit 90544b4fa as in the timeline I have in mind it did not happen yet. What I am thinking wrong?
    - good point I would also not expect to see it. let me try/look.
        - I tried that and this did not happen to me. Can you please post here the series of commands you typed? indeed that commit should then not be part of "git log" since git can only see "into the past" but never "into the future" (git commits reference parents but not their children). so your thinking is correct but I suspect something else happened on the way
    - `90544b4fa~1` means "commit right *before* 90544" - so 90544 isn't in it's (past) timeline anymore.  There's no easy shortcut to do "commit right after this one".
    - These is my history:
      ```
      1318  git branch past-code 90544b4fa
      1319  git status
      1320  git switch past-code
      1321  git show 90544b4fa5
      1322  git switch --create just-before 90544b4fa~1
      1323  git status
      1324  git show 90544b4fa5
      1325  git status
      ```
    - OK you should not see `90544` on top of `git log --oneline` but `git show 90544` will still work. `git show` can point to any commit in the repository. it does not have to be older than the current branch. Did this explain the question?
        - please try then also the `git log --oneline` - it was a very good question
        - Yes it does, and `git log --oneline | grep "90544b4fa5"` is empty.

55. In the bisect exercise, I got the following error: 
    ```
    Some good revs are not ancestors of the bad rev. git bisect cannot work properly in this case. Maybe you mistook good and bad revs? My good was the first commit and bad the latest.
    ```
    - can you please post the series of your commands?

56. In "Exercise: Basic archaeology commands" I do the following:
    1. git grep "Logic error in degree_correlation"
        - finding the part of the code that has this.
    2. Then I use annotate:  git annotate networkx/algorithms/threshold.py
        - This should give me some insight to the file that I from grep found out has the line I was looking for. I think?
    3. Then I write in "/Logic error in degree_correlation" specifically with the "/" in there as this should search through the file. I think?
    4. I drank some coffee and felt confused, but also comfortable knowing that I have adept people to help me let me know what I did wrong, because it was missing? What do I do? <3
    - Solution: I redid my git config `git config --global core.pager less"` (from question 52, 58). After this the search worked.

57. After I inspected the code as it was before the mistake was done by using 4dff462e52~1, is it possible to continue working with this version? Should I merge the just-before branch to the main branch? Or is it just for the sake of inspecting and then correcting manually?
    - Doing a normal merge won't work, since it's already "in main".
    - You could make a new branch from that old point (but then you lose everything else done since then)
    - you could `restore` that file to its old version (`git switch main, git restore old-version filename`).
    - You could open new version and copy just what you need (maybe this is simplest if it's been a long time ago and there are other changes?)
    - here it was for the sake of inspecting the past so it should be safe to delete the branch and try again with a different branch

58. I tried `git config --global core.pager less` and now I'm stuck in that view (running annotate). How do I get out? Enter produces more lines and esc and ctrl+x don't work. I'm using Git Bash on Windows.
    - type "q" to get out of that - did it work?
    - Yes! Thanks a lot!

59. If I do `git restore old-version filename` will I lose all the versions after this old version? Or what does `git restore` do exactly? 
    - it will overwrite your FILENAME with a version as it was in OLD-VERSION but it will not create a new commit yet. but you can lose changes of FILENAME if they were never committed since it will overwrite your file

60. Would `git log -S "TEXT HERE"` also work to find the commit where a specific line was deleted?
    - yes indeed, it will go through all commit deltas

61. Could you show how ```bisect``` works in practice?
    - +1 to this question, `git bisect good f0ea950` (the one in the example) doesn't work
    - we will post a video recording where we go through this exercise (we need to find it)
    - +1, could you at least explain how we finish the process since https://coderefinery.github.io/git-intro/archaeology/#optional-exercise-git-bisect and the solution do not explain what to do once the last good commit is found. Diff with last commit of main? When and how do we finish (with `git bisect reset` presumably?) 
    - Been searching but haven't fonud a past video.  Maybe we can do it at the end of the day.

62. Can we pipe grep in less command?
    - `/` searches (`n` / `N` to to next/prev)
    - `&` will limit to matching lines
    - less is super useful!
        - My question is `git show HASH | grep "keyword"` is it possible?
    - Yes, not a problem, you can pipe any unix command this way, even more complex stuff or a full script
        - Oh oops.  Yes, that works.  Since git uses less, maybe the hotkeys above are useful too (it's what I often do)

63. Can y'all correct answer to 52.?
    - I added some.



:::info
### Lunch break until xx:00
:::


64. Where can I find the "cheatsheet"?
    - Link now added to the very top
    - https://aaltoscicomp.github.io/cheatsheets/git-the-way-you-need-it-cheatsheet.pdf

65. Throwback to the push exercise: when I try to push it asks for username and password, and when i put it in i get this:







mic/win/linux?
    - tried ssh. Im on mac. After 'git push -u origin main' it asks for username and then password for https://github.com
    > got this issue too. If you have a key (or create a new one) it has to be called id_rsa.pub or id_ed25519.pub (there is a third one). It does not recognize any other key names. You also need to a) add the key to your user profile (didn't work for me) or as a deploy key to your repo (this did). And b) do all the stuff with the agent, etc or eventually creating a key -> https://docs.github.com/en/authentication/connecting-to-github-with-ssh/using-ssh-agent-forwarding). 


## Undoing and recovering

https://coderefinery.github.io/git-intro/recovering/

We can all start from this repository:
- step out of the networkx repository from previous exercise
- git clone https://github.com/coderefinery/recipe-before-merge.git recipe-recovery
- cd recipe-recovery


66. Regarding (computer) directory structure, do you recommend having one git directory in which one places all git-tracked projects?
    - I have a directory for projects. Each project has its own subdirectory. Some have multiple git tracked folders for some, the whole project is tracked as a single repository.
    - Git tracked folders can be anywhere, so I would follow which ever method you have followed so far, but start tracking some of the project folders.
    - Remind us about this qustion during the final Q&A, it will be perfect then.

67. What is a staged change ? (I forgot)
    - When you have added a change (`git add`), but not committed yet (`git commit`)
       - `git add` stages/prepares the change to be committed. it is a nice way to prepare changes and make sure to collect changes to nice logical units if you have many modifications in your working area.

68. how do you selecet where to restore with -p?
    - by default will ask for every file.  you can give a filename and it limits to that.
    - it will ask you patch by patch and then you can decide what to do with each

69. Can we 'revert' to a commit that is not the HEAD? If yes, what about the future commits?
    - Reverting goes back in commit history, so you can revert multiple times but this will revert multiple commits.
      - but reverting does not change the history before that revert, only adds new commits (the person who answered knew that but just to avoid possible confusion since we don't really go back, only forward) 
    - You can revert older commits.  If something has been changed since then, you get a conflict (and we learned how to resolve yesterday)

70. Can you demonstrate how to combine many commits in one commit?
    - there are several ways to do it but this is what I would do:
      - if the commits that you want to "squash" are at the end, then I would use `git reset --soft HASH` to the HASH just before the oldest commit to be squashed. This will "remove" commits but keep your changes and stage them. Then you can commit them all in one commit.
      - alternative and solution when the squashed commits are not at the end but somewhere "in the middle": interactive rebase, where you can squash, reorder, rename, delete commits, to your liking. in this case try an `git rebase -i HASH` where HASH is a bit more in the past than what you want to edit. it will open an interactive menu where you can do all these things. it's fun but experiment first on a test repo, not on your real code since rebase modifies history. 
      - before combining any commits, create a backup branch: `git branch backup`. If I mess up and all is destroyed, I can go back to that backup branch and all my commits are still there.
         - branches don't take up any space in Git so I always create a branch before a command that I am unsure about what it might do

71. I have fixed a change in ingredients.txt and entered `git add ingredients.txt`. When I enter `git commit --ammend` I get the prompt `You asked to ammend the most recent commit, but doing so would make it empty`.
    - Was your new change exactly the opposite of what the previous commit did?
        - Yes, would it be preferrable I did `git revert` in this scenario?
           - Since the change was only staged but not committed, if you want to modify it, I would modify, then `git add` again, then `git commit`.


:::info
### Exercises: undoing and recovering, until xx:42
https://coderefinery.github.io/git-intro/recovering/#exercise-revert-a-commit
- Do whatever exercises seem most interesting to you (four "Undoing" on that page).
- Undoing-1 to Undoing-4, any combination that is relevant for you
:::

71. What is origin/main in my case?: 40d63a5 (HEAD -> main, origin/main) Merge branch 'dislike-cilantro' Decided on half of the spoon
    - origin/main refers to `main` on origin and origin is the place we cloned from. Tomorrow (Thu) we will clarify these in more detail. but already at this point I can say that when we clone from a place, Git defines "origin" to refer to that place and it creates a local branch from the default branch (in this case "main") and it creates a read-only reference to origin/main ("main" on origin). If too confusing, tomorrow it will become clear.

72. I am getting the error "commit XXX is a merge but no -m option was given. fatal: revert aborted." after having committed a change in ingredients.txt.
     - you probably tried to revert a merge commit (double check this with `git graph`). you can revert a merge commit with `git revert -m HASH` (where HASH is the commit identifier)


73. Why do I have a red (origin/main) tag in my git graph? And then also a (HEAD->main) as the top-most tag.
    - I guess you used our sample repo.  This is the remote (origin, from where we cloned).  It says "this is what origin thinks is main".
        - I haven't cloned it, it's my original local repo. 
        - Ah.  We also added it as a remote yesterday!  `git remote -v` will list some details.
    - see also question/answer 71 (unless I misunderstood the question) +1
    - "HEAD->main" means "you are currently working on branch main, that's where commits will go" (record head is aligned with main)

74. Does the order matter with git add and git commit?
    - Yes.  Committing uses what has already been added.
        - You commit whatever you add, so commiting before adding will have no effect.
        

75. I am not getting a good understanding of a difference between commit and push. I have 2 local commits and now he is asking me to push.
    - Git stores your history locally on your computer. When you run `git commit`, it adds a new commit to the stored history. In this case, you also have a remote repository on GitHub. `git push` will upload your commit history to that online repository.

76. In which case it's more interesting to use `reset` instead of `revert` or create a branch starting from a previous commit ? 
    - if it is all only on my computer, I can delete the commit or even start a new branch just before or move the branch just before. but `revert` becomes interesting if other people already cloned that commit and add new commits based on the branch that I have published. Now if I delete it or change the branch, it will be surprising and confusing to others. Did it clarify?
    - sometimes you want to also keep a trace that you changed your mind, even if it is a single-person project. I use `revert` also just for me for those situations.

77. Yes sorry, I made a mistake in my question. It's `reset` that seems surprising since the 2 other solutions seem better.
    - yes, reset is find for local work but we need to apply it carefully for published branches.
    - advantage of reset: it makes the history look more organized
    - sometimes you really have to "remove" commits (for instance somebody committed a password), then you need `reset` and `revert` will not be enough
    - did these answer the question?
        - yes the password example is very clear!

78. Why it asks me to push when I try 'git commit --amend', but it does not when I do a simple commit ?
    - it asks to "git push" ? 
         - Yes, here is the message:
        ```
        "On branch main
        Your branch is ahead of 'origin/main' by 3 commits.
        (use "git push" to publish your local commits)

        No changes
        ```
    - You asked to amend the most recent commit, but doing so would make it empty. You can repeat your command with `--allow-empty`, or you can remove the commit entirely with `git reset HEAD^`.
    - When I do simple commit I get message I get: 
    > HERE is now something missing due to a weird multi-cursor editing glitch in HackMD archive. Sorry about that! -MJ
      > ps. always keep backups of your stuff you are editing, or better yet: a version control 🙈
    - "git commit -p
    ```
    No changes.
    [main bd26dca] going back to less avocado
    1 file changed, 1 insertion(+), 1 deletion(-)"
    ```
    - so it means that in both cases (amend or not) it did not make any changes?

79. Is amending only for editing the text in the previous commit message? Or does it also revert the previous changes, like with git revert?
    - It can add new changes (whatever you have `git add`:ed)
    - It will offer you to edit the message if you want
    - You can do one or the other
    - so if I edit a text file and do git ammend, I could revert the text file with ammend?
    - Yes, you could.  You'd have to do the exact opposite change, so other methods wolud be better.
    - ok thank you! :)

80. A curious question. If the branch does not take space, how does it behave in the memory? If it is not a physical copy then how is it done? 
    - Internally branches are just a statement "branch old-code is a515f51256d3...".  That commit is part of history anyway (probably), so the branch is basically no overhead.  If it's not part of history, well, you can figure that out.
    - There's a "git under the hood" episode that shows more.

81. There is git pull but there is also git fetch whats the diff?
    - Git fetch would be in advanced material, it's not something I use often. It downloads the remote branches and renames them to "remote_name/branch_name". It does not merge them with your local branches.
    - Git pull downloads the remote branch and merges it to your current branch (or another local branch if you specify it).

82. Can you demonstrate any example of using GitHub for version control when writing your thesis? Eg working in word and commiting to Git, is that possible?
    - Word and other office documents do not go well with git (at least not without some additional tools/plugins)
    - Usually people who version control their thesis etd documents use $\LaTeX$ 
      - If you feel LaTeX too overwhelming, maybe take a look into markdown
        - https://www.theurbanist.com.au/2018/02/writing-a-thesis-in-markdown/
        - https://paulihuhtiniemi.com/blog/2019/07/03/masters-thesis-markdown
        - https://github.com/tompollard/phd_thesis_markdown

:::info
### Break until xx:05
Then the general Q&A below.
:::

## Practical advice and general Q&A
https://coderefinery.github.io/git-intro/level/

"+1" the questions you'd especially like discussed

83. How will we get connected to participants to collaborate with tomorrow? Asking as an individual participant (who is sometimes out of office during this workshop).
    - RB: please follow instructions here (email from yesterday but not everybody might have gotten it): https://coderefinery.github.io/2023-09-19-workshop/communication/#2023-09-19-summary-day-1-and-preparation-for-day-3
    - this afternoon I will process such requests

84. Do most people who use git actually use git bash or any other terminal-window or do they use github desktop or visual studio code's git-add-on or other programs for git?
    - The command line interface (CLI) is older than the desktop interface for git, so it would probably be cli, but use whichever one is more comfortable for you.
    - for small things: web, for larger changes: CLI or Desktop or editor with git included (e.g. VSCode) 
    - WSL & terminal if you are in Windows. Or MobaXterm (not open source, but free). Notepad++ also has extensions. On Linux or Mac... terminal + vim / emacs 
    -

85. How do I push changes following a reset to the remote, if I had already pushed the changes I am reverting with the reset?
     - it probably errors that you cannot push because the remote contains commits that you don't have? if yes this is a good safeguard to warn you against accidentally removing commits in the remote. if this is the case, you can still force it with `git push --force origin SOMEBRANCH`

86. It seems really that understanding a git history of a project that you just want to start collaborate in is very complicated. How is it possible to collaborate in opensource projects? Is it even reasonable and if yes, what level of expertise in git is needed?  +1
    - Very good question!  There are so many complexities, but when contributing to some other project it's easier, since someone else has set it up.  You only need to be able to make a new change
    - Tomorrow ("git collaborative") focuses on that exact work flow: clone, make one change, send it back (two ways: directly, or via a pull request ("change proposal"))
    - the goal of tomorrow is to be able to do that

87. Is `git commit -p` per file or per line? And, if it is per file, why do not we just use`git add` the selected files?
    - per line ("a" does "all lines in this file")

88. How was the learning curve for you before starting using Git? How did you learn it? and at which point you decided you had to learn it?
    - We discussed on stream a lot
    - Most of us had used something lightly, but then change to get / got more proficient later on.
    - Try visual tools eg. GitHub Desktop if you struggle with git logic in the command line 😊

89. So, I have a project with already 60 scripts in there. I have the feeling is important for me to keep track of the next changes. How would I recomment I incorporate git in this already big project? Thanks
    - so I have multiple folders (like a complex folder structure) all is a part of a research project. Thanks
    - initialise the folder as a repository with `git init` and see content through `git status`. Stage and commit all or in chunks and include reasonable files to .gitignore. Then push to GitHub/GitLab and continue git workflow with reasonable size commits + consier using branches when trying new stuff.

90. What plugin/library/... would you recomend to use git, when your main programming language is R and Rstudio as a tool to use? +3
    - Rstudio has its onw integration, no plugins needed, just add the GIT option and the repo URL to the project (check the help )
    - There is a recent R package called gitgadget that provide addin for additional git commands that is not available in the default integration.  https://cran.r-project.org/web/packages/gitgadget/index.html
    - Alternatively I can open Git Bash (set this in the Global Options -> Terminal -> General -> Set new terminal open with Git Bash) as a terminal (Tools -> Terminal -> New terminal) in Rstudio to type complicated git commands and see the changes in the GIT option.
    Found also interesting guide: https://happygitwithr.com/rstudio-git-github.html

91. How do you decide what to push to git? What kind of things do you look for on github (or in what instances woudl you look for other peoples' code?) ((person w very non-technical background asking))
    - Usually you are pushing changes that you want to have on the remote repository. There is no single answer for this, but it depends on the project, your goals for the project and the contributions you would like to make. You can look at it in the same way as writing a book together with other people: what are the sections you are responsible for and what contributions would you like to make.

92. How do you go about finding the right commands? Sometimes I feel overwelmed by the man pages in git/linux or just forget the exact command
    - Google them and look for the most updated websites that provide answers to that. Try those commands and if they work for you then write them down for future reference. It's perfectly normal to forget a lot of the commands and have to look them up, so don't feel discouraged by that.
    - I really like the "tldr" command (needs to be installed), then for instance `tldr git push` it will give me short and nice summary of commands that I can use without too much text
    - Chatgpt? (I already trouble shooted quite a few problems during the course)

93. It is advised to not track binary files. Another curious question. Why not(in brief)?
    - When changing a file, it has to re-record the whole thing, and that can not be space-efficient. (though it does try to compress it).  That, plus not being able to diff, makes it not ideal
    - But we do have repos for minor photo storage, for example.  Since it's better to have them in the normal place than not be able to find when we need.
    - git-annex can be used to track larger data

94. Question 90. but with Python?
    - CodeRefinery conda environment has already a good collection
    - more important than plugins to a certain language might be plugins for your editor or environment where you write Python
    - Visual studio code has tools for python and git

95. Let's say I have `file.txt` and I add and commit and then I add the `.gitignore` file. And then I add the `file.txt` in gitignore. How would I untrack it? 
    - If a file is already tracket, it will stay tracked / keep updating if you change it even if it becomes ignored later.
        - How would I untrack a tracked file in git?
            - track: `git add`
            - untrack: `git restore --staged` 
            
96. Just a general question, as an expert in git and also probably fluent in a couple of programming languages, how often do you need to actually look things up? do you still do mistakes?
    - look stuff up: not that often, but most stuff we do is routine
    - I'll often run `git COMMAND --help` to check or review help pages when doing something I don't do often - always good to check!  For complex stuff always web search + stackoverflow - even now.
    - Whenever I need to run a git command other than `add`, `commit`, `pull` or `push`, I check before running.

97. So if I want to add the tracked file in gitignore, I have to untrack it first and then add to gitignore to ignore it. Am I right?
    - Yes. If the file is tracked, git will continue to track it even if it is already in .gitignore

98. Would we learn about `.gitignore` in the future sessions?
    - Not much more than we have now.  It basically makes `status` ignore files in there that aren't already tracked.

99. What is the difference between merge and rebase and why would I use one or the other?
    - here some discussion: https://coderefinery.github.io/git-branch-design/ (lesson is a bit old but still relevant)

## Feedback, day 2

### Today was:
- Too fast:ooo
- just right: oooooooooooooooo
- too slow:oo
- too easy:o
- right level: oooooooo000oooo
- too hard:
- Exercises were good: oooooooooooo
- I would recommend today to others: ooooooooooooooooooo
- I wouldn't recommend today: 

### One thing good about today:
- The questions were covered very well.
- I like the practical tips and discussion at the end +1
- Was cool to push things to github, and get to know the interface a bit better +1
- Good to learn about revert and reset
- we've learned very nice stuff (revert, history tools), the sherlock holmes exercise was very cool.

### One thing to be improved for next time:
- I know it is not easy but I would rather it be slowed down a little bit.
- I think it would be good to summarize and show very fast the solution to the exercises after the exercise +2
- I would skip exercise with online github reposittory from previous day as it was confusing at least for me, that it was introduced today as well. It created some confusion and problem as in previous day we did create README, but today we were not supposed to. This is a very minor thing, but I would wthink about that, apart from that it was really great :)
- it would have been nice to spend more time on the undoing and recovering part (and maybe a bit less on the history - it's very cool but we have more difficulties to know when to use them)
- it could be nice to recap the main commands a few more times when doing the exercises; I keep having to scroll up to remember the basics but I think hearing them again (and again.. :D ) would help remember them as well

### Any other comments:
- So glad to be in this course and learn git "properly" instead of bit by bit as the need comes up.
- you guys rock. Thank you! +7
- It has been a very valuable workshop for me so far. Thanks a lot and keep it up:)
- the sound level was different for each of you during the discussion
    - RB: I will get a headset to improve the situation

### Workshop mascot?  Anyone offer to draw it? (and we'll combine with CR logo)
- cat: oooooooooooooo
- gopher: oooo
- tree of souls from Avatar (symbolising git): o
- git goat: oo
- A hedgehog (HedgeDoc) ooooo
- Shiba inu: o
- not sure if one is necessary o

