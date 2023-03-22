+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 2"
+++

## Icebreaker questions:

I am watching:

- by myself: ooooooooooooooooooooooooooooo
- in an organized group: oooooooooo
- group is online: oooo
- group is in-person: ooooooo


What has been your most collaborative project so far (tech or not)? How many people and how did you work? Do not put names or identifying information on this page.

- Building my house, including floor, furniture, and painting walls. We worked in 4 people and divided the tasks.
    - Cool! (+1)
- Research project with 4 people - we worked together in-person and over online platforms.
- Course programming project - 8 people, was chaotic
- Open-sourcing a large-ish project with many authors over 2 decades
- Research data management team with 8 people in total.
- Analysis of financial data with 4 people in total 
- First paper with 7-person team distributed from Western N. America to Asia, no one had ever published in a journal before - lots of spreadsheets and Skype meetings. Exhausting and often felt inefficient but learned a lot (I did a lot of the project management and handled submission and reviews). Having so many meetings was rough because someone always had to be working either very late or very early.
    - What did you use to write?
        - GoogleDocs (not my choice) :-( And then moved it to Word for final draft and submissions. One of my problems with the process was how much writing we did by committee. We used Google Sheets for collaborative text coding, that worked okay. 
    - What would you recommend to write with?
        - Depends on the team and process, I don't feel qualified to make a recommendation at this point. I just found the collaborative doc tricky and GDrive products can be very laggy with large documents. My second paper we used Word documents in Dropbox, which was better, but we also had only two primary writers. I am interested in trying RMarkdown for paper drafting since I am using R a lot in my current project.
- International collaboration of about 8 people. Mostly we used email and website based communication and we met a few times a year.
- Large infrastructure project with 100+ people involved.
    - How did you manage to make everyone be on the same page during the project development?
        - File management systems and a lot of meetings.


## Questions overnight, before day 2:

1. Will we receive a certificate at the end of the workshop?
    - Info here: https://coderefinery.github.io/2023-03-21-workshop/certificates/
    - Let us know if something is unclear and we can make it clearer :) 
        - "git log --all" only shows commits - is that all we need to submit for code?

