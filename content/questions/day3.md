+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 3"
+++  
  
## Icebreaker

### Which types of projects can you use git, etc? Which will you use it for? (+1 what you agree with):
- Working on project (code) where we have different extensions involved. We can then share the work into smaller teams and then make sure everything come nicely together. +1
- Storing small amounts of pictures for our team (presentation material)
- Co-drafting a proposal
- Backups +2
- To merge changes from co-authors who send changes via email +1
- To sync my codes between different computers and clusters +3
- Drafting manuscripts with LaTeX.


### What cool thing/tool have you discovered/learned the past days? (independently of this course)
- That I can diff changes also directly on the web using 
    ```
    https://github.com/USER/PROJECT/compare/HASH1..HASH2
    ```
- That I can create branches where I can try out things and then merge (or not) if they work +1 +2
- Using git merge tools like kdiff3.
- From the comment above I learned that I can merge code that I got via email from people that don't like/want to use git
  
  
  
## Git collaborative
https://coderefinery.github.io/git-collaborative/


### Concepts around collaboration
https://coderefinery.github.io/git-collaborative/remotes/

1. After merging, does one always delete a branch?
    - most often I do but sometimes I forget and that is not a problem. It only starts to be a problem when there are 30 branches and I lose overview. To have better overview, it helps to have good branch names. I use for instance `myname-topic` to name a branch and so that I can find it again.
    - not always. Some branches may be meant to live in parallel for the entire lifetime of a project: think about `release` for the public and `development` for the backoffice work. Look at this classical implementation: https://nvie.com/posts/a-successful-git-branching-model/

2. How do I add a tag to a commit?
    - https://coderefinery.github.io/git-intro/branches/#tags (we skipped this on Tuesday)
    - or on GitHub/GitLab directly
    - with the command `git tag` in your local copy and making sure that you also push the tags to the repository: this is not the default and there are several options to keep in check. Look up this thread for some orientation: https://stackoverflow.com/questions/5195859/how-do-you-push-a-tag-to-a-remote-repository-using-git 

3. In what situations do you use fork as opposed to just cloning a repository?
    - if you want to also keep a backup of your changes on services like GitHub
        - Version control kind'a does this by definition, no need to fork? Not sure I understood.
            - Version control does what you ask it do it. There is no definition that governs the actions that are executed from case to case. Here the relevant distinction is between *where* the repository is stored: with `git clone` you make a local copy of remote repository, with forking you make a remote copy of a remote repository. And you play around with the former at your leisure because you are its owner. (Of course, the administrator of the first repository may want to limit your freedom to make a clone.)
    - if you intend to contribute your changes back and do not have write permissions to the repository that you wish to modify (this is the case for most open source projects)
    - At least whenever you want to work on a repository that you don't have write access

4. Are there any places where you can find public repositories listed, that you could join and collaborate with?
    - I would start with the tool/library that you use but where you have some ideas for improvements or want to "pay back" by for instance helping with their documentation and examples
    - Otherwise I sometimes like to browse GitHub by topics: https://github.com/topics/
    - For R, the NHS R community is looking for collaborators for their R4DS (2nd edition) solutions repsoitory. https://github.com/nhs-r-community/r4ds-ed2-exercise-solutions
    - For Bioconductor, the Bioconductor community is also looking for people to contribute to their blog pages to advertise Bioconductor packages. See https://blog.bioconductor.org/about.html and https://blog.bioconductor.org/contributing.html
  
5. Can we fork from GitHub to GitLab?
    - No, and we cannot send pull requests/ merge requests across services
    - But you can "mirror" (manually copy by cloning and pushing) a repository from one to the other but they will be "disconnected" and not see each other
    - these answers usefully imply that when you clone and fork a connection between the pair of repositories is mantained. The copied repo knows the (https/ssh) address of the source repo. I don't know to which extent the source repo has an adminstration of who has cloned/forked.  

6. Why should I create a template rather than forking?
    - template is useful if you want to create a number of repository with the same structure and have a template as starting point
    - however, templates are not meant to receive changes back, they are only templates. with a fork there is at least the possibility to send changes back to the place where you forked from

