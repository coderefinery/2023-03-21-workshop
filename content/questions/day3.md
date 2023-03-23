+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 2"
+++

## Icebreaker questions:

Which types of projects can you use git, etc?  Which will you use it for?
- Internal lab knowledge / documentation (+1)
- PhD thesis summary
- Script of my PhD version control (+9)
- Bookkeeping all my codes and papers (+3)
- internal documentation
- Sharing scripts related to a publication (+4)
- Store codes for future using (+2)
- Research collaboration in projects with multiple partners where we collaborate at code level (+3)
- Version control of my models (+2)
- Version control for my analysis and sharing code for papers (+2)
- Version control and repository for research group code (data scraping and cleaning protocols etc.)
- software development (e.g. R packages) (+maybe 1)
- Making personal websites via Hugo and host it on Netlify for free

I am watching:
- by myself: oooooooooooooooooooooooooooo
- in an organized group: ooooooooooooo
- group is online: oo
- group is in-person: oooooooooo

After the course, I refere to these things by the next day:
- Course webpage:ooooooooooooooooo
- Lesson materials:ooooooooooooooooooooooooooooo
- Twitch videos:ooooo
- YouTube videos:oooo
- Friends or colleagues for help: ooo

### Icebreaker questions / Discussion on intro


1. Will we receive a certificate at the end of the workshop?
    - Info here: https://coderefinery.github.io/2023-03-21-workshop/certificates/
    - Let us know if something is unclear and we can make it clearer :) 
        - "git log --all" only shows commits - is that all we need to submit for code?
            - Yes there won't be actual code to submit

2. Should we check "all activity" or "particiation and mentions only" for the exercise repositories?
    - select "participation and mentions only": this way you get notifications about the changes you are involved in but not about all changes
        - For me this was the default setting, did not have to change anything
            - oh! that's good. we were thinking a lot on how to make this default for all but we were not sure how. maybe this just worked.
            - we wanted to make sure that you don't get too many emails during the exercise

3. [name=Marijn] is talking about this project https://github.com/mne-tools/mne-python a neuroscience analysis toolbox that grew by incrementally adding features from a small group of developers to hundrends of contributors.

4. Heads up: the youtube videos are titled September 2023...
      - we realized this morning. thanks for reporting. we will fix

5. Why the name pull request and not push request?
   - better name would be merge request or change proposal. under the hood it is implemented with a git pull
   - I think in gitlab it is merge request and github is pull request
     - yes
    - Maybe a following question, what is the difference between git pull and git fetch?
      - Oh that's a good one.  So "fetch" is "see what is on the other side".  "pull" is "fetch + merge automatically".
      - for the good practice, which one is preferred?

6. Question from yesterday. If I create a branch from version master m3 for example and I stay in the branch for a while. In the mean time, people have modified the master multiple times arriving at m6 for example. When I merge my branch back to the master branch would include all the changes that have been done in the mean time until m6? What exactly the commit m7 would include? 
     - The short answer is yes. The commit m7 will contain the work from the branch and the content of m6. If there is a merge conflict, this has to be resolved before merging into m7.
     - Thank you

7. Question from yesterday. Multiple files modified at the same time but related to each other would they need to be added and committed at the same time or is it better to commit them separately?
    - Good question!  You can add multiple times befor committing.  This would be recommended when they all go together.

8. What were those important points for managing a large project again? 1) Fulltime person managing merging; 2) use automatic tools (linters and CI tools); 3) set up a Code of Conduct for contributors...?
    - I think an additional point is to make sure there are systems in place that prevent changing main without getting a few sets of eyes on the changes. The purpose is to prevent changes that would break the main code.
    - Here were my ([name=Marijn van Vliet]) "growing pains":
        1. Lots of issues and pull-requests coming in that need comments and revolving. This can take a lot of time when you attract more contributers. With [MNE-Python](https://mne.tools), we had the fortune of attracting research funding to hire someone fulltime to work on the project. However, there are also many stories of open source projects where the initial creator starts to get overwhelmed. Take care of yourself. And try to let go of the reigns once other collaborators join your project.
        2. The burden of reviewing pull-requests can be reduced a lot by good use of continuous integration (CI) robots. These are automated scripts that go over the code and check for the little things. Any spelling mistakes on your variable names? Any unit tests that fail? Does new code have accompanying unit tests? Etc. Over time we've added more and more of these CI robots. So much so we talk about "fighting" them and "winning" when they all report back green. Once all our CI robots are happy, your code is probably in pretty good shape.
            - This is so interesting to hear - thank you! Does automatic code testing have a role here too? (edit: of course... unit test => code tests etc). CI seems like a superpower... worth learning.
                - CI == automatic code testing in a way. Also things like spellcheck are formulated as just another unit test that needs to pass.
        3. Issues and pull-requests are submitted by people. You want to make them welcome and tell them how grateful you are for their time. This means responding to them somewhat quickly and also creating a safe space for them to have their voice heard. Typical human biases and flaws (sexism, racism, etc.) are rare but will start occuring once you have enough contributors. You need a code-of-conduct document in place and importantly a well defined mechanism for enforcing that code-of-conduct.

9. Not a question, I'm just happy the Saga of the Instructor's Cat is in the archived notes for posterity. :-) :-D
   - Sure! :innocent:

10. Can you please repeat the name of this invited expert?
    - [name=Marijn van Vliet] talked about [MNE-Python](https://mne.tools/stable/index.html)

11. Is this HedgeDoc system open source that we can also use it for teaching? 
    - HedgeDoc is an open-source project, you could use it yourself.  notes.coderefinery.org is hosted by Aalto and I wouldn't recommend to use it for others.  HackMD.io is another version of the same that is free for use online - I'd recommend starting there.

12. Will the Coderifenry website be available indifinitely after the completion of this course?
    - Yes (and continual updates as we teach and develop)

13. I understand the power and advantages of Git - using branches etc. However, how do you implement for example in python: if i create a new branch, how do I access that in my environment? Do i change the branch (git checkout) in terminal and then open an environment? 
    --> for a little more context, i mainly use jupyter lab
    - When you do `git checkout <branchname>` you switch to the branch. For any editor or jupyter lab session will then work on the `branchname` 
            - Does the editor show in which branch you are working?
      - Basically any editor/file browser sees those files/versions that are in your current branch. When you change branches also the versions you see change.
         - So it would be better to not use the same shared folder, right? Otherwise if one user in the shared folder changes the branch, it affects all others. 
             - Exactly. The design behind Git is that everyone has their own folder. And then you let Git take care of merging those individual folders together.
             - what about when working on a shared server? I have my own designated repository.
                - The server has its own folder. Say we have two people working on a project. It's typical that A has their own folder on their machine and a folder on Github (A's repository). B also has their own folder on their machine and folder on Github (B's repository). Both A and B are syncing their local folders with their folders on Github. Then, they instruct Github to start merging A's and B's Github folders together. For example, to merge B's Github folder into A's Github folder. Finally, both A and B need to sync their local folders with their respective Github folders to have them reflect the new situation on Github. So, folders everywhere!
                - folders everywhere indeed! 🤯 i also use my own repository that only i work on in a server. it is a server run by my lab group and each member has their own designated rep. in which case, it's fine to run Git in the same way as if it is a local folder?
                    - Yes!
    - For Jupyter Lab I'd recommend activating the CodeRefinery Conda environment and then launching Jupyter -> There's Git plugins installed and visible in the left toolbar
        - okay. thank you both (i think?) for your help :) which left toolbar do you mean?
        - also, do you have a recommended environment to work in? i'm aware there are more functional options than Jupyter (i am a Mac user)