2. History of git
    - "Git development began in April 2005" (from https://en.wikipedia.org/wiki/Git)

3. What do you recommend in terms of the number of (main) files created for a given project? What have you converged to in this respect? Yes
    - you mean like number of source files in e.g. a Python or R project?
    - yes
       - more about it next week but project almost always start with one file that at some point gets too large. I split the large file into smaller files once it gets difficult to navigate. Then I collect related functions into a file. Many projects of mine have a hand-ful of files. Only in very large projects I have more than 10 source files (sometimes 100). When a file becomes difficult to name it can be an indication that there are too many things in it and it asks to be split. It's really about making it easier for humans. For compiled languages splitting code into files can also shorten recompilation times.

4. How do I re-open the same work from yesterday in git bash for today? Complete newbe, so I don't know how?
    - either open Git Bash and navigate to the folder from yesterday with `cd` or in your file explorer file the folder from yesterday and right click you can then open it in git bash (I am writing this answer on Linux so I am not 100% sure myself)
    - I'll give it a go on windows, thx! - cd recipe worked fine :)

5. How can one close the chat window? theater mode is too small now
   - Try making the window larger/less narrow.  Then you can hide chat, and make it narrower again.



6. Do you think it (always) makes sense to introduce people to Git in a commandline setting... is there space for GUIs as their initial introduction (e.g. for people who don't otherwise use commandline... perhaps don't even code that much)
   - [Five reasons why researchers should learn to love the command line](https://www.nature.com/articles/d41586-021-00263-0) 
   - Learning the command line while learning git is a good "side effect". In general it is that kind of skill that can be very useful also outside academia if you keep writing code or supervising people who code
       - I agree... but it may be the case of getting people started (and getting them to continue using Git)... commandline may be too unintuitive ... too much of a leap / alien environment... GUI-based teaching at least gives them the theoretical grounding plus a tool that they can likely pick up quickly and easily in the future (and doesn't preclude a switch to cmd later)
   - Another practical problem: which GUI that works for everyone?  Could probably be solved though.
        - GitHub Desktop is pretty good
   - we also tried the other way: https://coderefinery.github.io/github-without-command-line/
   - TortoiseGit is a nice option
   - I am not sure you mean the other way to use git. I am using gitextensions sometimes
   
   
7. Git so far seems very useful for editing text, but what about, say, java code in eclipse?
    - java code is text right... +1, and git is overwhelmingly used for code actually. But it's easier to learn by not also focusing on the code at the same time.
       - yes Git is definitely very relevant also for Java projects
    - Yes it's text, but how would I use git? Will I go on using eclipse like normal, and then git keeps track of everything?
       - eclipse probably has plugins/extensions which use Git under the hood directly from the development environment (sorry I don't know eclipse well but I know that Git is great for Java)
       - It is also OK to use any code editor / IDE / etc. you are comfortable with and then use git from command line (like we are doing here in the lessons). I personally use this workflow (programming with VSCode and using git from command line.)

8. I have problems with sound in twitch, started with sound, then suddenly disappeared. Known problem?
   - Not sure, does refreshing the page work?
   - No, I will restart computer, thanks. 
   - Check if it's muted in the Twitch window - it can automatically mute for some reason.

9. Is Git usefull for all sorts of version control? e.g. word, excel, powerpoints, and other more "userfriendly" programs with less codng?
   - csv works okay - and small ones render in GitHub 
   - it's less useful for those files since they cannot easily be edited in a text editor. in other words it is less useful to version control binary files. Git (and any other version control I know) works well with text files (and source code are text files)
   - My similar but other view: if you don't have very many word/excel/etc files, it can still be better to git-control them than any other option.  You just can't diff / merge them, and all updates are all-or-nothing.  Not as good as with text files, but better than losing things.




10. Question: Is there any difference in philosophy to version control code, scripts etc. and data generated by them? I've interacted a bit with auxilary tools like dvc for example. (might be a bit of an advance question for now, so it's alright to postpone it.)
    - I have same question. The analysis of the data genereated (comments, steps etc) could be a tool to understand and assess our developing processes and solution approaches.
    - See also https://scicomp.aalto.fi/scicomp/git-annex/ 
    - The short take home message is that git is not efficient for version-controlling large files, but small data files are fine (e.g. csv). Git-annex (and dvc, and other options) extend this ability. They are not yet widely adopted but people are getting more familiar with "data versioning" as input (or output) data can change in time.
        - It seems like a quite rapidly developing field with plenty of new innovations.
        - Do the same principles apply to DVC as Git? Learn one => learn the other (easily)?

11. How can i see my folder structure in Git? I mean, if i want to see the location of my 'recipe' folder?
     - you need to locate it using your file explorer or similar. Git itself is inside that folder (there is a .git subfolder). It does not store the location outside of that folder.

12. Can we visualize the git graph like the figures yesterday in the tutorial rather than on terminal?
  
  - in practice you will later rather use "network" (GitHub) or "graph" (GitLab) but the lesson graphics have been made with https://github.com/bast/gitink (not very elegant code I wrote some time ago)
    - This is a non-answer but usually "can I do X with git?" the answer is yes.  For example `gitk` does this, but there are probably many more better ones.

- Your browser doesnt fit the stream. 
    - thanks. this is now zoomed in. or is this not rendering well? 
        - we couldn't see "the plus" in the corner for example, so far not a big issue. seems it might be fitting now, and only the picture covering few things. 





13. Whats the working principle (intuitive) behind HTTPS and SSH git operation?
     - it defines which protocol to use to authenticate whether you have read or write access to the repository. on github all public repositories can be read using https but to write (push) to a repository, you need to use SSH authentication (or authentication tokens which we did not mention)

## Git-intro day 2
https://coderefinery.github.io/git-intro/

### Sharing repositories online
https://coderefinery.github.io/git-intro/remotes/

13. About uploading projects online: is there any mechanism protecting users from undesired use (by companies) of our data avaliable online in these repositories such as git hub?
    - In theory, you would choose a license that is appropriate.  But, once information is out there, it's out there.  You do need to consider the risk of misuse before opening.  (Most of us believe more open is better)


14. I tried to clone what we have done so far but I got the message fatal: Could not read from remote repository.
    - "Please make sure you have the correct access rights and the repository exists."
       - in this case please clone using https. I assume you tried to clone with SSH. (later we will want to use SSH keys almost exclusively but in this particular case clone with https)
-I am in mac terminal and I simply did a copy and paste of git clone .... how do I clone using https? 
15. Can someone share the github repo link to clone from?
      - https://coderefinery.github.io/git-intro/remotes/#type-along-create-a-new-repository-on-github (the blue box "If you don't have the recipe ...")
      - but just to clarify, if you have the repository from yesterday, you don't need to clone anything right now
          - Yesterday we were not on github necessarely, right? I was doing on my local computer. Should I clone the github repo today?
             - correct. in this case nothing to clone. the clone is only if you don't have any repository from yesterday. our goal now is to share our work from yesterday to github





16. If we set up a repo from command line can we choose public or private?
    - Public or private is a property of the web platform.  When it's on your computer, there's no sharing (so always private).  Make the choice when making the web-repo before pushing.

17. Hi, if I set up another remote project repository by adding the git remote add origin remotessh, will the origin of the previous project be overwritten?
    - You can have as many remotes as your want - they have to have different names.  So no, not overwritten.  Good question.
    - tomorrow we will learn how to work with 2 or more remotes. to Git, they are placeholders for web addresses.
        - I'll try to remember to ask tomorrow... but I'm curious as to why multiple remotes would be used (different use cases?)
        - In my case, I have a remote project set up already with the name origin. I'm afraid that If I do git remote add origin newremotessh, the origin will be overwritten.. (I'm a participant)

18. What does SSH mean? What does it stand for?
    - "Secure SHell".  It's a way of asking remote servers, and it's very secure so Git can also use it for remote connections.


19. How do I know which username to use in the git URL?
    - `git@github.com` is always `git` - it detects you via your ssh keys.  Is that the question?
        - the "user" in: git remote add origin git@github.com:user/recipe.git
        - is that literally how it should be written, or should I replace it with my user name?
           - do not replace with your username. to clone a github repo, copy the address as it is, without changing it.
               - I'm not going to clone. My question is about creating a remote repo from my local repo
               - for instance dianaiusan in her url
               - Ok, so I can't create a github remote repo from the command line?
               - answer to my own question: the "user" should be replaced with the github username. like in 
               - git remote add origin git@github.com:the-user-name/recipe.git
               - before that, one has to create the repo in github, right? (it worked for me)

20. I am stacked because I cannot find the folder from yesterday. 
    - I would open git bash and type `ls`. There is probably a folder called "recipe". Otherwise try to locate it with the file explorer.cd workshop
        - I would expect you have one called "workshop" first and then the "recipe" folder.
            - Thanks that was it!

21. Why would we need to clone a repository? What is the main reason for cloning?
    - If someone has written some code that you want to get then they save it in their repo and you can clone it from there. You can think of it like cope-paste when you want to get what someone else has written.
        - so the branching is for collaborators and the cloning is for other people that want to use my code?
            - clone makes a full copy with all branches. it's often the first step in collaborating to even get the repository onto your computer.
            - If you want to make a new branch then you would clone first then make a branch. When you create a branch then it's similar to editing the main code base, but then you have two versions (i.e. two branches). In order to create a branch you need to clone what is in the repo. So the process would be: I clone the repo, then I create a new branch where I can make changes to the code without affecting the original code.
    - but in this case it was to make sure that everybody can participate from here on, also those who were not here yesterday or don't have the repository from yesterday
    -ok perfect. thank you






22. I already create a repository, but now I would like use the new repository (recipe). How can I  change the repository?
    - Is this repository on github or on your computer? 
    - This is in github.
        - At this stage I would start with a brand new repository and forget the old one. Alternatively one can rename repositories in the repository settings via github web interface.

23. Any restrictions on the repository name? Lower case / upper case? Special symbols? Numbers?
    - I am not aware of restrictions. I personally prefer lower case no special symbols, in practice the name will also be in the URL link, so you don't want to use characters which might be difficult to use (e.g. umlauts)
        - dashes are quite commonly used though "-"

25.  I am still stuck. How can I do the git clone thingy so that the folder appears on my terminal. I did 
     - If you have the folder from yesterday, you do not need to "clone". If you want to start with a demo folder, open the terminal and go somewhere "empty" (not inside another git folder) and then check the instructions at: https://coderefinery.github.io/git-intro/remotes/ where it says "If you don’t have the recipe repository from previous episodes

"

26. -- The concept "central source of truth" might be relevant.
    - good point. we will come back to this tomorrow

27. I am getting the error: Cloning into 'recipe'...
                            git@github.com: Permission denied (publickey).
                            fatal: Could not read from remote repository.
      - you probably tried to clone the SSH address instead of the https address. 
      - sorry my fault the material should have said: `git clone https://github.com/coderefinery/recipe-before-merge.git recipe`

28. Can I use git clone while being inside my old repository? (If I still want to clone for some reason) Or will that mess up the folders somehow?
     - you should step out of your old repo otherwise it will create a new folder and a new repo inside your other repo and it will be confusing (it is possible to nest repositories but not like this)

29. What is the role of `origin` in `git remote add origin`? Why to rename `master` into `main` before pushing our repo?
     - the renaming master (branch) to main (branch) is so that we follow closely what github recommends anyway but it will work also if you push master directly
    - "origin" is a conventional name usually refering to the repository (usually one online like on github/gitab etc.) that act as a source of truth. In advanced cases there may be many different forks of the repo and one might want to push/pull from many of them and then you'd differentiate the remotes by giving them names on your local machine. origin is just that default name essentially. Whenever you clone a repo, you typically call that remote origin except in advanced usecases. But don't worry to much about that for now.

30. What does it mean to "Add a remote reference with the name “origin”? Is it basically just modifying my local .git file to be aware of the remote GitHub server, whilst identifying itself as 'origin'? 
      - yes. then your local git will know what web address to communicate with when you later refer to origin when pushing and pulling (more clarification tomorrow)

31. Be careful with showing things on your shared screen in the right corner as your faces unfortunately is hiding it :) 
     - thanks I will relay this

32. why the command git branch -M main changed the master branch to main???
     - we could have left it master but default on github and other platforms these days is "main" and we wanted to follow precisely the instructions that you will see from github




33. I am getting the same error as above when trying to clone. Could you please address that? There are several of us stuck. I used "git clone git@github.com:coderefinery/recipe-before-merge.git recipe"
     - the error is: permission denied or something like that?
     - what was the precise command you have used to clone?
     - oh! the instruction is not good ...
        - sorry it should have been `git clone https://github.com/coderefinery/recipe-before-merge.git recipe`
        - I will fix answers above and also fix the material. Sorry all.
        - please reload page, fixed

34. Please, no I just copied and paste the git clone command right into my mac terminal. It worked yesterday but not today. Without the cloning we are stuck. 
    - To clone a similar repo to yesterday's: 

``` bash
git clone https://github.com/coderefinery/recipe-before-merge.git recipe
cd recipe
git remote remove origin
```

35. Now that I have pushed the files to github and run 'git status', it says that I have 'Untracked files' (.ingredients.txt.swp, ingredients_BACKUP_2077.txt, etc). Should I use 'git add' and 'git commit' on these files?
    - Those look like temporary files (you have a text editor open?); I wouldn't worry about them... it might be worth adding them to the .gitignore (using a pattern)?

36. What I do with this error message? 
    git@github.com: Permission denied (publickey).
    fatal: Could not read from remote repository.
    - "ssh connection to GitHub not set up": Try working on this installation step (OK if not done today, but important tomorrow): https://coderefinery.github.io/installation/ssh/#ssh

37. Once we create the github instance there are some things that cannot change such as name, availability etc. what issues would be raised if that option was available?
    - you can rename later and transfer later and also change visibility (private or public). if you move/rename it, github will forward to the new name if people look for the old name.




### Exercise: create github repository

:::info
https://coderefinery.github.io/git-intro/remotes/#exercise-push-your-guacamole-recipe-to-github
- goals: push the recipe repository from yesterday to your githuob account.  You should be able see your files on GitHub.
- If you can't manage: it's OK, next part starts from a new beginning.
- until when: xx:45

Your status?:
I am done: ooooooooooooooooooo
Still trying: oo
Not trying: o
Problems I couldn't solve: 

:::


38. I have a message error:
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com:NAME/recipe-2023.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

39. Getting this error on last step after putting passphrase for .ssh key
ERROR: Repository not found.
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.

  - Is the name/remote correct and matching what it should?
  - Yes. I can get through all the three steps, the last step where I push shows this message. I tried removing the remote origin and added again, but gives same error. I checked that my ssh key works well also.
  - Sorted it out :)