7. why would one fork instead of clone? How can you work on something if it is not on your computer?
    - see also 3)
    - but after forking you then still want to clone but then you would clone the fork (which you can modify and which you can push to) as opposed to the "central" repository which you might not be able to push to
        - that's correct, you clone from the forked repository and this gives you full control of what you do. The source repository may not give you any permission to change its content. So you can work locally and remotely with a fork independently. When you want to contribute to the source repo, then you *ask* its administrators to consider the change you did in your fork. This is the transaction of the *pull request*, to be presented presently.

8. When cloning, is only one branch of the repo cloned? How can I clone more than one branch?
    - when you clone, you clone all branches and all tags, everything
    - a clone is a full backup of the Git repository
    - i think you can also clone a single branch, but anyhow you should be able to push and pull a single branch. In that case the other branches stay idle in the cloned copy. 
        - `git clone` has a `--single-branch` option that probably serves this purpose. Refer to https://www.git-scm.com/docs/git-clone to investigate

9. If I clone a repo, do I have a remote of that repo as origin? Or, I should create a new repo?
    - yes, after a clone, it automatically creates "origin" which points to where it was cloned from
    - you can verify this with `git remote --verbose` which lists all remotes (addresses)

10. When forking a repo, is it later visible on the new repo where the code came from? (To give credits to the original author)
    - It will say under the repo name that it is a fork of the other repo.
    - but still good to check the license and also in the README or similar to acknowledge where it started from and what changes were made (more about that next week)
  
::: info  
### If you want to participate in collaborative exercises today as individual learner

- If you registered after the workshop started, you might not have received this email: https://coderefinery.github.io/2023-09-19-workshop/communication/#2023-09-19-summary-day-1-and-preparation-for-day-3
- TLDR: you can still join by opening issue at https://github.com/cr-workshop-exercises/access-requests/issues/new/choose (There click "Get started" -> "Submit new issue")
- Leaners who are part of team do not need to do that, you will form your own exercise
- ~~13~~ 8 persons who requested access have still pending invites, please check your email inbox for the email that you registered in GitHub with
:::


11. When forking a repo, is my fork in some way "connected" to the original repo, can I for example pull new commits from the original repo?
    - yes exactly
    - example: https://github.com/coderefinery/git-collaborative/forks (this lesson)

12. If I push to my fork will I need to do a pull request if I want it to become part of the central repository?
    - yes and we will exercise that

13. Is it "better" to fork than clone, since you can contribute back to the original repo? Or does it just depend on the context?
    - if you have write permissions to the original repo, cloning is enough (first exercise today) but if you don't have write permissions, you first need to fork, then clone the fork (second exercise today)
    - ok thanks! I'm a bit confused about the difference but I'm sure it will become more apparent through the exercises! :)
        - the easier thing is only to clone directly but then you need to be able to push if you want to send changes back. you can always push to your fork since it then belongs to you (in terms of github access permissions; maybe not in terms of license/copyright). but it will become clearer during exercises.
           - I see, thanks!