14. Not from the exercises but related to ssh issue. We have 4 memebrs in my lab working on the same PC. We always have issue to switch between our own ssh keys to push in our private repo on github. Any suggestions?
     - Do you all have different user accounts on this PC or do you use the same account? If you all have different accounts, each of you should have an "home" folder and there you can store your personal keys.
         - We have the same PC account (user@lab-pc), We have created our own ssh keys and stored them in .ssh. I also tried some tutorial where we mention these keys in config but couldn't manage to get it work
         - Use multiple ssh keys, and password protect them?
     - The `ssh -i FILE` option can specify which key to use.  Maybe not a perfect answer but can work around?  Hm, but to use that in git... there's an option for that.
         - `git -c core.sshCommand='ssh ssh -i /PATH/TO/ID_FILE' fetch` does a single git operation with the key you specify
             - What do you mean by single git operation? Is it not that the ssh key changed untill its executed again with other key or only for one command ?
             - You can specify which SSH key to use in the repositories git config. This way, different respositories and use different keys by default when pulling and pushing from and to github. That should make things a little easier.


## Collaborative distributed version control
https://coderefinery.github.io/git-collaborative/

### Concepts around collaboration
https://coderefinery.github.io/git-collaborative/remotes/

15. What happens if you tag a commit on a branch which is then merged into a "main"? Will the tag only live on that branch? And possibly removed if the branch is deleted?
    - Tag stays on that exact commit.  That exact commit stays "alive" and you can still see it was a branch
        - :+1:

16. Is a Tag just a commit with a human readable name? (+1, but not a commit but a hash?)
    - Pretty much.  Well, more like a human-readable pointer to a long hash.
    - Tags must be unique? What happens if someone tries to tag two commits with the same tag?
        - Tags must be unique in the same repository (I think, but I never actually tried)

17. When you should use tags and how often? Because technically we can find a needed place via commit description? Or I am incorrect?
    - I tend to start using them once my project becomes important enough that the memory matters. For example, I release official versions - I want to be able to refer to those versions.

18. Does git clone become git fork by commiting the changes of the cloned repo to our repository?
    - `git clone` and `git fork` are two different operations. You can see it as follows: clone (cloud to local) whereas fork (cloud to cloud).
    - Commit takes us from local to cloud though.
        - No, commit puts your changes in the staging area. Push is from local to cloud.
    - Then clone + push = fork.?
        - No, usually it's fork then clone then make changes then push back to the cloud (which would be the forked repo).
    - That was useful thanks!
        - You're welcome :) 

19. Is it understood correctly that if you are not in a team you are not actually a part of the collaborative exercise?
    - We have a form that works for everyone - follow stream (request access as per email last night) and you can be part of the "whole livestream team"
    - Cool cool. Already did that, but the phrasing made it sound like "well good luck if you're alone" lol
    - Sorry about that, but yeah, it's hard to explain when so many ways of attending!
    - Of course :) Would just feel a bit cheated on if you wouldn't get full experience alone and it wasn't clear before the workshop started.

20. What is the difference between fetch and pull?
    - `git fetch` fetches updates from the online repository to the local repository. If there are two commits more online than what is locally, `git fetch` will fetch those to commits, but it will only fetch the commits. This makes it possible to insepect the new commits before merging. Merging will be and addtional operation that has to be done explicitly.
        - Ok, but if there're conflicts in commits between remote and local, what are the different outcomes between fetch and pull? Would pull try to merge automatically?
        - `fetch` will only update the local repository. `pull` will do a merge. If there is a conflict `pull` will probably abort in the middle of the merge and give a message that there is a merge conflict that needs to be resolved.
    - `git pull` do two operations. It will fetch like `git fetch`. In addtion it will merge the commits from the online repository onto the local repository.
        - will there be conflicts if pull will also do merge job?
            - Typically, you will work on your own branch. The `git pull` will collect the changes on master/main branch and apply those to your local master/main. In this way you avoid conflicts.
            - if two or more people are changing  the same branch, in this case, if i do the pull, will there be any conflicts?
            - if the two people changes the same lines in the same file(s) on the same branch, there will be conflicts.
            - in this case, will git fetch be better to show the changes on other side not to merge?
            - yes, in this case `git fetch` will be better, as you can inspect the commits that you have fetched.
            - Thanks for explanation

21. How can I check if the remote repository has changes without affecting any file in my local repository?
    - `git fetch` then `git graph` / `git log` shows without affecting your files

22. Why is it called a pull request and not a push request, given that you do it in order to push your code?
    - It is confusing at first, but you can think of it as "pulling into the main branch".
    - This is also different depending on which git service you use. On github it's called `pull` request on gitlab it's called `merge` request.
    - On Bitbucket, it's also known as a 'pull request'

23. "Clone using the SSH path you get from the webpage (the one that starts with git@github.com:), not the one that starts with https://github.com." How do I find the git@github.com:?
    - Click on the green 'Code' button in GitHub and click on 'ssh'
      - found it. thank you

24. Can main branches be 'protected' in free GitHub accounts? It's not a special feature of pro accounts?
      - yes

25. Is this network graph (insights) being built automaticaly?
      - yes

26. What is the clone URL for ssh in the centralized repo? ( I don't find any "clone url" button)
    - maybe make the window wider?
    - Under "Code" (green button)
        - Thanks! green button! Yes!

27. It feels like we haven't really said anything new the last 20 min - like, "clone" copies the repository to your local machine, while "fork" makes a copy online. Is there anything else that I've missed?
    - Basically that, preparing for exercise.

28. I think I did the preperation exercises b then ut why can't I get it to show "unwach" I have "watch" but the "participating and mentions" selected as should (this was the default setting).
    - i had a similar issue. Turns out it was already the default setting. If you click "all activity" then it shows the option to unwatch. But watch and "participating and mentions" is what you want.
    - so do you think I'm good to go with the deafult?  -yes -Thanks so much!


29. Love the structure of the lecture today. Explaining the concepts with graphs before actually working on them is really helpful.(+3)
    - Thank you very much! :)

30. Will we talk about what happens if the branches are different when you make a push request? For example, let's say github has a branch named "coolFeature" and I clone the repository and change this branch to something else, and then make a push request.. Nevermind I don't know what I'm asking really :P
    - On Github, branches are always internally named: username:branch-name. So Github will always know which branch is which even if it looks like they have the same name. When making the pull request, Github will ask you to specify which branch you would like to merge into which other branch and here it will start showing branch names in the username:branch-name format.
    - Then if there are conflicting files/content in branches you'll have a change to resolve the conflicts and I think that will be part of the following exercise

31. I got a little lost yesterday with the basic console commands mixed in with the Git things. In the future workshop it may be beneficial to have an (optional) intro to basic usage of console / vi / ... for people how are more used to work in UIs.
    - We have one here, I plan on making it more clear/important in the future: https://scicomp.aalto.fi/scicomp/shell/
    - Great. Thanks!


32. I am confused about the ssh key. When we clone a project, I am asked about enter passphrase for key. Do I consider the ssh key that I created in my repository in the last two days?
    - It's going to be the passphrase that you used when you created the ssh keys.
        - Okay great. Because I do not have my notes, is it possible from github to check our ssh keys?
            - I don't think so, since it's a security feature for ssh keys.
        - You can create a new ssh-key and add that to github. and have the password somewhere (preferably in a password manager)
        - Ok thanks. I think I know what you mean. However, the speakers continue speaking and I am too slow to solve this. Is it possible to do the excerices later or after the session?

33. What makes templates different? do they contain some specific configuration?
    - It's bisacly a bit of config, when you "generate from a template" it doesn't by default send pull requests/config back to the original.  So the new one becomes a new upstream, basically it doesn't make it a "fork" in the Github sense.