40. What is the -u flag in the push command?
    - Upstream which means it's pushing to the remote repository
        - Thanks. Where else can you push aside from remote?
            - You can push to different remote repos if you specify the remote-url path
                - ..so with the remote-URL path, you wouldn't use the -u flag?
    - more clarification tomorrow but my short answer is that you can also always leave it out but if you use it, it knows how they relate to each other and you get more information when using `git status` and you can type less when pushing/pulling since it then knows what you mean

41. Is there a way to see all created repositories on my machine? Since I had several trials from yesterday, I can't find my correct unfortunatly....
    - You have to find the folder in which you created them. I would suggest doing a folder search with the name of the folder you created yesterday
    - Are you on Linux or macOS? — then you could use `cd ; find ./ -name '.git' 2>/dev/null` This will list all `.git` directories recursively under you home folder. (`cd` changes to your home dir, `find` searches, `2>/dev/null` sends errors to nirvana)

42. Can I delete remote branches from the command line ?
    - Yes: `git push REMOTENAME BRANCHNAME --delete`

43. Is it possible to clone a specific branch already created and work just with it instead of main branch ??
    - yes.  I would often clone (gets everything) and then check out the branch I wanted.  `git clone --branch` does the checkout for you.





- Then, to push to this branch one should use something like `git push -u origin <branch>` ??
      - yes

44. what's the meaining of -u in the "git push- u"command line? 
    - See question 35
    - more explanation in tomorrow's material: https://coderefinery.github.io/git-collaborative/centralized/

45. Please be aware that we defined the repository to be named "recipe-2023", but the in the instructions, it is just called "recipe".
    - yesterday we recommended "recipe-2023"?
 
46. If I clone the repository does it fetch me all the remote branches?
    - It does by default fetch a full copy of all history and all branches (but only checks out for editing the default one)

47. I first run the git remote but it did not work. I figured out the issue and tried to run it again but I got the following error message: remote origin already exists. How can I remove the remote origin once created?
    - `git remote remove origin`
    - Thanks!!

48. Can you change the Github repo to become private. In Github settings, this option seems to be in the 'Danger Zone' for some reason?
    - Yes, you can (and it's fine here).  I guess it's "danger zone" since it makes big changes?
        - What are the big changes you are referring to?

49. Please, no I just copied and paste the git clone command right into my mac terminal. It worked yesterday but not today. Without the cloning we are stuck. Could you please help me with the cloning question? It 
    - maybe remove the folder recipe first before cloning? And make sure you start the cloning from the folder 'above' the recipe folder. Use cd ..
    - What message do you get?



50. Lets say we clone a repository from some else (lets say a code of how to do data analysis or even a model), but we want to create a new repository, where we save our changes, how we can do this?
    - In this case it would be better to fork it. This means that you copy it from their Github repo to yours. From your Github repo you clone it to your local machine then when you push changes, it goes to your repo and not theirs.

51. I'm facing the following error: git@github.com: Permission denied (publickey). fatal: Could not read from remote repository. Please make sure you have the correct access rights and the repository exists. We could have a SSH keys tutorial.
    - we have fixed our instructions, please reload: https://coderefinery.github.io/git-intro/remotes/#type-along-create-a-new-repository-on-github (here we need to clone a https address)
        - I did not manage to make this key thing to work. Instructions are not clear to me. Will it be a problem for the rest of the workshop?
           - no problem rest of today but we need to get this working for tomorrow. but even if it does not work tomorrow, it will still be really useful to follow tomorrow in watching

52. I did all the steps, but instead of 3 enumerating objects I have 34. Any idea what went wrong? Everything else seems to be as it should. I also checked on github and the 3 files are there. Just very confused by the 3 vs. 34?
    Enumerating objects: 34, done.
    Counting objects: 100% (34/34), done.
    ...
    - That's fine, it's just because it's uploading all the work you did yesterday (I had 61). It depends on how many commits you made. If you didn't make any, you'd get 3.
    - Great, thank you for clarifying!

53. Is it possible / easy to change folder name after creating a repository and publishing it in GitHub
    - yes you can rename and move the folder and .git (the folder inside your repository that keeps all the commits and branches) moves with it happily
        - You may change both the name or your local repository and the name of the remote repository. On GitHub, go to the main page of the repository Setting -> General. You will see 'Rename' at the right of the repository name.




54. General note: if anyone using Windows is having problems with Command Prompt/Git Bash terminals launching suuuper slowly, it may be Windows Defender. You can manually add the terminal apps to the list of programs allowed through the firewall.
     - thanks for sharing this!
     - thanks, how do you do this?
         - Open Windows Defender Firewall control panel, click on "Allow an app or feature" or similar option.
         - Click "Change settings"
         - "Allow another app" - navigate to where git-bash.exe / git-cmd.exe / cmd.exe live and add them each separately
         - Details may be different on your Windows installation, I'm running Windows 10

55. Can I clone all branches instead of just the master? Or can i clone specific branch? when I clone my own repo, only the master branch was cloned
      - when we clone we always clone all branches (try `git branch --remote`). More clarification how to work with those tomorrow
          - I get it. when I push the repo, I only push the main/master branch.. haha
               - yes we typically only push one branch (but it is possible to push all)

56. git push gives me the following error an I can not figure out how to solve it: 
        git push -u origin main
To github.com:user/recipe-2023.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com:user/recipe-2023.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
        Ok that must be the license file then!
    - It would still be interesting to understand how to solve a problem like this 
       - explanation is that you push a local branch which does not have all commits on the remote branch and it prevents you from overwriting the remote branch and losing those commits

57. If I use origin, the script doesn't work (error: remote origin already exists) , but if I use master, it works. Is there a way for using origin?
    - Did you do the "If you don't have the recipe repository from the previous episode" box?

Yesterday I created another repository in Github and I tried this command. Now I eliminate the old repository and I create a new repository called recipe-2023. When I use origin I have problems.
- `git remote remove origin` to delete existing remote

Thanks




58. I am facing a problem with connecting to ssh (in my local computer I have the ssh used for gitlab, not for github), and if I try to use the https it says permission denied (public keys). Any idea on how to solve this?
    - for pushing we will need SSH. it won't work with https. but don't worry for today, we will not need this after this exercise but we will need this a lot tomorrow.

59. In `git push -u origin main`, what does the `-u` key mean?
    - It's the short for `--set-to-upstream` and it means: create a local reference for branch main. That means that whenever you push  changes in your local branch 'main' with `git push` it will 
    - more about this tomorrow

60. I tried git remote add origin https://github.com/inaki-longarela/recipe.git . Do I have to be on the recipe folder? I tried that there and I got the message fatal: remote origin already exists. When I tried outside the folder I got the message fatal: not a git repository (or any of the parent directories): .git. But I don't understand, Ok!
    - you already have "origin" defined, try "git remote --verbose"
    - you can remove origin or redefine it with "git remote origin --set-url NEWURL" (or something like that, needs double checking)
    - Simple recommendation `git remote remove origin` to get rid of it and start from before.

61. I get the error "remote origin already exists"? Then I push it and I get an error that permission to my remote area on git is denied.
    - did you do the "if you don't have repo from yesterday" recovery box? 
    - No?
    - Hm, well, you can delete the remote with `git remote remove origin`.



### History inspection
https://coderefinery.github.io/git-intro/archaeology/

62. what is the readme file.rst?
    - "readme" is a common name for file in projects that gives a big overview of what's in it and basic things
    - the rst ending refers to restructured text. rst and md are very popular formats for README files (md much more than rst)

63. How do i access git history in my repository?
    - On your own computer: we will see some commands that do it, there are also other graphical programs.  Or, if you push to GitLab/GitHub, you can see on there.
        - Yes, where in github i can see the nice history browser as shown in the example?
            - did you mean this one? https://github.githistory.xyz/networkx/networkx/blob/main/README.rst
                - if yes, you can replace "networkx/networkx" by "youruser/yourrepo" and adapting the file you want to look at

64. I am stuck with : 
$ cd networks
bash: cd: networks: No such file or directory. 
    - `x` not `s` ?  Assuming you just did the clone command
        - i.e. `networkx` 

65. Are we meant to type along again or not?
    - yes
    - hard to decipher when it feels like he's just reading out loud...
    - Please make sure that this is the case, as these commands are part of the next exercise. The material says that this is for demo purposes????
    - no problem if you only watch this part, in the exercise we will test out these commands

66. For `git show`, is it enough to use a short version of a hash ID, i.e. first 6-7 symbols?
    - yes

67. I don't understand how I am supposed to use git commands when I am in a repository that does not have existing git according to the instructions in the begining. I am sorry, not following how and in what files these commands work.
    - These commands are meant to work in a git repository. If you're not in one, they won't work. (sorry if I misunderstood.)
    - I understand that, it is just confusing since at the beginning of the page it says that you should be in a repository that does not have existing Git. Maybe clarify this in the instructions.
       - the git clone part comes later. when the instructions were written they were meant for demoing only, not for type along. it is extremely difficult to make this not confusing.
       - I think what made it more confusing is that it was said we should be typing along
    - Ah, that's probably before doing a `git clone`. 

68. shouldn't you introduce bisect before having an exercise on it? (even if it's optional)
    - We cannot go though all material due to time constraints. There are rather clear steps on how to do the exercise, but if that is not the case, please ask.
    - it would be too confusing to introduce at this stage. this is purely optional and we are very happy if we all manage the first exercise part. the bonus exercise also works well in reading later.
        - ok :-)