14. How is it possible collaborate in centeralized workflow and not get conflicts? Who would solve the merge conflicts?
    - There could be conflicts, but it would be up to whoever is in charge of the repo to resolve those conflicts or there can be a discussion of that by using the commenting feature.
        - the conflict resolution does not have to be on the maintainer, it can also be done by the person contributing
    - A person should solve conflicts before they push (a person needs to pull, resolve conflicts, then push).  If using pull requests, then it's done as part of that pull request
    - Conflicts are usually rare because people try to share quickly, before too much happens.  And talking with people to not do the same thing twice.  (if you wait a long time before sharing and don't communicate, it can get bad!  But then it would be bad no matter what you did when collaborating)

15. I still dont get how the remote repositpry and local repository can be synced real time? is it even possible?
    - we sync by `git push` (from local to remote) and `git pull` (from remote to local) - so you decide when to sync. Git does not sync automatically. did this answer the question and clarify?

16. where to fine repository URL is it just the URL when we click on the repository we want to collaborate?
    - yes exactly. if you are part of a team, then the team leader sets this. if you are part of stream collaborators, it is either:
    - SSH protocol git@github.com:cr-workshop-exercises/centralized-workflow-exercise.git or git@github.com:cr-workshop-exercises/centralized-workflow-exercise-recorded.git
    - HTTPS protocol: https://github.com/cr-workshop-exercises/centralized-workflow-exercise.git or https://github.com/cr-workshop-exercises/centralized-workflow-exercise-recorded.git


:::info
### Break until xx:56
:::


## Exercise preparation

:::info
### Exercise until xx:35

https://coderefinery.github.io/git-collaborative/centralized/#exercise-part-1-creating-a-pull-request

- Goals: Do parts A-H.  STOP at part 2, don't do that merge yet (we do that together).
- try to browse the "network" for the exercise repo: -> top bar "Insights" -> "Network" - you will see other commits in there
- don't forget to "unwatch" if you don't want to get email notifications about pull requests
- stream participants: you now got write permissions, please do not go too far in the exercise yet since you can now change the repository
- exercise leaders: please check that the default branch in your exercise repo is "main", not "master" (we changed this few days ago)
:::

17. How can we create a template? Is it the same concept as git submodule?
     - it is not the same as git submodule if this is what you meant
     - in any git repository that you create you can go to settings and then set the repository as template (Settings -> "Template repository")

18. As a maintainer, do we have to protect the main branch ?
     - for this exercise you don't have to but to prevent accidental pushes directly to main, I would write-protect it and only allow changes through pull requests. please ask if it is unclear how to do that.

19. What are the differences between these two? 1) First, fork a public repo and then clone the forked repo to my local 2) First, clone the public repo into my local, and then upload this local repo to my namespace in the remote. What does the fork so extra?
     - the extra of the fork part will be that the fork will remember where it was forked from and it will then be easier for you to send changes back to central public repo through a pull request.
         - Also, you will be informed if your fork is ahead or behind the source, meaning if either of you have committed more than the other in the meantime  
     - example of fork relation (this lesson): https://github.com/coderefinery/git-collaborative/forks - you can click on any of those and on top left they will show where they were forked from

20. Do I need to wait before I could merge my branch locally to my main? What's the typical process? 
     - we will recommend the process that somebody else reviews so that we get a bit of code review and collaborative learning. I recommend to wait with that. We give a lot of time for this exercise block so that everybody can catch up.
        - I meant more like in real projects. If I would locally merge my branch to main and not push it. Is this okay?
            - for single-person projects you can merge any time, locally or on web. but agreeging on not pushing directly to main can make sense if you are 2 or more people on the project
    - in terms of computational thinking it is always wise to think ahead of *what* you would be waiting for when you think about waiting. Otherwise you could wait forever. A way out of this loop is that before merging you need to look what you would be merging. Here your friend is `git fetch`. `git pull` is in fact a composite command `git fetch` + `git merge`. Fetch tells you what happened in the remote without touching the files you have in your local repository.
  
  
21. Suggestion for those who are done
     - you can try to send another pull request and try to create a conflicting one if you want to see how conflicts look on github and how to resolve those

22. I was wondering where could we find the SSH of the repository if you hadnt provided here?
    - yes, example: https://github.com/cr-workshop-exercises/centralized-workflow-exercise - there on top right is the green button `<> Code` and clicking on it you can switch between SSH and HTTPS and you can see the actual address

23. After I hit 'git push origin -u something', I still get this message "Enter passphrase for key '~/.ssh/id_rsa'". Afterwards I get a permission error. I have used the SSH url.
    - I woder if the SSH key is set up.  You can test with: `ssh -T git@github.com` - does it show your username or not connect at all (you'd probably need the *ssh key* password again, not Github passwword).
        -  I did it. I can connect after typing in the ssh-key password. However still I cannot connect to the cr-workshop-exercises/centralized-workflow-exercise-recorded.git, permission denied.

24. I am still a bit unsure about the meaning of origin. When exactly did we define it in the exercise?
    - when you clone a repo, it automatically sets it to the address where you cloned from. on your computer, try `git remote --verbose` which will list all remotes (in this case you have one) and their addresses
    - `origin` is just a generic name for a remote computer that gained acceptance as first choice; origin is actually a certain type of server. 
You can change that name into `anything` with `git remote rename origin anything`. Then you would do a `git push|pull anything your-branch`. `origin` is one alias name for the full remote address: look up `git remote -v` to  check this association. 
Final note: that origin is arbitrary name shows up nicely when a local repository has more remotes, which is certainly possible. 

25. should teams already start reviewing?
    - yes we can start merging now :-)
    - please review other people's changes and merge those, not your own