34. What are these funny avatars (cubic shapes on white background) that a lot of people have on GitHub? 
    - It has some algorithm to make the cubic ones by default, if not changed.


35. I did not understand why would we create a template. Can't we just clone the repository?
    - That's what we used to do (make a fork).  But then, in the next steps, pull requests appear on the template, not on your copy - which isn't what we don't want.
    - If you clone the template-repo then you're gonna change the actual template (probably restricted tho by us)
    -sorry. still not clear. Creating a fork is equal to make a template?
    - This template is like a draft repo that you can use to create similar looking repos that have stuff ready for you. Teams at least should use the temlpate to create their own repositories (that have stuff ready for them) 
    - Forking is like making a copy of the repository with a link/connection back to the original repo (to suggest changes back to the original)
    -what is the command for forking? Do I use the commmand on git?
      - In GitHub web GUI there's a button for that but I think you don't need that at this point. We have that in a later exercise.
    -so if I understood correctly:
A clone is from github to the local machine. It creates a local copy from which I can push and pull changes.
    A fork is an a copy from github to another user github and these are still in communication or independent between each other?
    A template is when a user takes from another user github account their code as a template to use it for their scope. The two repositories become independent between each other.
    Is this correct?

36. Could you please let us know when then individual learners watching through stream should be listening again? How many minutes?
    - soon
    - Thanks so much for asking them about this for us!

37. when working on a shared server, how do i set up my git? can I run `git config --global user.name <Name>`? or is `global` an issue? is there an alternative?
    - `git config --global` set the settings for your user on the shared server.
    - `git config --system` set the settings on the system and will be active for all users.
    - `git config --local` set the settings for a repository
    - Is this a server where you all use the same user account?``
        - we each have individual logins (so individual users) to the server - is that what you mean?

38. Watch and Unwatch is confusing. When I select 'Participating and @Mentions' then I expected it to show 'Unwatch' and when I select 'All activity', I expected ti to show 'Watch' but it's opposite
    - Heh, yeah.  So, the button shows the *change* that would happen if you click it.  So the opposite of what the current state is!
        - hmm, ;)


39. Where does the merging to the master happen? Should I do it locally on my machine and then make a push request, or should I have my own branch 
     and push the whole thing to github, and then do the merging there?
    - In this case merging to master happens on Github - don't merge yourself.

40. I had no brkfst this morning. Could we do 15 min. break, pls? (-1)
  - There you go! Please have something to eat! 🌮
      - Thx a lot! Nonetheless, cantinen had no food ready any way :'(

41. I added the reporsitory with URL, not SSH and now I can't add with SSH. How to remove the reporsitory and try again?
    - You can delete the folder and do it again in a new folder.
    - Just physically delete the folder? Also on the exercise it literally says repository-url, but afterwards it says don't use the url...
      - where in the material is this? 
    - so the remote points to https and you want it to use "git@..." address?
      - if yes, then you can change the address with `git remote origin --set-url NEWURL`

42. I understood that changes to forks didn't affect the original repository, but apparently that's wrong?
    - Changes to forks don't affect the original repo, it's only when you do a pull request and it is merged, then it affects the original repo.
        - I thought the pull request was between  the fork and the local computer?
            - No, that's push (local to fork).
            - The Pull Request we are doing here (as individual learners) is from a feature branch to the main/master branch (within the same repo)?
            - Pull Requests can be done branch-to-branch within a single repo... or branch-to-branch between two repos (where one is forked from the other)?

43. For individual learners, we should git clone the repo, than we should create a new branch with our names or alias?
      - yes, I recommend a branch name like myname-thefeature. This makes it less likely that we collide with names and in bigger projects it can help to be able to find your branches

43. Can i as an individual learner already start the excercise myself? I have to leave soon.
      - yes. but the review part will come later (but can be also watched on video later)

44. In the website to get a certificate, it is specified that "The output of git log --all from the repositories that you have used during the course as a text file." is expected. My question is, do they refer to the all the practical exercises solved during the first 3 days? what does the "git log --all" refer in this case?

45. What is a good way to review this material later, if you are not able to follow all the way through today? Since you won't be able to participate in the collaborative exercises.
    - You can actually do this all by yourself: your same person can be the maintainer + the one making the pull requests.  (or find a partner and do it together)

46. Is there any way to merge from command line ?? or we are forced to do it from browser ??
    - git merge: can be from comman line (we did it yestreday), but that's probably not the question...
    - GitHub pull requset merge: there is a `gh` command line thing that can do it (I think).  Or... checkout master/main, do a command line merge (above), push, and Github detects it was just merged.

47. so if I understood correctly:
    - A clone is from github to the local machine. It creates a local copy from which I can push and pull changes.
       - Yes
    - A fork is an a copy from github to another user github and these are still in communication or independent between each other?
       - Yes, it is copy inside GitHub. The fork remembers the repository it was forked from, making it easier to suggest changes to the original repository. You can also automatically pull changes from the original, as long as there are no conflicts.
    - A template is when a user takes from another user github account their code as a template to use it for their scope. The two repositories become independent between each other.
       - Yes
    - Is this correct?

49. Lol, I misunderstood, so I did the assignment and thought it was break now haha. Just waiting for other to push now :) 

50. Can I do the excercice afterwards? I forgot my ssh key and I do not have time to fix this.
    - Yes.  It's possible to do this all yourself (you are maintainer + contributor), but you can also find a friend and do it.

51. I try to push a separate branch with `git push --set-upstream origin some-test` and getting this error: 
    fatal: refs/remotes/origin/HEAD cannot be resolved to branch.
    Any idea?
    - Hm... did you clone this repo? Yes
    - So the problem is it doesn't know which is the default branch on the other side.  You can tell it which branch to push to.  But I'm not quite sure how it got here and thus what the solution is.
    - I think you can do: `git push --set-upstream origin some-test:THE_NAME_OF_BRANCH_ON_REMOTE` - it will 