### Break until xx:12

After break: Exercise (below)





### Exercise: archeology

:::info
https://coderefinery.github.io/git-intro/archaeology/#exercise-basic-archaeology-commands
* Try the basic things, bisect is definitely more advanced and optional
* Until xx:40

:::


69. Do we need to clone eventhough we are already in the networkx directory?
    - in this case you don't need to clone again, you already have it then

70. I have cloned networkx inside the recipe folder. Is there a way to move it up to the workshop folder?
    - first go "up" to the recipe folder with `cd ..` (verify with `ls`), then move the networkx folder "up" with `mv networkx ..`, then go "up" with `cd ..`
        - It worked, but now I get an error message when typing "git status". It says "fatal: not a git repository (or any of the parent directories): .git"
          - this means you are currently outside of a git repository 
              - I am inside nerworkx folder
                  
    - in doubt I would clone a fresh directory somewhere else so that you have the exercise time for the new commands
        - I will reclone, thanks
        - Will you explain later how to remove the cloned repository?
            - essentially just delete the directory (`rm -r networkx`) again (as long as you didn't add/commit the cloned directory). You will have to confirm a few file deletions, as git does create write protected files so that the repo is not accidentially deleted, but that's how you would remove that local copy.


71. Yesterday we tagged a commit... checkout out a commit and creating a branch at the same time seems to be similar... what are the best ways to decide when to tag and when to create a branch? I'm guessing a branch is more 'mobile' (we can commit on the branch and it will move to the new commit), whereas a tag can only be added or removed from a single commit?
    - tag should ideally not be removed unless some terrible mistake happened. they are meant to be as "landmarks" forever. as you write they are technically similar. branches move as long as they live but tags stay next to their commits.






72. $ git checkout -b exercise networkx-2.6.3
    fatal: a branch named 'exercise' already exists I keep getting this error when trying to get to the 
    - this sounds as if you already have a branch with the name (either created earlier or maybe fetched from a remote?). What happens if you do `git checkout exercise`
        - That takes me the excerise branch but do i not need to be in networkx-2.3.3?
            - That means you already did create the branch at some point in the past so you will probably have to delete that branch. Or you can use a different branch to start from the `networkx-2.6.3` tag.
                - Ok got it thanks!

73. what does the -b do again? git checkout -b exercise networkx-2.6.3
    - this is shortcut for first "git branch exercise networkx-2.6.3" (create a branch called exercise referencing the same commit referenced by tag networkx-2.6.3) and in the second step switch to it "git checkout exercise"
    - it is a shortcut to create a branch and switch to it in one step

74. after git grep I get no result, should I try something different?
    - what was the exact `git grep` command?
        - git grep "Logic error in degree_corellation"
    - could it be this: https://coderefinery.github.io/installation/shell-and-git/#on-windows-git-log-git-diff-git-branch-or-other-git-commands-show-no-output-at-all
        - No that was not
            - Try "degree_correlation"
                - No result again it seems to work though, tried also git log -
                    - sorry, two r, one l in correlation
                        - -That worked

75. Once I close the bash terminal and reopen it again, how do I get back to all the branches and avocado recipe things from the previous day? I cannot proceed with the excersises because of the following: "$ git status
    fatal: not a git repository (or any of the parent directories): .git"
    - Assuming you didn't switch to a different folder, you should be able to list all folders in the directory by `ls` (linux/shell) or `dir` (windows command line). This should show you a folder to which the recipe repository was cloned to. Then `cd` to that folder and you should be good to go.
    - but also for this exercise I would abandon the guacamole recipe and focus on the https://coderefinery.github.io/git-intro/archaeology/#exercise-basic-archaeology-commands since we will not need the guacaomole recipe anymore (except later some time for cooking)
        - true.

76. Do I understand correctly that both git branch and git checkout create a new branch? And that checkout directly opens that new branch as well?
     - "git branch" creates branch but does not change to it
     - "git checkout" can be used to switch branches
     - "git checkout -b" is a shortcut to create a branch and switch to it
     
78. In the exercise, point number 3 is to use git show with the specific commit but in the solution, the git show is not used. How do I get the commit number of the specific "networkx/algorithms/threshold.py:543:                print("Logic error in degree_correlation", i, rdi)"
     - to find out which commit modified this line, use `git annotate networkx/algorithms/threshold.py` and search for that line. on left side you will see the commit.
         - This is essentially what's done in step 2 of the solution.

     - is there a way to search for that line withoth spending time looking at it and searching for it
         - ` will pipe the output of "git annotate" into "grep" (shell command which can filter out certain patterns) 
           - for some reason it is not working. It is giving me just this sign ">"
               - What was the command you used?
              - ok let me test it on my side ...
                 - it worked on my side. hmmm...

79. I actually do not know now how to exit from here
    - hit "q" - did it work? No
      - here means you are now inside `git annotate`? or where are you currently? 
        - I am in workshop/networkx/exercise
        - I ll close git and reopen it
        

80. Hello, I would like to ask about the workshop materials available at https://coderefinery.github.io/. I have pretty packed schedule this week, will the materials be available also after the workshop ends?
    - yes. The materials stay online. and recordings will be available. so no problem.




81. When I get a lot of text and then :, git bush seems to be waiting for my input. How do I get the rest of the text printed?
    - use the arrow key "down" and "q" to exit

82. I can't type in the command line after "git annotate networkx/algorithms/threshold.py". Are you meant to "q" first or how can you type here to search for the "Logic error"? 
    - Try `/Logic error` ENTER.  If this is the "less" pager program that would search.
        - That helped, thank you, I was trying to type ' " ' and this didn't work. (+1)

83. At point 3 of Explore Basic ARqueology exercise I used the following command ```git log -S "Logic error in degree_correlation"``` and obtained the following commit as the latest:
    ```
    commit 1dc16026a654e6bca3f8d182a18e213b7fb31871
    Author: name <name@colgate.edu>
    Date:   Fri Aug 7 11:02:04 2015 -0400

    Merge master into iter_refactor```
- What's the difference with ```git annotate```?
      - `git annotate` will search through the current version (HEAD, your current hash) only. it does not search through all history
      - `git log -S` searches through all history


84. Why does terminal text autocompletion not work on `annotate` in `git annotate`?
    - git annotate will open another command line tool (by default `less`) which does not have autocompletion, so essentially you are no longer in the command line but in a program after running git annotate.. 
    - or did you mean that when you started typing the hash it did not suggest the rest?
        -  no, I meant when I press Tab, while typing `annotate`, nothing happens. At the same time, Tab works for `grep`, `show`, `status`, following `git` & etc.
            - Seems like git does not list this as a command, so the shell doesn't know about it. 
                - Clear, thx!

85. Isn't possible to inspect files with just the less command when we are in a branch inspecting older code? Do we need to type git annotate? Thanks!
    - Yes, that's correct (and probably what I would do).  annonate most useful when you want to know more of each line's history
    - less will "only" show the content but not when each line was modified last. if you need to know which commit changed a line, then "less" won't be enough but to browse the files itself, it is perfectly fine
    - Clear, Thanks!!
    - also try "blame" button on GitHub (the name "blame" is very unfortunate, not for blaming anybody)
        - They could have called it "author"... But admittedly you tend to only be interested in this if you want to know who "messed up" (at least in my experience :smile:)
            - for me the essential question should be *when* not *who*, and the who only to know who to contact for more context. often when I use this functionality with some irritation, I find that the author is me in the past.
            - Hahahaha! (+1)
            - Good constructive spirit also!93

86. I don't get this ... how do we actually create new branches: `git checkout -b` or `git branch`? 
    - with `git branch` you create a branch based on the commit your repositry is currently at. With `git checkout` you set the currently "checked out" commit or branch head or tag. And the `-b` flag in the checkout command indicates that a branch should be with that name. So, what `git checkout -b branchname <tagname/commit>` is essentially `git checkout tagname` followed by `git branch branchname` and `git switch branchname`. Essentially `git checkout -b` does multiple things and is just a very convenient shortcut. If you don't give a identifyable object as tagname/commit the current checked out commit will be used and only the `git branch`/`git switch` commands will be issued.

87. I don't understand exactly how to use bisect - it's simply the syntax I'm wondering about - and the "solutions" didn't show the syntax. What is the procedure? First we use "git bisect good somehash" and "git bisect bad somehash", but then what?
     - then you run the test (manually or automatically, here: manually) and after running the test you need to tell git whether the new hash it presented to you is working or not working (git bisect bad or git bisect good) and based on your answer it will present you a new hash. you can think of "git bisect" as a tool that creates branches for you in the past, traversing the past in the fewest possible steps and whether it should look more in the past or less in the past, depends on your answer (or a script's answer when automated). did this clarify a bit?

88. Is it possible to tag an old commit, for example to add tag for version numbering . Do I need to commit tags...?
    - yes: `git tag TAGNAME OLD_COMMIT_HASH`  (same idea works with making branches from an old point).
    
89. The 'degree_correlation' example seems to show that `annotate` should be used with care: when you switch to the commit where the change took place and use `annotate`, the line is correctly attributed to user XXX... but if you use `annotate` on the main branch, it looks like someone else (user YYY) was 'to blame' (plus the files were moved around - threshold.py was moved into a new 'annotate' subfolder after that change)
    - this is a great point and good to remember when copying large part of code from somebody else. even if the other person agrees, git history will then say it was you who added it. and 3 years later somebody runs "git annotate" and then asks the "wrong" person questions or gives credit to somebody else.

90. According to the answer, the line "Logic error in degree_correlation" was introduced in a 2017 commit. However, if you type `git log -S "Logic error in degree_correlation"` the answer is a commit from 2005. Why is this?
     - thanks. I will double check this as soon as I have a minute ...
         - this relates to the stuff I mentioned above - the actual commit was due to dschult in 2005, but if you annotate the file in main branch it looks like it is attributed to someone called YYY in 2017
        - Actually there is a minor change in that line in the 2017 commit. Spaces were added in the line in the 2017 commit, so it is correct that 2017 is the last time this line was modified, but of course the logic/function didn't change in 2017.
        - Why didn't it show up when using `git log -S "Logic error in degree_correlation"`? I assumed that any change affecting the line that contained that text .... oh wait...
            - Because it actually notices what was changed in that line and that it was only spaces. So the "Logic error" string was not modified and thus doesn't show up...
            - I see now: there were spaces in the same line after the "Logic error .." string, but I'm surprised that string didn't get found regardless, given that it did show up unchanged in the diff
            - ps.. is it normal to have so many changes in commits? Long diffs!
            - no, but this is a typical commit where code style is changed. And then you get loads if almost every line changes from `function(a,b,c)` to `function(a, b, c)`
            - Understood (but I'm still disgruntled that the string didn't show up in `log -S` given that it appeared in the diff :/ )
                - As I said, the problem here is that git is "too clever" and only shows the actual changes, while diff shows all lines. But I agree this can be irritating and unintuitive.
                - Thanks for clarifying! (good example :} )
91. What does "git log -S sometext" exactly do since it shows text where the string sometext is not there (I substituted sometring with "algorithm")?
     - it looks through all commits and (unless I am wrong ...) lists all commits where a string was added or removed. but please verify this.

92. I did not understand one thing in the exercise: "Now compile and/or run and/or test and decide whether “good” or “bad”." How would I run/test or check each commit?
    - After `git bisect`, you may for example compile the code and do a test run. If it runs without errors, you mark the commit as 'good' with `git bisect good`, otherwise mark it as bad: `git bisect bad`. After any one these commands, Git will automatically continue to swipe through the commits until it finds the latest stable one.
    - In the exercise, you run the ```get_pi.py``` file and see if the output is correct or not.

- How do I check what exactly there is in that specific commit? Then i will need to copy it into the SPyder for example, run it and see which one is the wrong one? If there are 251 commits, will I need to run all of them?
    - also answer 87 might help

93. I could not push my repository. I get the error "fatal: Authentication failed for 'https://github.com/inaki-longarela/recipe.git/" although I am sure I am using the right pasword and username in github.
       - I am guessing that origin refers to a https address (verify with `git remote --verbose`) - is this the case?
       - Yes, it is. but I am doing the whole thing from mac terminal. Does this matter?
       - What do I do?
           - you can change the remote to a ssh remote (on the green "code" button on github select ssh. Copy the line (starts with git@github.com...). Then on your local repo run `git remote --set-url origin <put the line you copied here>`.  The problem with https remotes is that you need to set up tokens etc. 
           - I don't really understand. What do you recommend then? I don't know what you mean by setting up tokens. How can I push it then
           - I tried with ssh and followed the instruction in github to push but then I got the message  "git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.
 


94. Is there an opposite of ~1, for the successor of a commit?
    - no, since git commits only know their ancestors but they don't know their children. git is a "directed acyclic graph" and the direction points towards parents.
    - in practice, this is usually not a problem unless we remove a branch that has never been merged and then we can have a hard time finding the commits (but we can find them with `git reflog`)
        - thanks!
    - (that would also be logically problematic, since a given commit may have an arbitrary number of successors. Which one would it choose.)


95. What is first parent of 90544b4fa? (Oh I get by the context, it's the first ancestor commit, right?)
    - yes

96. In [Exercise: Basic archaeology commands]([https://coderefinery.github.io/git-intro/archaeology/#exercise-basic-archaeology-commands), we create branch `exercise` from `network-x.x.x`. Then, we create another branch from `exercise` branch. I don't  get it, why?
     - ok the first branch "exercise" (created from a tag) is to make sure that this exercise will work even if the networkx people change their repository so that it does not break our exercise in future. so we already start a bit in the past in this exercise
     - the second branch we create even further in the past because we want to show that this is a good mechanism to visit past commits since branches in git do not cost anything and then there is a "marker" which you can later remove again as soon as you don't need it anymore
     - is this now clearer?
         - Well, clearer, but not entirely, since any new branching makes the history structure more complicated, and there is a natural fear that in the future you can face with conflicts, while merging branches. Let me ask some more Qs: could I browse & use the code, being at branch `exercise` without creating another branch from that?
             - yes you could have done `git checkout somehash` where you visit `somehash` without creating a branch.
             - confict is no concern here since we don't really intend to integrate that old code into the new code, it is only to visit it and do some experiments and to perhaps compare it with new code. this can help debugging.
                 - alright, makes a better sense now... thx!


## Undoing and recovery



96. Did you skip the (https://coderefinery.github.io/git-intro/staging-area/) staging part?
    - We will not cover the staging area lesson. Left as read-at-own-pace material.

97. I am wondering... So we created a repository in Git. Do our comits being updated automatically in the repo from pur local machine changes? Or we should do additional... Ah, I see. Thanks! 
     - No. You need to `git push` when you want the changes in teh local repo to be implemented on remote GitHub repo.
     - all git commits except push, pull, clone, fetch (we haven't seen it) are local operations and don't synchronize, they only modify our local repo

98. What is the exact command to `git restore` for previous git versions?
     - so you have a couple of commits and you want to change past commits or remove certain commits and go back to a previous commit? (trying to understand what exactly you are after before writing more concrete)
         - they basically said that for previous versions we use `git checkout` but not sure the exact command
             - ah, if you want to visit previous versions (and later return to the latest version), then the preferred way is `git checkout -b somebranch hash` where "somebranch" is the branch name and "hash" is a commit identifier in the psat

99. If I restore to an old commit I lose all of the afterward modifications? 
     - you mean "reset"? if yes, then it will move the branch back and the commits that came later are lost. but you can still find them with `git reflog` if you did this by accident or change your mind.

100. does git reset only change the branch pointer, or does it also affect the staging area?
     - it also changes the staging area, removing everything from there as well.
         - Depending on the option you use with `git reset`. If you `git reset --hard` it will remove modifications from working directory and index/stagind area. `git reset --soft` will only move the HEAD, but keep index and working area as they are, and finally `git reset --mixed` (default option) will move the HEAD reference, clear the index (so no staged file afterwards), but keep the modifications in the working directory.
             - so reset can be used instead of restore? (in some cases?)
                - only if you haven't commited anything yet and only if you want to go to the current head but they are fundamentally different commands in what they are supposed to do. 
                    - I would add that `git reset` is an alternative solution, but the commands are not identical. And commits will dissapear from history (think `git log`) if you use `git reset`. `git restore` will keep the old history but add new commit(s). 
    - thanks!

101. If you've pushed a bug to production, you should probably do a revert. Don't mess with history of a "source of truth repo"
     - fully agree. I like "git revert" and one can add more context into the commit message. "git revert" is always a safe operation since it does not modify past history


102. more cat content 🤩: ooooooo
     - :heart: (+1000000)
     - (= ФェФ=)
     - yes! finally
     - oh no, I missed cat content ;_;
       - twitch/youtube channel later :-)
     - this is what you should be screenshotting and posting.  (unfortunately cat does what it wants so can't be summoned)

103. A potentially useful practical point: "Undo" in git is highly dependent on the context, i.e., do you want to undo changes before committing? After committing? Before pushing to remote repo (e.g. github)? After pushing to remote? Etc. Because of this, there is a lot of different ways of "undoing" and you can find a good way to go about it using resources such as this blog depending on which scenario you are handling: https://github.blog/2015-06-08-how-to-undo-almost-anything-with-git/
     - edit: after several years of using git, I still go to these resources when needing to undo :)
     - thanks for posting this

104. Scenario: I made three commits, 1st was correct, 2nd was wroong, 3rd was correct. When I revert the 2nd (wrong commit), it will create conflict. Althoug this logic makes sense, wouldn't it be very tricky to resolve the conflic if the wrong commit is quite old (say I made that mistake two months ago)?
     - yes indeed. in this case it might be easier to not use "git revert" but to manually create a new commit that manually undoes what was done many commit ago but make sure to refer in the commit message to the old hash so people later have some context that they are related.
         - Thanks! So it is more like a "fix"?
             - It may be good to think that the version history is just that, history. It may contain mistakes and often does.

### Break until xx:08 / Exercise xx:30
:::info
https://coderefinery.github.io/git-intro/recovering/#exercise-revert-a-commit
* 1, 2, and 3 on that page.  Do what you can, if you can't do all it is OK.  bbx 
* Break until xx:08, exercise until xx:30

I am:
* done: ooooooooooooooo
* need more time:
* not trying:
* having problems (please indicate your problem in the questions): oo
:::

103. Can you do the exercise and we write along? (+3)
     - We've tried this before, but it's hard for people doing it themselves to focus and it's very easy to get off-track if we don't go very slow.  And doing it twice takes a lot of time.  So... we try to summarize when we can.
     - Ask us to demo and we can do a quick demo sometimes.

104. In which repository are we supposed to do the exercise? networkx?
     - No. The 'recipe' repo. You could in principle use any repo for testing things out. It's a great exercise to use more complex repositories so that you can play around with more complex commands.
        - oops sorry to the person where I wrote we won't return to recipe repo anymore

105. I tried to push my code with ssh instead as you suggested earlier but then when I typed the push thingy I got the error message 
     ```
     git@github.com: Permission denied (publickey).     
     fatal: Could not read from remote repository.
     ```
     - Make sure you have ssh keys set up and that you use the correct remote URL. Type `git remote --verbose` and the origin should point to your own remote repository on GitHub (under your own account).
        - What do you mean? I did git remote --verbose and there is no spelling mistakes. How do I check if the origin points as you say?
             - followed up in next question. in short: github needs to know your public SSH key otherwise it cannot recognize you

106. (from 105) It was not a spelling mistake. How do I check if the origin points as you say?
     -  I think most likely it is the "ssh keys".  Were you able to push to github in an earlier part?  The setup guide: https://coderefinery.github.io/installation/ssh/#ssh
     - No, how do I set up the ssh keys. Do I do that in github? Thanks!
         - Follow the instructions in the link above. There are steps you need to do on your computer and steps you need to do on GitHub. We have a video as well for setting up ssh keys.
         - see guide

107. i am getting an error using the recipe repo due to unmerged files (using my own recipe repo from the exercises yday). is it best to use the recipe repo from github instead?
      - maybe you are still inside the conflict resolution from yesterday? if yes, you can `git merge --abort` and continue from there hopefully. otherwise a fresh git clone is also a good idea.
          - "there is no merge to abort" :( will try cloning instead. 
               - ok.

108. The solution to excercise 2 (undoing) isn't very helpful - it's not entirely clear how to use the git add and git amend commands with the newly created commit that I want to correct.
       - sorry. first create a commit (you have done that)
       - then: make a modification that you want to add to the last commit
       - "git add somefile" (the file with the modification)
           - So I make a seperate file with a modification or do I do this in the existing ingredients file?
             - same file in this case 
       - now: "git commit --amend"
       - if you only want to modify the message but not modify changes to files, you don't need to "git add" anything and go right for "git commit --amend"
   - how is this different from two seperate commits/commit revert?
      - in revert we create a new commit but the `--amend` modifies the last commit (technically it creates a new commit which replaces the last commit)
         - ok I get it :)

109. I see this message when I try to amend commit, after correcting a typo:
     ```
     You asked to amend the most recent commit, but doing so would make 
     it empty. You can repeat your command with --allow-empty, or you can
     remove the commit entirely with "git reset HEAD^".
     On branch typo
     No changes
     ```
     - Ah, I guess your change exactly undid the latest commit.  Try making a different change?
         - Okay, Thanks!

110. Do we have access to suggested solutions to the exercises?
     - there are the "Solution" boxes on https://coderefinery.github.io/git-intro/recovering/ but probably you mean something else?
     - I actually mean that but I see no solution box. Is it on just some exercises only?
     - sorry, I found it
         - some don't have it because the steps are the exercise but it would still be nice to add boxes there with some discussion



111. If one already has all the scripts related to a publication and wants to put them up on github, how should one go about it? Say there is one main directory with multiple directories within it with multiple scripts. Is there a way of pushing everything to github at once?
     - git add -A, from the docs: https://git-scm.com/docs/git-add#Documentation/git-add.txt--A


112. I though ```git reset --hard``` would destroy information, but it is still there with ```git log --all```!?
     - `git reset --hard` moves the current branch but actually leaves commits unchanged but they become more difficult to find
     - if there is another branch (possibly on a remote) with the commits, `log --all` will still show.
        - But the info on the removed commits should not show with `git log`.

113. Why is Readme a *.md and not *.txt? 
     - `md` is markdown, what we are writing in here with stuff like **bold** and *italics* and [links](https://coderefinery.org).  GitHub/Lab format this nicely in the previews, which is nice

114. I would like to know how to use .gitignore. Any tutorial or lesson?
     - Hm... this is our intro: https://coderefinery.github.io/git-intro/basics/#ignoring-files-and-paths-with-gitignore
     - Basically, `.gitignore` is a text file, each pattern in there is ignored.
     - The docs also have some examples https://git-scm.com/docs/gitignore#_examples Try various options and see how files are ignored or not.
        - Do I need to create a .gitignore.txt in my local repo? Or it is there by default?
          - The filename is `.gitignore` without any extension: "Patterns read from a .gitignore file in the same directory as the path, or in any parent directory (up to the top-level of the working tree), with patterns in the higher level files being overridden by those in lower level files down to the directory containing the file. "
          - 


115. ERROR $ git revert 3af9633 error: your local changes would be overwritten by revert.hint: commit your changes or stash them to proceed. fatal: revert failed
     - That is because you have uncommited changes in the working directory.
     - It's generally good to commit everything before doing these types of changes (merge, revert, etc).  Becasue if things go wrong, the previous changes are messed up.  So it might be annoying but better than the alternative.

116. If I use `git reset --hard hash` does it creat a branch just before that commit? or in that commit
     - It moves the current branch to exactly the commit you give

117. yay more kitty :cat2: (+104)
     - Hecking cute
     - I wish my cat would like to be held like that <3
     - I wish I would be held like that (+1)
     - I wish I was a cat (+3)
     - give the mic to the cat
     - Why am I always looking at the wrong window when there is a cat?? (+1)
     - All hail to the kitty

118. What is the difference between local and global aliases?
     - local = only in that repo (without `--global`)
     - global = for everything in this user account (not actually "on the whole globe!")
     - system = for all users of the computer

119. when i do ~/.gitconfig i see this:
     ```
     /c/Users/name/.gitconfig: line 1: [user]: command not found
     /c/Users/name/.gitconfig: line 2: name: command not found
     /c/Users/name/.gitconfig: line 3: email: command not found
     /c/Users/name/.gitconfig: line 4: [diff]: command not found
     ```
     - This looks like you are trying to run this as a program.  Open it in an editor: `nano ~/.gitconfig` or similar.

120. Is there a way to remove an alias?
     - easiest to remember: edit the `.gitconfig` file
     - probably some command to do it too.
     - `git config --unset alias.aliastoremove` add `--global/local/system` as required

121. Where are you in the lesson?
     - Sorry, added below.

122. With `git rebase -i HASH` do we go back in time and just delete anything that happened after that moment? Is it deleted forever? (e.g. a password was accidentally added to a commit)
      - this command opens an interactive editor (also see 124) where you can then decide to delete, reorder, squash commits, etc. the command itself does not do anything on its own yet.

123. After doing a `git reset --hard <hash>` we can safely push to the GitHub remote even if the 'post-revert' commits are already there?
     - github will actually not let you push and complain and that's good. it will not let you accidentally lose the commits remotely. but you can force-push if you are sure that this is what you want to do

124. What if you notice sensitive information added a few commits ago, how do you delete only the sensitive commit?
     - you can remove specific commits in the past using "interactive rebase" (git rebase -i). it can do a lot: reorder commits, change commits messages, squash commits, delete commits. but it changes history. but sometimes you have to.

125. What is actually a **tag**? Can I understand it as an ID of a commit and other events in repo life?
     - you can think of it as "sticky note" with a human readable name sticking to a commit hash which is difficult for humans to remember and communicate
         - a sticky note only to `git commit`?
             - yes, it refers to a commit. try: `git show sometag` and it will give some metadata and the commit it refers to
         - a note like a pointer to a particular historical moment? it's just looks weird to me that one can **restore from a tag** or **continue working from a particular tag**, really confusing

126. I would like to know about stashing ? 
     - how to use it or when to use it?
         - Both
         - (Trying to write a practical example...): stash is useful e.g. 
         - when you're working on a branch (say, main) and need to quickly visit another branch (say, experiment). In this case, "git stash" will put your current non-committed changes in main "on a shelf" and you can take them back with "git stash pop". Example:
         - git checkout main                    # go to main branch
         - git status                           # status shows "nothing to commit, working tree clean"  
         - echo "content for a file" > file.txt # make a text file
         - git add file.txt                     # stage the file.txt
         - git status                           # status shows that file.txt is staged
         - git stash                            # this will put file.txt on the shelf
         - git status                           # status shows "nothing to commit, working tree clean"  
         - *do some other work here, e.g. git checkout another branch and work on it*
         - git checkout main                    # go to main branch again
         - git stash pop                        # return ("pop") file.txt from the shelf
         - git status                           # status shows that file.txt is staged (how it was before using "git stash")
            
         - Hopefully this made some sense :)
                 - Great, Thanks at lot :)
                     - Great! :) Optionally, you could create another branch, commit file.txt there, go work on the other branch, return to the another branch, eventually merge it to main... so in some cases such as this stash can be quicker
         
127. In "Git under the hood" section, what exactly means "Let us open this file and change it to: ref: refs/heads/idea-3"." How do I open the file?
     - with a text editor, such as `nano refs/heads/idea-3`

128. Why isn't git LFS used in this course?
    - Good suggestion! https://git-lfs.com
    - I have not used it myself so I think these lessons have focused on tools that people use the most.
    - it's at least mentioned somewhere in the lessons but we did not mention in voice probably.

129. Is there good way to encrypt git repo so that is would be safer to keep in the github or somewhere else?
     - If it is important to keep it safe, don't use github. The "remote" can also be an ssh server e.g. you have a project folder in a shared server.  
     - https://github.com/AGWA/git-crypt 

130. How do I commit from Spyder for python codes? 

131. On a similar tangent as 131, how would the best way be to use it for MatLab code? Does it make sense to work inside MatLab, compile/run etc. in there and then use git once in a while to upload versions?



## Break until xx:00
Then we will discuss best practices 


### Practical advice: how much Git is necessary?
https://coderefinery.github.io/git-intro/level/


Any questions/comments about "how to use git in practice?  What's the right strategy?"  We will discuss together after the break.

How do you [plan to] use Git:
- For coding, working on a script together with others (+4)
- For sharing the ready code (publication) (+5)
- For keeping and sharing my (research) data analysis code and share it for publications (+3)
- For keeping my research code updated (and shareable when needed) (+6)
- For using other people's code (R packages etc.)
- For keeping track of my own code (+4)
- For seeing the changes I have done on my code and go backwards before continuing. Also I used it to see what other users did before me. I use the git for modelling.
- For KEEPING TRACK OF YOUR PHD MANUSCRIPT main versions, aka new chapters, new iterations of full sections or revisions from your advisor(s).
- - I have several codes that use the same functions just with little changes (I would like to perhaps be more efficient by using branches)
- for keeping track of different projects I'm following (work, learning or hobby projects) with github project board (not really git but github...)
- I would live to use it to update my own project on Github faster. I would also love to learn ways to use it privately with LaTeX.
- For data management and collaborative works.
    - It would be interesting to know if there can be a "git-philosophy" to enable good data management practices.  


What is git *not* good for (that you still need):
- For writing documents together with others. (+1)

- For jupyter notebooks (lol) (+3)
    - Why, if I may ask? (+1)
        - Any figures (eg. matplotlib plots) may make the notebook a large file.
    - The tracked file is the .ipynb json file where the changes are not that obvious (diff does not work well) (+1) 
    - whenever you re-run a block of code the code becomes unstaged (+1)
    - CodeRefinery Conda environment contains tools that
    - Use jupytext https://github.com/mwouts/jupytext (:heart:)

- For versioning portions of data/methods deposits that are not simple text files (+1)
- For LaTeX collaborative documents. Do the instructors use this instead of Overleaf?
- For storing data
- For drawio / powerpoint. I would like to have drawing program with underlying text



## Feedback, day 2
:::info
See you tomorrow, there will be an important email about preparation for the exercises tomorrow with something you need to do in advance.
It's OK for others to join tomorrow, if you go through the preparation (see email/website).
:::

Today was:
- too fast: o
- too slow: oooooooooooo
- good speed: oooooooooooooooooooooo (+1)
- too advanced:o
- too basic:
- right level: ooooooooooooooo
- I will use this in my work: ooooooooooooooooooooooooooo
- I would recommend this to others:ooooooooooooooooooooooooooooo o1]1=
- I would not recommend this to others:


One good thing about today:
- git add --patch
- I feel inspired and encouraged :) +6
- I have a good plan for the future (+1)
- happy to learn about the commands that I have been just told to use previously (+2)
- git bisect is quite useful (+4)
    - the bisect example was good and pedagogical!
- iI'm sstarting to see the usefulness of git (+2)
- Good to know how to create a repository and push code
- cat!(+10)
- enough breaks (+2)
- it was nice that you provided the yesterday's exer4ises (possibility to clone them) for those who didn't4do them (+5)
- agree with above written: it is super nice to have the previous code from beforehand excercises!!! Thank you! 
- cherry-pick is useful... also `reset --hard`; starting to feel a lot more intuitive to play with a repo's history (+1)


One thing to be improved for next time:
- Way too many breaks without excercises to do -today (+17)
- I am a bit confused. There are too many commands to do the same things
- More type along excercises maybe (+2)
- insist that attendees have checked their environment (+1) 
- Give more concrete examples of solutions in the exercises - some were unclear.
- Generally the setup is great to follow, but as a beginner with the whole environment (git bash, nano etc.) I sometimes need repetition of the very basic commands. Maybe those could be included more? (I tend to just go back to the older instructions, but it trips me up) (+1)(+2)
- Pause the teaching everytime cat comes on camera!



Any other comments?
- not sure what to do, what I'm personally confused, can't understand how to do an exercise, but the course continues : keep on following the instructor or to stay with the exercise until I have it solved
    - I'd recommend follow instructors.  This is why we have the material available for immediate review after (and when something is critical for next step, we try to give more time/make sure).
- It could be fun if all of us at this workshop worked on a test project together, to illustrate how to do it in a big group! (Once we are ready)
    - creative writing... text-based-improv :D
- Thanks again to the organizers for a job well done (local and on twitch) (+2)
- I found the personal comments on how you guys use git and your practices usefu
- Thanks for the recommendations for how much git is necessary for different types of projects
- I am scared that too many branches would mess up the project.
- I would prefer if the teacher does the exercise and explains each step. Which now happens after we do the exercise. Why not do it and we follow?
  - I rather do them myself, I learn better that way. +1
- it would be helpful to add the commands that are only said by voice (it didn't happen much today, but if in the future I have to go back and see these exercises again, it could happen that some parts are missing). (+4)
- Please, tell DI never call **TeX** and **LaTeX** with _eks_ in the end. It's _eh_. DK (the original author of TeX) wouldn't be happy :)
    - I thought it was '_ek_'
        - read wiki on **TeX**, the name comes from Greek, not from Latin. At least, there is certainly no _s_ in the end.
    - DI: Pls. don't tell him. :)
        - I won't :)

- is that a home office or does the cat come to work? 
    - haha! would like to have an office cat
    - The cat doesn't play by the rules...he/she roams
    - home ()
    - can we ask the cat's name?
        - online name is CATS.  Anyone get the reference?
            - they can pull any git from the web. they're equally cunning with bash..
    - can it say "meow-w-w!" ?
        - echo "meow-w-w!" ;)
            - s="meow-w-w";
            - printf "%s\n" &s;
        -  cat
        -  `cat meow.txt`
        -  git add "meow-w-w!"

- Data versioning usecase using an additional tool called dvc. Potentially combined with continuous integration. (+1)
    - The idea is to logically separate code and data. You define a pipeline and datastorage using dvc and then you track checksums and the whole dependency graph using git.

- Does Overleaf have version control? 
     - It does but it is a premium feature
- Thank you so much for the great management of questions in the shared doc! (+1)
- 

- Excited for tomorrow! Thank you for everything so far :D :heart:

- I have been asking ChatGPT the most stupid / out of sync questions about git. It has been useful. Such as "where is .gitconfig in windows 11?"

- what was the difference between the two ways of creating a branch? the one with git branch and the one with git git checkout -b temporary ?
    - It was about swithing to a branch, a bit unclear from my part. One may `git switch branch` for newer (> v2.27) versions of Git, or `git checkout branch` for older ones.
    - yeas but it seamed like there was also two ways of creating one. The one we learned yesterday vs today?
    - you can create a branch with `git branch <branchname>` and then switch to it with `git checkout <branchname>`. The other command `git checkout -b <branchname>` is just convenient combination of these two. You create the branch and then immediately switch to it.
    - Thanks! That clarifies it!

- I think it'd be useful for participants how to edit prompt in such a way, that it shows on what branch you are, whenever you are in a git repo. Also, it'd be nice if you implement it for your code samples in a Git tutorial. I thought about it after I look into your link, which you put in reply to Q.21 from day 1.

- What is _stash_?

- What is the official Git documentation? Is it [here](https://git-scm.com/doc)?

- Is a git repo is essentially a folder, local or remote? For a git newbie, the word `repository` is confusing.
    
- Thanks a lot for today!