26. I am getting this error.![](https://notes.coderefinery.org/uploads/13b5c1fc-7b3c-4967-b7bb-8c22afa29777.png)
    - is this one of "our" exercise repos or a team repo? (you don't need to paste explicit address)
        - It is the non-recording public repo `entralized-workflow-exercise`. I am already in the team `stream-exercise-participants`
        - I get this too...
        - RB: OK I see, fixing in a minute
           - fixed. sorry our fault when setting it up
             - explanation: merging to default branch was accidentally restricted only to staff
  
  

27. We misunderstood a bit and created our own github repo to which we did the exercise on, will this affect our certificates?
    - oh no this is great and ideal situation. it's good that you practice with your own
    - Are their certificates??
       - depends on location, see also https://coderefinery.github.io/2023-09-19-workshop/certificates/

28. Those participants on the stream, can review right? because it seems we dont have permission for reviewing
    - yes we can start merging :-)
    - please review other people's changes and merge those, not your own

29. I dont think we have permission for reviewing? it says merging is blocked +2
    - is this here? https://github.com/cr-workshop-exercises/centralized-workflow-exercise
    - RB: fixing ...
    - fixed (hopefully)
    - Now it is working!
      - explanation: merging to default branch was accidentally restricted only to staff

30. Who will merge the centralized-workflow-exercise?
    - RB: I recommend that you try to merge a change from somebody else. I will also merge couple of those

31. The other branches apparently don't apppear to my local pc after pulling?
    - you did something like `git pull origin main` ?
    - yup
       - try:
          - `git fetch origin`
          - `git branch`
          - `git branch --all` (you have then all branches)

32. I have tried to review and merge, but I get following mesage: "This pull request is closed, but the BRANCH_NAME branch has unmerged commits." I am not sure if that was succesful.
    - Not sure, either the pull request was merged succesfully, or accidentally closed. Did the changes make it to the main branch?
    - There are new commits after the pull request was closed, so maybe they added another commit?

    - I think it did not:
      ![](https://notes.coderefinery.org/uploads/f6a279c6-2b54-4eab-99bb-bd83fae96bd1.png)
       - OK, you can recreate the pull request and try again. (I checked but did not find a way to reopen a closed request.)

33. when pulling, should you switch to main or is it possible to stay on your own branch and still main would get updated
    - you should switch to `main` - a pull will modify the current branch

34. For the certificates, you require the output of each terminal command. How do you expect we hand these in, in what format? And copy-pasting each seems a bit much work?
    - (will answer later, I need to read up on what the page says)
        - where does it say output of each terminal command? https://coderefinery.github.io/2023-09-19-workshop/certificates/ (this is an honest question, just trying to locate it)
        - I was refering to this line: 
        ```
        "The output of git log --all from the repositories that you have used during the course as a text file. Evaluation criteria: we expect to see the results from most of the git commands that are run in the first 3 days of the workshop." But maybe my interpretation is incorrect`
        ```

:::info
### Lunch until xx:00
- We can keep answering questions here
- after lunch, we look at a "forking workflow"
:::


35. When do I run `git pull` and there are multiple branches in both local and remote, which remote branch goes to which local branch? what is the default workflow?
      - it depends on your configuration. and since it depends, I prefer to do it explicitly: `git pull origin somebranch`, then I know I am pulling `somebranch` and always only modifying the current branch. but some people like to configure `git pull` to update all local branches.
      - if you type only "git pull", you can configure git to update current, matching, or all branches

36. Any recommended tools/extensions for working with VSC and git?
     - hopefully somebody who uses VSCode can answer (vim/helix user here who does not know)
     - I think it works out of the box (at least I haven't installed something).  I think that's probably the starting point (I don't know beyond that)
     - There is the GitLens extension. It has some free functionalities like seeing commit details, diff, and some others. And some extra paid functionalities. The free ones are good enough I think. 
     - I go with preinstalled stuff only

37. "Notice how after the pull request is merged, the issue gets automatically closed. This only happens for certain keywords like closes or fix." Is it a default setting for git or was it set up for your project configuration?
     - default behavior in github (and gitlab):
       - [Linking PR to an issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue) 
       - and specifically the usage of *keywords* in [Linking PR to an issue using keyword](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword). 
       - Therefore, you do not want to use these keywords in the commit messages inadvertently: a statement like 'partly fixes' will be read as licence to completely close the issue, I fear. (You can reopen an issue.)

38. I managed to simulate a pull request on my own repository but I cannot do it with the exercise repository?
     - fixed it! 
          - excellent

## Distributed version control

https://coderefinery.github.io/git-collaborative/distributed/

39. My pull request was "closed". Does it mean it was refused? And should it in this case not dissapear from my fork after doing a `git pull` ?
     - I assume that this was done by accident. Indeed "closing" is a mechanism to either "reject" or "retract". But there should have been an explanation why. Normally there is first a discussion requesting changes before a pull request is closed. The branch still exists on your fork and the closed pull request can still be re-opened. You can find it under "closed" pull requests.

:::info
## Exercise preparation, until xx:47
https://coderefinery.github.io/git-collaborative/distributed/#exercise-preparation

goals/notes:
- no need to request write access or add collaborators because the point of this exercise is that we don't have write access
- steps A-F, create a pull request
- don't merge yet.  We merge after the exercise during the discussion.
- But it is no problem to merge earlier together if your team prefers.
- if you get "bored", try sending another pull request that will create a conflict so that you can see how it looks on github and how it can be resolved in the browser
- again, try to browse "Insights" -> "Network" on the central repository

(after the exercise: 10 minute break, back on stream xx:57)
:::

40. Where can I find the "Create issue" button?
     - top left -> "Issues"
        - found it, sorry! I was on my own forked one..
           - ah! no need to apologize. it is a great question. you now see that forks by default do not track own issues. this is a good default that issues stay in the central repo so that there is never a doubt about where issues are tracked. this can be changed though.

41. where can I see the issue number?
       - click on the issue and on top you see the issue title and then for instance `#123` if it is the issue 123. Found it? Example: https://github.com/coderefinery/git-collaborative/issues/269 (this is issue number 269) 
         - yes!

42. How to edit last commit? I think we learned that. I forgot to include my issue number in the commit message
    - `git commit --amend -m yournewcommitmessage`
    - If you don't give `-m` it will reuse the old message and let you edit it again.
    - a workaround is to edit the pull request title. you can also auto-close issues from the PR title or PR discussion

43. How do I verify where “origin” points to?
    - "git graph" to have a visual representation
    - `git remote -v` shows the URL
        - Thanks!

44. I did additional (optional) Distributed-3 and commit was succesful, but I don't see it on github, what may be the reason?
    - you should see a new commit added to the same pull request. it does not show up there? if you like you can share URL and I will look and edit out the URL again but no pressure.
    - (URL redacted)
        - OK so there is only one commit here. Try to add and commit and push another commit to your `add-mayo-proposal` branch
        - AA I forgot to push :)))
            - now it appeared. good. yes. until you push it only exists on your local repo.