52. I got an error when git branch: 
        fatal: not a git repository (or any parent up to mount point             Stopping at filesystem boundary (GIT_DISCOVERY_ACROSS_FILESYSTEM         not set).
        Sorry I was in the wrong folder :/

53. We experimented with deleting branches. One person deleted their branch, also on remote (it is gone on github). When another person did git pull, git branch -a still shows that remote branch though. Why? Trying to pull only the deleted branch gives an error that it doesn't exist (as expected).
    - I think it might not remove deleted branches on a remote... (`git fetch --prune`).
        - `git fetch --prune` removed them! thanks. 



### Break until xx:10
:::info
Then we will set you up for the exercise (30 min then)
The state after the break should be:
* Individual learners on the stream: request access (see email last night) and you will start cloning after the break
* People with their own teams: One person per team (maintainer) start setting up exercise repositories and start sharing usernames.  We did demo, you will have time to do it after the break.
:::


### Exercise until xx:45
:::info

https://coderefinery.github.io/git-collaborative/centralized/#exercise-preparation
- steps A-H (inclusive)
- Do not do part 2 - we do that together.
- Try to get everything done, because part 2 continues from this.  (but in the next hour we do something else completely new)
- If you have time left, look at optional exercises "Centralized-3" and "Cenralized-4"
- **don't merge branches yet** - we do that together next.
:::

54. For individual learners streaming at the moment, should we use the "centralized-workflow-exercise-recorded" or the "centralized-workflow-exercise" repository
    - depends if you want to be in a recorded session or not. (-recorded will be livestreamed + end up in Youtube video)
    - ok thanks!
    - bear in mind: it'll be a pretty boring livestream for everyone if no-one takes the leap and works on the recorded repo ;)

55. In step F, does git 'know' that 'origin' refers to the master branch on GitHub? 
     - origin refers to the repository
     - but the fact that it anticipates that you want to merge to master comes from master being the default branch

56. What is ment by: "Clone using the SSH path you get from the webpage (the one that starts with git@github.com:), not the one that starts with https://github.com. Otherwise, you won’t be able to push later."?
    - in Github within the repository click on green button Code. It shows the SSH clone path. You can copy it from there. 
    - This is where I find it badly described that the exercise says url, but then not to use the url. (+1)
    - yeah now I have already cloned it with https and I don't know how to undo it. I guess just try it again with ssh and overwrite it?
        -  delete the repository and try again using ssh. `rm -r <name repository>`
        -  Plz update that on the lesson material to avoid confusion (+2)
        -  Or you could do: `git remote set-url origin <new url>`
         

57. HedgeDoc is starting to do some funny things - when I click on a line it starts editing a line or so above where I put my cursor. Works better in half-half mode. 
    - Maybe try refreshing the page, we are trying to keep it short to solve this but can still happen sometimes... 
    - It seems happier now... 


58. Where can I find the SSH path to the repository (for cloning)?
     - see answer 56

59. I pulled my branch to the main branch and it says on git hub "Review required" and "merging is blocked". what should i do? what exactly it means?
    - This is probably where you want to be - we merge next.


60. I have done the first clone command, but I get message like: 
```
ssh: connect to host github.com port 22: Connection timed out
fatal: Could not read from remote repository.
```
  - Please make sure you have the correct access rights and the repository exists.'
    - I thought I got the accesses, I got the confirming email etc but did I miss something?
     - It seems that ssh isn't working.  does `ssh git@github.com` work and show your username?
         -it shows: ssh: connect to host github.com port 22: Connection timed out
     - Something is wrong with the network on that computer (probably) ssh connections don't go through/are being blocked/etc., since it works for the rest of us.  Probably not much time to fix this now.  Could it be a firewall or something?
         - I tried to restart computer, didn't work. I tried with the HTTPS and not SSH, you instruct not to do this way but can I proceed with it? It seems to have worked.
         - never mind, suddenly the SSH worked now!

61. I have sent the pull request from the github web interface. Now I am given the option of "merge pull request". Is this something I should do to complete the pull request? What does it mean?
    - Wait and we do that next.

62. This doc is like watching half a dozen ChatGPT sessions running in parallel (just less glib) (+XD)
    - Heh.
    - The fact that this is being compared to ChatGPT tells that they are becoming mainstream 🤓
    - I'm guessing that ChatGPT has been trained in part on the corpus of code in GitHub... I wonder if it respected less-permissive licenses?

63. I can't find the ``<repository-url>``... Please help, where to search for it?..
    - see answer 56

64. I rename my branch and now it appears with two names (origin/souza, allantsouza-r). Is there a way to fix that?
    - So the `origin/` one is the view of what was last pushed.  `git push --delete origin NAME` would delete the old name.
        - now I loos the origin, git graph shows this: (allantsouza-r) 
        - there are no origin branches so it doesn't show.  Try pushing again.
        - I did git pull, git push and remains the same. My initial mistake was to rename the branch before checkout.I don't know if it makes any difference not having the origin there before my branch. But I am the only one in this situation, when I write `git graph`. 
        - I deleted this falty branch and created a new one.

65. In the Optional exercise 3 .... after creating a issue the branch and the pull request have to be made from the command line ? I mean... step 1 in the browser and steps 2 to 5 locally ?
    - yes correct. sometimes I forget to reference the issue number in the command line and you can then still do that in the pull request title or description later, with the same effect.


66. When I type git branch, I don't see all the available branches, even if I did git fetch before. How can I list all available branches?
    - `git branch` will only show you the branches defined locally. References like 'origin/master' can be seen with `git graph` if you have defined that alias.
    - `git branch -r` will show also the remote branches
        - but if id did "fetch", the remote branches should be in my local repo, right?
        - yes, but the remote branches are more like tags and not branches.
        - but git branch doesn't list them


67. Could you please go over the meansing of the -u flag in the stream? Thanks.
    - From today. There is an explanation box ("Meaning of -u") on the instructions but I don't fully understand it.


68. In bitbucket there is a button for "request changes". I don't see that in gihub, what am I missing?
    - Is it on a single file view?
        - no, for a pull request for a branch, involving potentially many files, there should be an option to ask the submitter to change things
    - In github web interface you can: navigate to a file, edit, and it will help you open a pull request
    - Push a branch and then web interface will let you make a pull request out of that branch.


69. To keep the history linear, shouldn't one do a git pull --rebase, rather than just "git pull"?
    - If you want to keep it linear, yes.  But maybe you want to preserve full history if you want to know how it was made individually.

70. Are we back online? I cannot hear anybody
    - Not yet (time updated, was wrong)
    - online shortly


71. Push gave me this error: ERROR: Permission to cr-workshop-exercises/centralized-workflow-exercise-recorded.git denied to my name
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
    - Did you request the access / accept the invite?
    I followed the link. But did not understand what to do.
    - you made the "request access", and got an email.  clicking link, was there some button "accept invite" ?
    No. That was my problem and confusion. Now I see that I answered the wrong email. Found the one with the button!
    
72. If I fork a repository and the original repository from where i forked from gets deleted on git hub, what happends to my forked repository?
    - https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/what-happens-to-forks-when-a-repository-is-deleted-or-changes-visibility#deleting-a-private-repository

73. I used the SSH key for the exercise, but when i wanted to push i needed to write the passphrase every time - is that normal? (it says in the learning material that "if you get a password request...." it should be because i used http - which i didn't). On windows.
    - There are ways to make it remember it - no time to discuss now but you can make it work later.  What operating system do you use, win/mac/linux?
        - Alright - I use windows
        - https://scicomp.aalto.fi/scicomp/ssh/#login-with-ssh-key - one example but search "ssh agent windows" and maybe you can find better ones
    - I solve this by not having a passphrase at all for my key... Is that bad practice?
        - Depends on security of your computer and how important the stuff you connect to is.  Most would recommend ssh-agent instead, but there are reasons no password is better.



:::info
**How was the exercise?**
* it worked: oooooooooooooooooooooo
* didn't work: 
* needed more time:
* didn't try:
* too much time: oooooo
* other: good amount of time o
- personally I had many problems and now I'm just starting with the actual exercise, so late...
  - Don't worry! You can also follow only and do it a bit after
:::

74. How does GitLab compare to GitHub wrt these project management / collaboration features? E.g. little things like 'self-assigning' issues etc. Pros and cons?
    - Pretty similar, bring this up again for the final discussion, it would be a good topic.
    - Will do, thanks :)
    - Personal opinion: Some things are (due to popularity) more easily available on github. 

75. Can you show the pushing part?
    - It was `git push origin BRANCH-NAME` I think (?)
      - Yes: push to the origin to the specified branch and specify the branch name

76. We make a branch, add changes, commit it, and did the pull request to the master branch. Then we make a sub branch and add another change, add, commit and then again the pull request with revision, and when it finished, it look like the sub branch is only connected to master via the branch. Why does it look like this [link](https://github.com/IVinterbladh/collaboration_test/network)?
    - This is a very good qusetion and point.  This is the correct situation, it's done as needed basically.  That sub branch wasn't modified by the other merge, so stays looking like it is.  Git handles this just fine!

77. Why were some issues raised and for some changes it was just a pull request?
    - Was an optional exercise, it seems.  It's a demo of extra stuff, it depends on if people want advance discussion before doing a lot of work.
        - Okay, thank you!

78. Is it possible to use the issue functionality to give suggestions on the code? I mean have a pointer to some file, line, etc. 
    - we will actually demonstrate that in the next exercise!
    - Awwesome!
    - I recently learned that you can 'point' to multiple lines at one time (cross-referencing in an Issue) - super cool :)

79. i had an issue with pushing. i have cloned using ssh. "ERROR: Permission to cr-workshop-exercises/centralized-workflow-exercise.git denied to xxx. fatal: Could not read from remote repository. Please make sure you have the correct access rights and the repository exists."

    - If on livestream: did you rquest access via the issue and then accept the invite when it was accepted?
        -  i think so. let me double check...
        -  The invite has to be accepted (new email from github, accept in link)
        -  i hadnt accepted! :s but now done and it works! thanks :) 