Yeah, thanks for reminding me :)

45. after step D, should I do "compare & pullrequest" on the fork?
    - yes. but even if you visit the central repo it will on top suggest you to open the pull request

46. do we need to always use the web interface to pull request?
    - it is possible to open and manage PRs from command line
        - https://cli.github.com/
        - https://hub.github.com/
        - https://github.com/NordicHPC/git-pr

47. I still don't see a difference between having had a repository cloned and then work on a branch and send a pull  request or fork a specific branch of a repository then clone and work on it then send a pull request. Is it for when the repository is too big or permission is limited to only some branches? or other reasons?
    - Please do not assume that the people who make a repository openly accessible appreciate uncritically the fact that you have a copy of it. The pull request is *your* request that *they* pull your changes. Which is a roundabout expression to say that they will not trust your changes until they have time and inclination to check what you did.
    - If you use your own fork repository, you have the possibility to distribute your own version of the original software to a new audience. This scenario implies that you play around with repositories after you made yourself familiar with the license terms, though.
    - I am not sure I understand the question. Can you please clarify what the two alternatives are that you are unsure between?
    - okay yes now I get it more or less. I thought the only differnece between cloning the whole repository and forking a branch from the repository and then cloning the forked branch was just the size of what you store on your computer.
         - when we clone and also when we fork, we copy everything, all branches. if I only wanted to have one branch somewhere else, I would clone and create a new repo somewhere else and push that one branch to it. Use case: you have a private repo with lots of branches and a public repo with the published code (main branch).
    
:::info
## Break, until xx:57
:::

48. It would be interesting to hear more about the different copyright licenses (or get some links to read more about them)
    - We'll talk about this next Tuesday in "Social coding"!  There's a whole section on them and practical advice.
    - Oh nice! Looking forward to it!
      - I also look forward (co-instructor here who will teach this and still needs to update material, haha) 

49. Mentioning the issue in the commit closes the issue. is that a fature og Github specifically? 
    - Yes (not a part of git itself - pull requests/merge requests are Github/Gitlab concepts) - but other platforms do similar.
    - Probably not, https://stackoverflow.com/questions/9630774/how-to-make-pull-requests-without-a-github-account suggests that git is able to arrange pull request. In that case GitLab/Hub are exploiting git features under the hood
    - see also next question with links to what keywords github and gitlab look for in commit messages and pull requests
    - it is a feature of github or gitlab. it is not built into git itself.
        - In contrast, https://www.git-scm.com/docs/git-request-pull shows that this is a feature of native git
            - this looks to me unrelated to the cross-referencing and auto-closing feature but also the `git request-pull` is new to me so I need to read more
                - This reservation is sensible

50. was that the #N in the commit that made the automatic closing? and is there a specific way of mentioning the number? like always with #?
      - it was the `closes #123` part (here assuming it would be issue 123)
      - default behavior in github (and gitlab): https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue and specifically the usage of  I wanted to  I words* in https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword
      - but yes, the "#" needs to be in there, also some keyword like "closes" or "fixes".
          - ...and "resolves". This is detailed in the two links just above

51. I wanted to make a conflicting pull request, but now I have to enter a passphrase and then I get the message ERRO: Permission to -cr-workshop-exercise ... and fatal: COuld not read from remote repository 
      - was this the first pull request you try to send? or the second one?
          - It was the second one
    - did you push to your fork or to the central repository? (in this case you cannot push to the central repository)
        - I think I tried both.. I changed the ssh url in this command: git remote set-url origin git@github.com:cr-workshop-exercises/forking-workflow-exercise.git and tried with the forked and the central repository
    - it should let you push to your fork, verify with `git remote --verbose` where the remote points to
        - So the it should point to the SSH-key for the forked repository?
          - if you wanted to push using SSH, the remote should start with `git@` and it should be the address of your fork.

52. Could you pull from the central repository if you add it as a remote as above mentiond: `git remote add upstream ....`
    - yes!
    - how would you do that?
         - https://coderefinery.github.io/git-collaborative/distributed/#exercise-part-3-updating-forks
         - check the 2 command line examples there (longer version and the shorter version)
            - Got it, thanks!

53. General git question: If I, for example, get code from someone else via email how would I go about merging that with my code? I would think the first step would be to create a new branch so I can easily go back if things don’t work but then I am not sure how to “import” new files in that branch.
     - yes you probably want to apply the patch that you got via email as a commit to your repository. note that git even has functionality to send patches via email from old days when there was no github. the next question will then be: where to add that code you got as new commit? at the end of "main"? or somewhere in the past? it might be a good idea to apply it in the history close to where your collaborator started (maybe they got your code few months ago, worked in isolation, now come back via email). in this case it might be not too bad to create a branch in the past, apply the commit there, then merge to `main`.
     - in short: yes, create a branch, add as one commit, test, then merge or not. and create the branch either from "today" or from the past, close to where they started.
     - were the answers somehow helpful or confusing? happy to answer more or differently
         - definitely helpful! But I have a follow-up question (54.)