80. On Radovan's page the terminal can't be seen fully. Could you please make it fit in screen frames?
    - I'll raise it.
    - thanks. saw it now. where was it cut off?
        - on both sides (left and right)
            - thanks! sorry. I will adjust next time

81. What is the difference between git merge and a pull request? Is it because of the centralized setting?
    - The 'pull request' is a request for a change. The reviewer then get the possiblity to merge this change and this is 'merge pull request'
        - So the reviewer gets to do the conflict resolution, right?
            - Well, yes, but it could also be a reviewer asking the requester to update their branch so that it doesn't have conflicts (which actually happens pretty often).

82. How to reopen a closed pull request ?
    - maybe a maintainer needs to do it.
    - If it's already merged, probably can't be re-opened since there is nothing new to merge.
        - its not merged yet
        - Then I think a maintainer needs to open, Github doesn't allow anyone else to re-open (this is a Github choice, Gitlab was different).  This is just from my memory...

83. My branch has comflicts in git hub and I cannot merge. What should I do?
    - For purposes of this exercise, probably wait/do nothing/try again with new change.
    - In a real situation, you can "resolve conflicts" via the web interface, or modify the change on your own branch to resolve on your own computer.
-In the web interface it does not shown any "resolve conflict".

84. Question: I hope it's ok that I attach a screenshot here to explain?
    - added as a link yes, even though explanations are more convenient, as they can easily be archived and are not lost.
    - Ok here is the [link](https://github.com/dinhe878/centralized-workflow-exercise-cfb/network). I use the template and created a team, I noticed that there is a "experiment" branch ahead of the commit chain. I can't see how made the change nor can I make a pull request. I guess it's from the original template repo (but somehow I didn't copy it when making a template)?
        - the template repository has two branches and you probably clicked "include all branches" (which is not a problem). the generating step "flattened" both and now they have unrelated histories although on the template repo they are related.
            - Right! But the generated template will actually sync all the changes from the original template?
                  - sorry what do you mean by "sync"?
                  - Actually now I forgot if I saw the "experiment" branch when I generated the template. I just saw there was a commit and I can make a pull request to that commit (which is the experiment branch). But when I went in and did the comparison, it didn't give me options to proceed with "actual" pull request.

85. How to make the review mandatory for all PRs?
    - I think it was touched on when talking about branch protection rules... there was an option to make PRs mandatory (and to say how many PR reviews were required)

86. If I do "git log --all" I get a commit log that contains everyone's commits for some of the branches, but not all. I can't see why those branches and not others.
    - do you get logs for all locally available branches? Or which branches do you compare with git log? It might be that you need to `git fetch` before all logs are available.
        - Yep, I think that's what I needed to do.

87. When I try to see the dependency graph in github I am getting this message (why?):
    `No manifest files found To view your dependency graph, your repository must define dependencies in one of the supported manifest file types, like package.json or Gemfile.`
    - dependencies are code type specific (e.g. whats mentioned here are javascript depenency management files). Github does read some of those and interprets them so that you can create a dependency graph fbut it is not strictly speaking git that does it, so as long as you don't have a respective file in your repo this github feature wont work. This is a nice example of a distinction between the github platform (which offers this feature) and git as a versioning system. 
    - I think I figured it out, thank you! I was using the wrong tab -.-

88. Shall we remove our branches after merging?
    - It's good practice.  You can always see where they used to be from the history.


### Break until xx:15
:::info
Then we will do "forking workflow": explanation + then quickly go to 30-minute exercise.
:::


89. There is a PR to add another 'quote' file (for John Muir)... if I wanted to suggest that it get merged with the existing 'quote' file (for Dune) would it make sense to: 
    - merge the John Muir PR into main, then create a new branch that combines the two files together into a single 'generic' quotes file?
    - ... can't think of how the alternative would work... I guess it does make sense to have the history contain the two separate files, with a subsequent commit showing them merged...?
    - maybe to keep things cleaner, keep working on the branch that introduces the John Muir quotes... update it from main (pull), then combine the two quote files, then (re)do the pull request
        - the history in this case would still include two separate files (from the initial state of the 'John Muir' branch)

90. How do i know if my branch has been merged?
    - `git fetch` and `git graph` can let you know visually.
    - `git branch --merged` shows what has been merged, but I'd usually look at graph unless it needs to be scripte.

91. So i just ran "git status" (on master branch) and it told me that i'm up to date with origin/master. When I pulled from origin/master, however, it downloaded a few dozen files. How can it tell me I'm up to date if I'm missing all these files?
    - That's weird, hm... wait, `git status` doesn't access the network, so doesn't know current state.  If you `git fetch` first then it would know what the latest changes are.  `git pull` does fetch first.
    - Because it's latest information about the remote was that you are up to date. (see above, `git fetch` to update the remote information)
        - gotchyall. Thanks.

92. If our feature branch is still there after the PR has been merged, should we delete it locally (with `git branch -d <branch-name`) and **also** on the remote repo (with `git push origin -d <branch-name`)?
    - Yes, probably good practice (unless you need it).
    - Probably good to double check that it has been merged first (with `git branch --merged`), but I guess that git will complain if you try to delete an unmerged local branch (as long as we use the `-d` flag, not the `-D` 'force' flag)


93. Is someone workin on merging the branches of the repository 'centralized-workflow-excercise'?
    - Hm, I guess no one did.
        - thanks for mentioning and working on it!

94. What is the difference between pull and fetch?
    - fetch is see what is going on in the remote.  pull is fetch+merge

95. How do we update our local repository with the one on github? so that we would see the stuff (done by others) that happened after we cloned it to our local computer and started working on it?
    - It is git pull
      - https://www.freecodecamp.org/news/git-fetch-vs-pull/

96. I think he is not sharing screen.. We cannot see the screen of the speaker. (+9)
    - You are still showing the notepad.
    - sorry, I was reviewing the pull requests and not focusing!
    - Thanks for pointing out! 

97. I see in some PRs that they are open (not yet merged), but show that they have been 'approved' by someone else... how/why do you approve a PR without simultaneously merging it?
    - Files changed -> Review changes -> choose "approve" -> Submit review.
    - :thumbsup:

98. I have problem when I push my txt file (folk exercise)


### Distributed version control and forking workflow
https://coderefinery.github.io/git-collaborative/distributed/#distributed-version-control-and-forking-workflow

99. Why is there a blue line from red square anf blue square, since the interaction with the red is only via green?
    - You are right, maybe we could go via the forks.  But sometimes one does pull from the central repo.
    - It might be good to add more colour-/style-coding for the lines, and explain them in the figure legend?

100. When I fork it usually gets miserably out of sync very soon. I.e. I have my own stuff but it is difficult to see how much it conflicts with new developements in the  central repository. How do you handle that (better than me)?
    - You can also add the central repo as a remote `git add remote upstream URL`.  Then `git fetch upstream` and see what is there, and build branches based on those.  I think we will talk about this later, if not raise it at the final discussion since it's a very important question.


### Exercise until xx:58, then break until xx:08
:::info
https://coderefinery.github.io/git-collaborative/distributed/#exercise-preparation
- Try to do all of part 1 now.
- Part 2 we do together afterwards.

:::

101. Should we uncheck the "Copy the `master`  branch only" when we fork?
     - here it does not matter (here there is only one brach when we start). but yes.

102. It feels like we skipped the code along session.
     - yes we decided to have this as part of exercise and then together to focus on the github part and the code review

103. Do I understand it correctly that in the command `git push origin -u yourname-somefeature` the `yourname-somefeature` instruction is basically the name of a branch created in a remote repo? And that for convenience, we name it the same as a repo branch on our local machine to avoid mess?
       - the command means: publish my local branch named "yourname-somefeature" to origin, and keep the name and connect the two from now on (the -u part). it is anyway a good idea to have the same name locally and remotely to avoid confusion.
           - alright, then one thing isn't clear : does it matter on what branch I'm _sitting_ locally when do `git push`, `master/main` or `yourname-somefeature`?
                - it does not. you don't have to be on the branch that you push. it only matters for the pull part which modifies the current local branch.
                    - alright, clear, thnx!

104. Not sure where to put this question, it's related to "Distributed version control and forking workflow". You mentioned forking vs. cloning, but what about forking vs. branching? When is each option better than the other?
      - this is a good place
      - Personally, I prefer having code on my repo (i.e. I fork). The only exceptions are Group internal repositories, where I'm mostly developing myself, or if it's really small changes to a repo I'm not really using otherwise and have direct access to (again group-repositories normally)
      - when having many branches in one repo you don't have to sync repos but advantage of forking can be that the "central repo" looks tidier
        - Thanks for the great answers!
        - I think it's also an advantage that your own forked repo looks tidier - it's nice not to see a forest of additional branches when you look at `git branch --remote` (I'm guessing that you'd only see branches that had been accepted as PRs from other forks, and not deleted)

105. I think I still didn't get the access working to the non-recording repository on github, I'm working alone not in a team. My user name is included in https://hackmd.io/@eglerean/CR2023
     - I think you have a different one, ask there and if not have one of those staff message [name=rkdarst] with your usranme - I'm not sure which to add.
         - I don't understand this sentense, what different one? Ask where? What staff message?
         - Are you part of the in-person Otaniemi room?
             
         - Oh, ok.  that document is for there.  Finding the stuff for us... https://coderefinery.github.io/2023-03-21-workshop/communication/#2023-03-22-summary-day-2-and-day-3-preparation -> "If you would like to participate as individual learner actively in the collaborative exercises, please request access by opening an issue at https://github.com/cr-workshop-exercises/access-requests/issues/new/choose (There click "Get started" -> "Submit new issue")" request access there and I will give access.
        - By now we are in the forking workflow and you don't need any more access.  You can work without permission, so I would proceed that way.
            - okay, thanks! I tried to do that before already at 9am, and I thought I had everything set up but still I keep getting the message 
              ```
              Please make sure you have the correct access rights
              and the repository exists.
              ```
    
        - I would check this exercise later, but I believe the same access problem would still hold me back so I couldn't do it later. That's why I try to ask help now...

`          

106. I am not sure "Open an “issue” as a change proposal". Do I need to go to my forked version or to the original? Why would I need this step?
      - in the original one. the forked one typically does not have a place to open issues and it is typical to track issues and proposals in the central one so that everybody can see them. one central place to track problems and discussions.

107. git graph doesn not produce anything even after the config
     - Does it show an error or nothing?

108. I pushed my taco recipe to my fork; should I first merge it into the main branch in my fork, or should I first synchronize my fork with the central repo?
     - I would first synchronize your main branch with the upstream (centralized) main branch OR directly create a PR to the upstream (centralized) main branch from your branch. If there are a lot of conflicts between your branch and the centralized main, I would first synchronize because otherwise it might be quite messy for maintainers to try to merge this, and essentially it might just be rejected for that reason.
         - My main branch = my local main branch, or my fork's main branch?
            - Normally your main branch should be in sync with your forks main branch. Or if not they should be synchronized via push/pull/merge.
        - I'm confused, all the main branches are the same since I haven't merged anything yet. The question is, should I first merge my changes with my own main branch, or should I first synchronize with the central repo?
            - What I would do: I would pull the centralized main and update my personal main with that. Then I would check, whether a merge of my branch into my (no synchronized) main has any conflicts. If not, I would open a PR directly from my branch to the centralized main. 
            - If I use 'git pull', will it pull from the centralized repo or the fork? I think the fork right?
               - It normally pulls from whichever repository you cloned. to get the centralized you would need to add it as an additional remote. and then pull from that remote.
            - But we haven't done that. I'm on step D and E. We only cloned the fork.
                - Ok, sorry. For this exeercise, you just push to your fork and open a PR to the centralized repo (and you don't care about conflict resolution previous to the PR).

109. I do not understand, why when looking at "Network graph" in my own forked repository I still see all the branches created by other users? 
     - Oh, I see. These are the branches created before I cloned, I guess?
         - Hm. To me it looks like all forks and their branch(es).

110. Why do I get these errors when trying to push my changes to origin? 
`remote: error: GH006: Protected branch update failed for refs/heads/master. remote: error: At least 1 approving review is required by reviewers with write access.`
    - are you pushing to your fork? or to the central repository?
    - The central repo.
       - then this has to fail since you don't have write permissions to the central repo. you need to push to the fork   
 
111. Where do we entrer the issue? in the forked rep? i see the tab on the page header but that takes me to previously raised issues
     - In the first repo you forked from.
         - tack :) 

112. How can we verify where "origin" points to?
    - `git remote -v`
    - `git remote --verbose`

113. Depite cloning with SSH url, I still get a passcode request every time I push. Is there any way to avoide it?
     - Yes, but I would recommend talking with someone after the course and look together to see what's going on.
         - Ok. thanks!
     - I assume you have created your ssh key with a pass phrase. You might need to add that key to an ssh agent so that it doesn't request the passphrase for every use of the ssh-key.
        - Yes, it is right, I created it with the pass phrase. I assumed there was no other way. How can I add it to the agent?
            - You can create an ssh key without a pass phrase by just hitting 'Enter' twice... but I'm guessing this is not wise?
                - It essentially means: If your computer gets hacked the attacker directly has access to all places where you used that ssh key.
                    - :scream:
        - This is the correct way. Then just the extra step with the agent. Found [GitHub instructions](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#adding-your-ssh-key-to-the-ssh-agent)
            - Thanks!
                - Alternative instructions: https://scicomp.aalto.fi/scicomp/ssh/#login-with-ssh-key
            - If we have a non-passphrase-protected ssh key already, is the sensible thing to delete it and create a new one with a passphrase (updating GitHub with the new one?)
                - It is the safer option, yes. 
                - And losing the passphrase isn't a big deal, as long as we can still log in to GitHub (and create a new one)?
                    - yes (:thumbsup:)
114. At the end of the tutorial there is a Discussion box saying "(remember: pull requests are from branch to branch, not from commit to branch).". What does it meand from commit to branch?
     - Commit is after you add all the necessary files, they are in the staging area, but this is still on your local machine. You then push those to your repo where you can create a pull request. This means that you are pulling the changes from a branch to another branch in the main repo.
         - what would be the alternative (from commit to branch)?
             - Commit to branch would be a push request. Branch to branch would be a pull request.
                 - Do you mean pushing to the master?
                     - Creating a copy of original repo both are remote = fork
                     - Creating a copy of remote repo on local = clone
                     - Make changes to local repo, add and commit = changes in staging area
                     - Moving those changes to remote (to copy of original i.e. forked repo) = push
                     - Updating the original repo with changes from the forked remote repo = pull  
                         - ok thank you very much!
                         - You're welcome :)

115. Is it a good idea to `git clone` fork into the local repo with the original project or is better to have it outside?
     - The idea is to have one local repository, but with pointers to the central repository (upstream) and to your forked repository (downstream).
     - You define upstream and downstream with the following commands:
     - `git remote add upstream https://github.com/project/project.git`
     - `git remote add downstream https://github.com/userX/project.git`
         - Thanks, but I don't think I have enough background to understand your answer. I think I meant smth simpler, related to a good/bad practice of working with project forks

116. I did a pull request but my branch hasn't merged with the (centralized) master branch, and now it seems I cannot do a pull request any longer. How do I get my branch to merge?
     - If your pull request is still open you cannot open a new one. Also as a note, your pull request will update whenever your branch updates, so if you push more changes to your branch, while the PR isn't merged yet it will automatically be updated. 
         - Okay but how do I get it to merge? That's all I want to know


117. What if the test.py is failed? Can the change still be pushed? Or it requires changes? If changes are needed, how to make that correctly?
     - You can still push, Github will display a warning and it shouldn't be merged.  You can then keep working on it and try to get it passing.
     - Thank you for the answer. I tried to resolve by myself: I closed a push, created a new commit and then created a new push request, but now can't find it anywhere...
     - does `git graph` provide any hints?
     - It seems to be resolved now... I went to my own repository where there was uninitialized pull request. So I pressed the button to request pulling and it should be there now. Checking... Yes, it is on the main issue page!




:::info
### Break until xx:08

**How was the exercise?**
* it worked: ooooooh (+6)
* didn't work: o (+1)
* needed more time:
* didn't try: oo
* too much time: 
* worked but need to go over it more to really understand it (+1)
* I made a mistake, did everything including a pull request but with a file not having 'taco' in the md and tried again, but failed. Can't do a pull request now 
* Problem with ssh key. So, I did not try the exercice yet.
::: 




118. This is difficult to understand "(optional) Distributed-2: Send a conflicting pull request. If you complete parts A-E much earlier than others, try to open another pull request where you anticipate a conflict with your first pull request." How do I create a conflict?
     - open a second pull request which changes the file of another pull request (your earlier one or somebody else's) in the same file portion in a different name. alternatively you can send two pull requests which add a file with same filename but different content. merging the first PR will work but then merging the second will conflict.
     - Do I need to create a txt file in my local repository before? Sorry I am a bit confused. Also if I click on pull new request, it doesn't allow me to do that.
         - yes, again new branch, add txt file, push branch, open new pull request.
         -does this need to have the same txt file as previously or changed?

119. How do some issues show an icon with 'linked pull request'? I've tried adding `closes #<issue number>` and `link #<issue number>` to the related PR, but the icon is not showing up next to that issue...
      - if you like can you link to the PR? but no pressure to
      - closes #N should work. the other is maybe not recognized by github
      - it seems like you need to have that closes # in Description
          - yes: this was it. I had `closes #<issue>` in the PR title, but not the Description; I went back and edited the Description (= 1st comment in PR conversation), and that added the PR link to the issue
          - this is pretty important, I think - best way of highlighting where work is being done on an issue (a bit annoying that making the link is so arcane!)

120. I have a problem when I push my txt (fork exercise). This is the error error: failed to push some refs to 'github.com:cr-workshop-exercises/forking-workflow-exercise.git'
     - It seems like you cloned the central repo, not the fork... looking.
     - https://coderefinery.github.io/git-collaborative/distributed/#step-d-push-your-changes-to-the-fork "if you get a password request for..." - that box, that isn't teh problem but you can set-url to the one of your fork, then you can push.
     
     Thanks, now it works

121. Why isn't my branch merging? I have done a pull request.
     - The merging will be done by the instructors as they are the owners of the central repository. The central repository is write protected.
     - And they might need some time to get through all PRs
         - Everything has been accepted for several minutes except mine. I doubt that's the problem.

122. Did you explain how to integrate the test in github? Or will you explain that later?
     - we will only hint on what is happening but next week we have a full session on that topic

### Forking Part 2: merging
https://coderefinery.github.io/git-collaborative/distributed/#exercise-part-2-code-review-and-merging-changes

123. I am not able to push the branch to my fork origin with `git push origin <my branch name>`. It did this and I went to get the pull request, but what then? The files are not in the master branch? (+1)
     - You cannot push? Or you cannot create a pull request?
     - I did get the pull request in the other branch, but not in the master branch
     - What do you mean by "get the pull request"?
     -    I found it online in github and then clicked it there, "create pull request". But then what? It says in github that it is 1 commit ahead of the cr-workshop-exercises:master.
     - OK, so if I understand correctly, you created the pull request but it was not merged yet. I think the merging will be done together.
     - How to do this? The files are not visible in the master and there are no more pull requests visible in github?
     - If you made a pull request to a different repository (from a fork), then you don't see the changes in your own master branch. They will only appear in the "main" repository. The pull request is also only visible on the "main" repository.
         - Can you see your pull request or your changes in the original repository? (see the question directly below)
         - YES! Thank you. This was very confusing, maybe a good idea to clarify in the instructions that it only goes straight to the centralized repisotory. Thank you!
         - noted
     - to follow from above^^ was the issue that the recipe was in your own branch? not in the master branch?
     - I added an note here: https://github.com/coderefinery/git-collaborative/issues/251. It's a quick note about the issue as I understood it, so feel free to comment on it.

124. How can I find my own pull request? If it exists..
     - Go to the upstream and "pull requests" tab: https://github.com/cr-workshop-exercises/forking-workflow-exercise/pulls (or the -recorded) one.


125. Why isn't my branch merging? I have done a pull request. All other pull requests have been accepted for 30 min.
     - In forking or centralized?  Forking we need to do it.  Maybe we forgot about it if it's centralized, sorry about that...
        - I'm in a team so it's not you. 
     - Unfornutately this happens a lot with busy peolpe, so it  can be OK to add a comment saynig "hey, I think it's ready..." or talk to them directly.

98. (COPY from earlier) I have problem when I push my txt file (folk exercise)
    - Sorry it seems we missed this one. Also we would need more details to provide meaningful answers 😇

126. Why isn't my branch merging? I have done a pull request. All other pull requests in my team have been accepted for 30 min.
     - If it's a team repo, ask the maintainer... they may have forgotten.  If it's us, then we probably forgot and will get to it.
        - Ok so the only thing that may be a problem here is that the maintainer hasn't approved it? There is nothing else that may be wrong?

127. OPEN FIRE FTW!!!!!!!
     - An extreme example catches attention 😇


128. Why does cross-referencing issues using “#N” not auto-close an issue (it works centralized, but not distributed)
     - Hm... is it made in the same repository?
     - Maybe this happens only after merge?
     - Related to 119?

129. im struggling with the pull request still :disappointed: i git add and committed my recipe so it is in my master branch. going to pull req, "there isnt anything to compare". not sure what it is im doing wrong. (+1)
     - Did you push to the online repository? `git push origin master`
     - If you did, it can happend that GitHub does not recognize the change. In that case you can click "pull requests" on the line below the repository name, click "create new" and select the branches. (+1)
        - i did push, that's via git push origin... right?
        - That should work. In might fail and print an error message that's not very visible. To check that, try pushing again.
            - i've pushed again. message is "Branch 'theo-better_tacos' set up to track remote branch 'theo-better_tacos' from 'origin'. Everything up-to-date"
            - OK, you can also check the branch in your repository (although the changes really should be there). In your repository page, there is a branch selector above the file view.
            - Once you know that the files are there, try creating the pull request manually on the "pull requests" page in your repository
                - it's not in the fileview 🤔
            - Hmm.. Maybe you are looking at a different repository. Can you run `git remote -v` and compare the url of `origin` to the url in your browser.
                - it's same url. v confusing 
            - OK. What is the exact command you ran to push? `git push origin master`?
            - yes, i tried that and git push origin -u master
            - And it tells you the remote is up to date? Can you check `git status` to see if the changes were committed.
            - i just ran it again and now it has updated/pushed! i can see it on GH. it is the same as a ran before tho.  
            - OK, weird. Maybe the online view was behind?
            -  could have been 🤷 but thanks a lot for your help!! :D 
            - That's a good thing for us to note. There were a lot of pushes and pull requests, maybe it did take a while to update.

130. So in general: centralized workflow for 1 user and forking workflow for several collaborators?
     - Centralized workflow works for many collaborators and it is common among teams working on a same project.
     - Forking is useful especially when you don't have write access to the original repo
     - Or when there's so many collaborators and branches that collaboration gets messy. Then people can start to do their work in their forks

131. It sometimes felt difficult to keep my local repo up to date when a lot of people are pushing changes at the same time. Is there a way to keep this cleaner? i.e. get less errors for trying to push changes to an outdated version of the repo?
     - My workflow (and a common suggestion) is to always run git pull directly before git push.
     - Usually there are not as many changes as in the exercise today.

132. I don't completetly understand how the pushing works when you don't have writing access (e.g. when working on a centralized manner). You push the changes to the branch you are working with? and then you get a pop up message on github to create a pull request since you cannot directly push the changes to the main branch in the remote repo.
     - You have writing access to your own fork. It's a copy you own. But then you need to get the changes to the original repository, so you create a pull request. The owners of the original repository have write access, so they can look at your pull request and accept the changes.

133. .
134. .


## Feedback, day 3

Today was:
- too fast:
- too slow: oo
- right speed: ooooooooooo
- too advanced: o
- too basic:
- right level:oooooooooooo
- needed more exercise time:ooo
- needed less exercise time:o
- I will use what I learned today: oooooooooooooo
- I would recommend today to others: ooooooooooooooo
- I would not recommend today to others
- too slow sometimes, too fast other times: oo
- pace was ok but it felt chaotic, would have been easier to follow in smaller groups
- **Thank you** for all you are doing!! :trophy: +2
- :cat2:: +15
- 
    - the real superstar :heart: :paw_prints:
    - all hail the cutest cat! :heart_eyes_cat:
    - I wonder what changes the cat would've made to the main repo (lol)
        - any changes would have been pulled immediately by CI (*Cat Integration*) lol
        - more treats for cat
            - A mouse or two? Don't think the collaborators would've merged that though
            - hand-prepared gourmet raw food diet?
            - little pieces of paper (no, don't eat that)
                - it enjoys eating the paper on my desk
        - issue (feature request?): we should make Cat official CodeRefinery mascot +1
- I could not get started because of access/SHH problem, I had to be at office today at my work and couldn't attend in person. On chat my problem was not disclosed even though I asked 3 times. Today was disaster: +1
    - Did you ask on Twitch chat or collaborative document?
        - collaborative document
            - Apologies for not getting to your question. We do try to get to everyone, but sometimes we have a lot going on. We will try to be better for the next session.

One good thing about today:
- Forking, cloning, push and pull don't feel like black magic anymore (+5)
- hands-on work (+3)
- learning from mistakes :smile: undestood why it is not necessarily a good idea to PR from the master branch of the fork
- Comments on the commits, nice feature for going back and forth on code review. 
- Very nice maintaining of a large number of participant! Thank you for a nice experience! (+5)
- I understand better how to use forking correctly and the issues # (+1)

One thing to improve for next time:
- please see that people who are working alone online can also join and get started. Maybe even have one hour more in the morning for the people joining alone (without a study group) + online (can't attend in-person at the university for example for work reasons), I had a lot problem with access/SSH and it was not disclosed at chat
- having more (smaller) repos for exercises might have been easier to follow
- sometimes it was difficult to understand what the instructors were saying because of pronounciation or too quiet sound.
- would like to have 30min break for lunch. (+1)
- Would be lovely if the course would also have a final session where those who want can come and ask questions about how to incorporate these skills in their personal work or then some examples on things that most people might like to use git for. Eg. How to work with git bash and LaTEX files when creating the phd thesis summary or then how to work on R-scripts that are on the server/cloud and are run there. Do these git commands work there too if you want version control for them? I'm still a bit confused about how I would use what I've learned so far in my own work/in the real life.

Any other feedback?
- Very confused; too many things at the same time and too much time for exercises. The pull request happens in the forked repository? Very confused
- It was unclear on what you would sync with - the fork or the central repo - and how to differentiate between the both.
- .Will we have some exercise for next week in order to remember what we 've done up to now?'
    - yes!  real practice
- Will need a little practice with the forking etc., but this was a nice intro, thanks!
- It was not clear on how the merges should be done, when there was also a fork present. Several people seem to have struggled with this, but it was never solved or clarified.
- After exercises, it would be nice if the instructors could show how things should look like when everything is done correctly. In some cases, I was not sure if everything went ok.
- It seems that GitHub has some extra features, build in routines, which are not necessarily a part of default git. I got confused when it automatically figured out pull request to central repository. I would expect that I had to explicitely ask for it.
- It might be just me, but I had some issues with ssh and took a veeeery long time to fix the connection. It happened but I was way behind what was happening. 
    - yes, and thank you! :) Ok, I'll do! Thanks for today, it was great!
- thank you, excellent exercises and so well prepared!
- Step E could have been clearer; that was the hard step, but the instructions were simply "do it"

### Closing questions, day 3
- How to I solve the issue of merging my branch in to the central repo main branch? I have asked this question multiple times for an hour now, still no solution.
    - I think it might be that you need to change the target branch of the pull request, it seems github by default sets the original repo/branch as destination, and you have to change it into your fork repo.
        - Why would I want to change it into the fork repo? It's the central branch I want to merge with, right?
    - I guess one wants to have the fork correct first, and then provide changes from it into the original repo.
        - The instructions were "Step D: Push your changes to the fork", which I did, then "Step E:  Open a pull request": Then file a pull request from the branch on your fork towards the master branch on the central repository. It never says that you should do a pull request on your fork.
    - If I am alone on the fork I can push to it and merge directly, but if sevaral people collaborate on the fork, the change should be approved and then merged, and then from there put in the original repo, as far as I get it. Maybe the moderators can say something about this?

- How do you do "Step E" in the exercise? I did a pull request, it was approved, but my branch still hasn't merged.
    - The owner of the repository should merge it. Are you in a group?
    - Approving a pull request does not merge it. It's an optional thing for a workflow where multiple people need to check each pull request. It means you have checked it, but maybe someone else in your team also needs to check. The last one would also merge it.

- Is it possible that setting the conda path environmental variables is why it now takes forever for command prompt/bash windows to open? 

    - Conda can create these kinds of issues sometimes especially when the command `conda init` is run. You should have a file called ".bashrc" in your home folder. You can open it with a text editor and check if conda has added extra commands. You can try commenting those lines (by adding a # at the beginning of each line) and then open a new terminal and see if things get better. We have a longer explanation here https://scicomp.aalto.fi/triton/apps/python-conda/ (expand the box "conda init, conda activate, and source activate").