54. I struggle a bit with naviagting the terminal and since branches are no physical folders I wonder how I get the files from my "downloads" folder for example into the correct branch (sorry, simple question probably)
    - I really understand since branches are like an invisible layer on top of the file tree. So to get them into the right branch:
        - `git status` (check where you are)
        - `git switch --create NAME` (create branch called NAME and switch to it; in this case from "today", you can also create it in the "past")
        - `git status` (verify that indeed you are on that branch)
        - now copy files from Download folder over to your Git repository
        - `git status` (they should now show up there)
        - git add and git commit them
            - Awesome! Thanks! One more question if you don't mind.
                - keep them coming.
                            - :D will do (55.)
55. How would I go about adding them "in the past"? I remember using the log to find a hash in the past but did we create a new branch then as well?
    - `git swich --create NAME HASH` (where HASH is the identifier in the past)
        - THANK YOU!
    - basically you want to apply the commit at the place where the diff will be smallest. if that makes sense.
        - yes. definitely.



## Feedback, day 3

### Today was:
- Too fast:
- just right: oooooooo
- too slow:ooo
- too easy:o
- right level:oooooooo
- too hard:
- Exercises were good: ooooooooo
- I would recommend today to others: oooo oooo
- I wouldn't recommend today: 

### One thing good about today:
- Loved the engaging exercises
- I liked the "redundant" explanation about some stuff (chaging from HTTPS to SSH URL), saves a lot of time seraching for the command (!) +1
- Really liked the exercises! We had great discussions in our in person team as well, was v helpful to understand. Feeling excited to understand more, and actually have the opp to collaborate on projects in the future
- Good and fast responses here really helped me. Thank you! +2
- I love that I can try things out even though I don't have a team. I usually work alone so it's good practice.+1


### One thing to be improved for next time:
- Real Tacos provided +2
    - I basically had some for my lunch!
        - wow! immersive learning. 
    - all we need now is some guacamole... :D
- This topic is not too complicated conceptually but it requires more practise and time for exercises. I would have added few more tasks (optional maybe) to the exercise proposed and show more cases.

### Any other comments:
- It would be really nice if we could get some tips on how to find an openaccess repository and how to find where to contribute in that project. How to make sense out of other repositories when starting the collaboration? +1
    - The maintainer usually will create a CONTRIBUTING.md file to create the rules and guildlines for others to contribute into their repository.
    - For maintainer, a good template of creating a CONTRIBUTING.md file (for R pacakges) can be found in https://gist.github.com/peterdesmet/e90a1b0dc17af6c12daf6e8b2f044e7c
- A vote of thanks to all the organisers, teachers and assistants who have contributed towards this course, it is highly appreciated. Keep it up and enjoy the rest of the week !
    - thanks!
    - thank you all for your time and good work!
    - Recommended to my colleages (SURF.nl)
- One last issue: You have this wonderful documentation on the web, is there a simple way of printing all those webpages? Being a little old school, I sometimes find it nice to read a document on the sofa in paper.
    - oh, good question!  We are working on printable versions (converting t o a PDF, but they can be rather long)
    - looking... https://coderefinery.github.io/documentation/_static/lesson.pdf
        - is that useful?  Number of pages is a lot.
        - There is also a way to make "single-page HTML" version which you might be able to selectively print/browse?  (that's actually where the PDF came from)
        - That is exactly what I was looking for. Only, it is for one of next week's lessons. Is there a similar document for the three days this week?
    - We pllan on auto-generating them for all.  Maybe I'll work on it sometime.  Can you make an issue in this repo asking for it, so you'll get notified?: https://github.com/coderefinery/git-intro/
        - That woud be brilliant! Thanks. Will create an issue on that and the other GitHub pages.
        - I'm actually enabling it now.  look for them at the same paths soon (changing `documentation` to the other names)
