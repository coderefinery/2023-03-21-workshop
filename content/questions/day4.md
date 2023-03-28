+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 4"
+++

## Icebreaker questions 

### Icebreaker Q1: Computer programs are expected to produce the same output for the same inputs. Is that always true for research software? Can you give some examples?
- I guess it depends, it can vary depending on the code. In my experience sometimes the same code can generate different results depending on the particularities of the functions of the code. Some use different seeds.
-  Not only on the code. It can vary depending on the toolchain and flags we use to compile it.
- The same version and compiled the same way (dependencies, arhitecture, optimization flags, ...), yes. What I would add is that it is important to track what version is actually used to produces the results. I find it very useful if the program prints out the version, otherwise it is wise to do it oneself.
- Perhaps if the computer performance is different it could affect the results?

### Icebreaker Q2: What do you want to be when you grow up?
- Data science & bioinformatics expert :)
- Geneticist focused more on bioinformatics
- I just started in an HPC center
- Have a happy life (totally agree)(+3)
- Psycholinguist/Neurolinguist - but aspiring to get more into Data Science, because it's cool!
- Happy (+6)
- A good dad/mom (+5)
- A useful person (+1)
- Retired(+4)
- Proud of contributing to something, small or big
- Pro-Programmer 

### Poll: Do you start this week or did you already attend last week?
  - Started this week: ooooo
  - I also attended last week: oooooooooooooooooooooooooooooooooooo

## Questions on last week's material

1. I can't get the link "Very detailed 2-page git cheatsheet" to work on this page: https://coderefinery.github.io/git-intro/reference/ I just get "404 File not found". Thanks for your help!
    - Fixed now :relaxed: Thank you for notifying!
        -Thanks so much!

2. Could you clarify the concepts of the branches combined with having your local repository, your forked repo and the central repo? For example, all of them have a "master" branch, so if I talk about the master branch, which one am I referring to? And where should mergers happen? All these things weren't properly discussed last week.
    - You have multiple repositories:
      - On your computer
      - the main repository online
      - maybe also a fork online
    - each repository has a bunch of forks. At minimum they all have a main or a master. (They can point to different code, but I like to keep them the same on different repositories.)
      - Multiple people might be working on the main online repository. So there might be changes your don't have
        - When you run `git pull`, you get those changes and merge them. This merging happens on your computer.
        - Then you may run `git push` to get your own changes to your online repository. This merge happens online (so it only works if the computer can do it. No conflicts allowed. You must pull first.)
      - If you make your own changes (say on branch "example"), you can `git push` them to the online repository. This merge happens online. (so no conflicts allowed, you must pull first.)
      - If you have fork you push to, then you will need to create a "pull request" (as we saw on the exercises). This asks the owner of the main repository to pull and merge those changes.
        - The owner can then click "merge pull request", which triggers a `git pull` (technically `git fetch` and `git merge`, actually). This merge happens on the main repository. Again, no conflicts allowed.


## Reproducible Research
https://coderefinery.github.io/reproducible-research/

### Questions

3. Could you please elaborate on this "reproducibility crisis"? How did it start?
   - Yes. And we will discuss this also later during the lesson.
   - I approve the new spelling of "crysis" - cause we cry because of it :crying_cat_face: haha
     - aha, I thought 'cry' was for very cold :-) but that is 'cryo'
        - haha yes, that's true! It's from Greek
        - but can it run crysis?(+1)
            - no, I don't think it's correct, unfortunately :P
  
4. Man I wish people were less selfish, I totally believe that science should be more collaborative and "for the good of all". Should we maybe redesign the funding and publishing systems? :D (+1)
    - I have the same wish, no answer though.
        - Stop the criteria of publishing x amount of articles to promote?
        - I totally agree. We should care more about the way the research is conducted (i.e., quality) rather than publications per se...
    - There are many initiatives for "multi-lab" (many research groups collecting independently data to answer the same question) and "multi-verse" (one big dataset analysed in parallel by many research groups, each using their own methods) projects. Here a multi-lab example from psychology https://psysciacc.org/ and here a multi-verse publication from neuroscience (E. was one of the 70 teams: https://www.nature.com/articles/s41586-020-2314-9). In particle physics they understood many years ago that the multi-lab approach is the only way to advance the field.

5. At least in bioinformatics it seems to me that people always believe they cannot use the programs/codes created by others, their own version would be better (at least 2-3 guys/girls I met), is that a field-specific attitude or is it in reality that many times the analyses for a specific biological question are just too "specific" (for the lack of a better word :D)? 
    - It occurs in other fields too. For many reasons I think. One reason can be for the sake of learning: a good way to learn a method or algorithm is to implement it yourself starting from scratch. When the programs become larger, then clearly not everyone can start from the beginning as it would take too long time.
    - Isn't is a problem for reprodicibility? I mean, using a tool as it is it's easier to cite and to refer to while creating your own version is more complicated. Moreover you should also maintain this version that takes huge effort.
    - Agreed, this could lead to problems with reproducibility. Another aspect is that codes/tools that are developed through often hard and long work might not get used that much for modeling/simulations/calculations for projects that get worked on all the way towards communicating results in a paper. Many codes are underused.

6. Slightly off topic; do you have any environments for Python you recommend working in? I currently use Jupyter Lab on Mac. (+1)
    - Personally I use VS Code, and I also like Atom. Both are general IDEs with good support for Python. (But I also think the different environments have mostly the same support, so it's a matter of learning one.)
        - Thanks. The ones I've mainly been recommended are Spyder and IDE (but i dont think IDE is available on mac)
            - IDE is just short for integrated development environment, think of a software application that helps you edit/develop your code.
    - I use the CodeRefinery Conda environment that you can find in the installation instructions. It includes Jupyter, etc.

7. This professor still knows more than most. :) Many others would just assume everything is available and not doubt there may be issues.(+2)
   - Heh, I can never read that comic the same again!


### Discussion

#### What are your experiences re-running or adjusting a script or a figure you created few months ago?
- I didn't comment it so much so it was very difficult understanding what the code was doing. It took more time than expected.
- I had several versions of the script I wanted to use again after 2 years. I didn't know which was the last version. I had to review each one. It took like 3 days (it was a nightmare)
- For some code I constantly was changing parameters and it was challenging keeping to track of which parameters generated which figure. Another reason for this was that figures took about a week to be ready, so after a week I had already forgotten about the context in which the figures were made.
- I didn't have the license for Matlab any more and had great difficulty obtaining the raw data to process the same data elsewhere. In the end I ended up editing my old figures in pdf format.
- Terrible, did not know how to make it run again. The script was contructed from other pieces of code found on stackoverflow and too difficult to understand.
- Something else changed and tests don't work anymore
- Not working, just getting lots of error messages that are hard to understand.
- I usually comment codes almost line by line and that makes reuse easy. But my problem is usually with a lot of files to handle. I had problems finding a certain simulation result of so because of a large quantity of files to deal with.



#### Have you continued working from a previous student's script/code/plot/notebook? What were the biggest challenges?
- Understanding what they meant and why they did certain steps in the analysis - this was mostly about the code. 
- The student took a long time to hand over every script because she had to "clean them up" before sending them to me.
- share experience in a constructive manner
- I tried to reuse a Python package from 10 years ago, it took almost one day to find the right versions of the packages so that the main example worked
- I had code from a supervisor, it was commented well but they didn't want to explain anything about it. If I asked what is this parameter x that you named in this way they would say shortly 'yea just the parameter x'... well that didn't explain it to me. Still I'm getting questions from them how is this parameter x managed in the code, did you do some quality check for it? But to this day I didn't get explanation what is it so no, I didn't get that QC done on that part... Also the same supervisor wanted me to develop the code further, but at the same time they would want me to not alter the original code ???
- Knowing where to start trying running the code.
- Next to impossible :(
- Missing the proper small tests to cover some basic functions. Hard to run whole program at the beginning
- The main problem for me was to understand where the output data were saved and changed the path directory of them. I do believe is what you said. The problem is the less communication between people and not coding. Without any information about what the data is about, how the person before us or even when we did the work few years ago, it is important to be provided with information.
- very difficult code to read, I had to test every line separately to see what it does. Took forever and found lots of bugs.


### Questions (continued)

8. In each sub-folder there should be a different `.git` repository? Or one `.git` repository for the entire project?
   - One git repository per project is the best approach. If a project is big, then subprojects can have their own repository. If you think of academic publications, one project corresponds to one publication.

9. Are there standard files that should be in `.gitignore`?
   - Depends on what content that goes in the git repo. For a git repo with source code, one typically lists in the `.gitignore` object files and executables that are generated by the compiler. For e.g. Fortran one would like to have `*.mod`, `*.o` in the `.gitignore`. 

10. Do you know of any version control for HARDWARE developments? (e.g, CAD or PCB designs)
    - If the development is done using text, git works.
    - Git is also fine with small non-text files, but it creates copies whenever they are changed. Essentially any version control will do that, though. You need a copy for each version.
        - Thanks!

11. Are there other resources one can use to share data that is too big to be shared on GitHub? 
    - Depends on what kind of data you have since there are a lot of laws now in Europe about GDPR and/or sensitive data, but you could use Dropbox in case your data doesn't need to conform to that.
    - Addition by Elisa (data steward at the VU): we don't recommend using Dropbox. Dropbox is a commercial company that can decide to cease operations, resulting in you losing your data. If you use Google Drive the risk is slightly lower if you use your institutional account, but still, Google could also decide to cease operations. Zenodo (mentioned below) is indeed a better option. That is, if data aren't sensitive, GDPR- or otherwise.
    - If it's a temporary sharing, and the data are not sensitive, you can use some of the popular tools that you most likely have access to at your organisation (Google Drive, Microsoft OneDrive, etc). If the sharing is instead more "permanent" (sharing with the world and preserving the dataset for a long time), you want to version the data release and use a data repository like Zenodo.org. Search if in your field there are dedicated repositories for data sharing https://www.re3data.org/


12. The files that we do not want to track should we then put them in the ./gitignore folder ? 
    - The `.gitignore` is a text file. There you can specify the types of files you do not want to be tracked by git (e.g. `*.zip`).


### Discussion

#### Are you using version control for academic papers?
- For code, yes. For manuscript, no. The idea of combining manuscript preparation to git is worth of consideration. One issue has been the size of Git repo. Using gitignore is a good idea. However, I am not sure that we should push everything to git version control. Do you have first-hand experience with MS and Figures, data etc?
- Not yet, but maybe after this course :) (+10)
- For code I use GitHub and for manuscripts I use Overleaf without git.
- I am trying, just started with github. I've been using overleaf previously
- I would really want to know what are the possible solutions available?
- Git and github integration for overleaf (+1)
- Using Overleaf but not with git (yet) 
- Yes but only with onedrive (+1)
- Yes,  use visual stuyi code to write the text in Latex, and use Git for the version control.o 
- Word documents with different dates in the file name :D (I know, bad and sad, but never knew of a really better version, also depends on the PI you're/I am working with)
    - Don't be ashamed of using the nice GUI of Word!
    - Track changes in word are also functioning well - so no shame there.

#### How do you handle collaborative issues e.g. conflicting changes?
- Communication is key. Like give a heads up before starting a new branch and talk beforehand about upcoming changes.
- Word with "track changes", email, coauthors append initials to filename, first author gets the merge headache :)

#### What tools are you using when organizing your projects?
- MS365 (+1)
- VS Code (+5)
- Passive Agrression (+1 :P)
- Emacs
- PyCharm
- cryptic file names (+1 lol)xD
- manual UMD diagram
- File explorer in windows? ;)
- Azure DevOps with git



### Questions (continued)

13. How to use overleaf with git? I don't use it although use overleaf a lot. Would be nice to know about this.
    - Git is used internally within Overleaf. My personal experience of using the git API of Overleaf is mixed. Things might get confused if some authors are editing directly on Overleaf, whereas others are adding material over the gitAPI.
        - The versioning may be a premium feature, I am not sure what is available for free.
    - handy links:
        - https://www.overleaf.com/learn/how-to/Using_Git_and_GitHub#.V7NMWLNnthE
        - https://www.overleaf.com/articles/git-and-overleaf-integration/qmdncpnqwfxx
          - thanks! 

14. This is actually a question about last week's exercise. For the forking exercise, it said to wait for someone to accept my merge before starting the second part. However, my merge request is yet to be approved.
    - That's our own fault for not being on top of things.  Pull requests don't make people magically interactive, you do need to talk and make sure someone will accept!
        - I do apologise. I am joining this session online, hence I did not know who to contact. Could I ask you to approve #32 in forking-workflow-exercise?
            - No need to appologize, we were too slow. It's accepted now.

15. I'm very happy to see someone else use cooking anologies! I always do this when running python undergrad courses (coding language = robot chef, data = ingredients, code/script = instructions) 
    - We used the cooking multi-chef / multi-pot metaphores to teach parallel computing last summer :) [1.2 What is parallel computing? An analogy with cooking.](https://www.youtube.com/watch?v=w12iCBUGYJ4&list=PLZLVmS9rf3nOmS1XIWTB0Iu7Amvf79r-f&index=3)
       - ah fun! more to come. I (RB) have the ambition to write a blog post about cooking analogies for everything computing related": parallelization, scheduling, resource use, SIMD, ...

16. If you use code snippets posted online by others, say in stack overflow etc, do you need to cite them? Always feel slightly guilty just using them, but then again my coding journey just began and nothing was published yet (not even close).
    - We'll actually talk about this in the second lesson of today!  Make sure to raise this question again if it's not answered.

17. Would like to hear a bit about where things "live" when using Conda. Like what happens under the hood, how do channels work?
    - Good question but might take a while to answer.  Let's see: "channels" are basically a way to organize groups of packages by a single group.  There is a default anaconda channel, but it also allows others to package and distribute what they need.  You can select a particular channel when you install packages with `conda`.

18. Probably you're going to treat this, but what is the difference between `Conda` and `Anaconda`?
    - `conda` is a packaging program. You use it for installing packages and creating program environments. Anaconda is the name of a set of packages. You also have miniconda which is a name of a set of packages. Anaconda is huge as it is a lot of packages. Miniconda is the bare minimum of packages needed for having a python environment.
        - thanks!

19. In `R` I am using the `renv` package (https://rstudio.github.io/renv/articles/renv.html) to deal with package versions. Is this a good approach? 
    - yes! :-)
        - Thx :)

20. If one wants to publish your work when coding in python, PyPI is a common choice. How do one accomplish this with conda? Is it possible, or is conda-forge and other channels the only option?
    - Conda-forge is the most common. There are other sources that specialize on different fields or different types of packages.
    - The instructions for conda-forge https://conda-forge.org/docs/maintainer/adding_pkgs.html
    - So, is there a motivation for ever using conda and publish to conda-forge, rather than virtualenv and publish to PyPI?
      - Both conda-forge and PyPI are viable options for distributing the code. Publishing to both might increase the uptake of the tool.

21. Is Spyder another package that can be used?
     - It's an editor that can do a lot of the similar things, yes.

22. Is there a good way for me not to have to remember which environmnt I made for which project. Something like `conda activate .`?
    - I name the environment and the project folder the same. Not perfect but helps 👍 
    - You can add the environment to the current folder: `conda create --prefix`.

23. What is `.yml` and why are enviroments written down in this format?
     - It's a format for textual data. It's meant to be machine readable and easy enough for humans to read and write.
     - And it is good to keep the name and format since this is now recognized by a number of tools (e.g. Binder, later ...)

24. R. said "I prefer having isolated environments instead of having it installed on my computer." I dont get the exact difference. Arent the things installed even if you use an environment, but the isolated environment just helps "list" exactly what you need and where they are?
     - If the environment is isolated, it is easier to remove it without affecting everything else on your computer. So they are still installed but often installed into a folder of your choice instead of installed "somewhere" where it's harder to remove.

25. It has been commented that it is recomended to have one environment per project, but when doing this it seemed to me that it takes a lot of space on my hard disc (few Gb space). Is this a know effect, or I didn´t perceive it properly?
     - Conda should reuse packages already installed in a different environment. It can create copies, though, when two environments use a different version. You can save space by using the same (latest?) version in different projects.
         - good to know, thank you!
     - The conda cache can take up a lot of space. `conda clean --all` will remove unused packages and other data.
         - Cool, thank you!

26. I am not sure I understood what is an environment. Would you mind explaining again?
     - In this context, a way to install outside libraries without needing to install them on your whole computer.  It lets projects not interfere with each other, you don't get your computer messy, and can do it without admin access to the computer.

27. Does anyone have experience with JULIA? i have been considering using it as it is supposedly excellent for analysis on large quantities of data
     - Julia tracks dependencies in the package lock file (sorry I forgot exact name) but tracking dependencies and communicating them is relatively easy in Julia and it is well designed.

28. When is the best time to generate this `yml` file? At the end of the project? or regularly at each major releases?
     - I would do it as soon as possible.  And incrementally as you add things, so you keep track of what is needed.
     - If environment gets messed up, you can re-create it.  Re-creating = ensures it's reproducible later!
         - Then, what is the difference of generating this yml file and generating requirements.txt using pip freeze? (I just realized that pip freeze only works for python venv)
             - If you're working with conda environments, the default is to store dependencis in a file called `environment.yml`. If you work in a python virtual environment, the default is `requirements.txt`.
                 - silly question, what is the Conda environment / Python virtual environment?
                     - `conda` and `pip` are both package managers for Python. They can both be used to create environments in order to isolate your code from the rest of the system and keep track of dependencies.
                         - Thanks!

29. What is the best approach to data sharing/version control if you are the only one in the team using it and writing scripts?..
     - I would use git and commit everything/push everything directly
     - But day 6 will show "automated testing", which would show some benefit of pull requests even for one person.
     - I find it useful to imagine: "what if my computer breaks today completely?" - what steps will I need to take to get this to run again. then I write down these steps and put this all somewhere safe outside of my computer. that already will go a long way towards reproducibility.


### Exercises until xx:10, then break until xx:20

**How was the exercise?**
* it worked: oo
* didn't work: 
* needed more time:
* didn't try:
* too much time: 
* didn't realize today started an hour earlier than last week :\ (Daylight Savings?)
* Central Europe changed to summer time last weekend.

30. Do we need to do the installation of dependencies for the exercise?
     - For Dependencies-1 you don't need any coding or installation of dependencies.
     - For Dependencies-2 you need the CodeRefinery Conda environment (or your own env)
        - but even only "reading" Dependencies-2 is hopefully useful. The `conda env export` will create a file similar to the one we see in Dependencies-1 

31. What is a `channel` in relation to Conda, envs, etc.?
     - these are different distribution channels: places where packages are shared.
         - when building, e.g. a Docker container, how do I know about `channels`: which one to use, where to get info about available ones?
           - When preparing a Docker container you could add channels e.g. conda-forge, similarly to how you work with conda and channels in a terminal.

32. I am not sure how to start the exercise. What exactly do I need to do?
     - No coding needed for part 1. the goal for exercise 1 is to read A-E and discuss/consider how this affects reuse in future
     - For part 2: if you are in the activated coderefinery conda environment, I would try to export that environment into a file
       - "A: You find a couple of library imports across the code but that’s it." how would I find the libraries?
          - in Python it would be that you find somewhere for instance "import scipy" or "import somelibrary"
        - what is the coderefinery conda environment? Where can i find it?
        - https://coderefinery.github.io/installation/conda-environment/

33. When in a project is it appropriate to create an `enviroment.yml`? at the start? at version 1? and when should it be updated?
    - I would create it at the start and add packages to it as needed. (Also periodically delete the environment and reinstall.)
        - Why would it be good practice to delete it periodically?
    - I like to write the dependencies in there and install from the file. This way it is already documented and I never install anything that I did not document.
        - (like the sound of this approach)

34. How and when does one decide to create a new environment? It becomes a bit tricky to me that people work on different projects and sometimes even hard to have a well-defined "project". What would be a good advice for that?
    - I would create a new environment when I start working on a new code repository. I have 1 or more environments per repository.
    - Also any data repository can have it's own environment. I probably would create one for a paper as well, but it could be shared between data and paper.
    
35. In the "Dependencies-1" example, should we not specify the python version (e.g. 3.5 or 3.7)?
     - good point! it could definitiely be relevant and can/should be added to `environment.yml` (however, `requirements.txt` has no mechanism for that as far as I know)

36. what is the "CodeRefinery conda environment"?
    - It is an environment that contains the programs used within this workshop.
    - https://coderefinery.github.io/installation/conda-environment/
        - sorry, we should add a link to it from lesson
            - I get:
            ```bash
            G:\>conda activate
            'conda' is not recognized as an internal or external command, operable program or batch file.
            ```
            - What should I do?
                - Is there an "anaconda terminal" of similar in the start menu?
                    - Yes, should I start from there? It is difficult to understand from which terminal a person needs to run from. There is the cmd, the anaconda one, the git bash etc...
                    - How do I "activate" this coderefinery conda environment?
                        - `conda activate coderefinery` 
                            - How do i know in which environment i was in? Maybe it was already activated?
                                - Conda usually adds the environment name in parenthesis to the terminal. For example `(coderefinery) $`
                                    - Ah yes, I see now. Thanks!

37. Would the conda environment be operating system agnostic?
    - In theory yes, if the packages work across different OSs.
    - An `environment.yml` can be made with "build numbers", the `=hcf16a7b_0_cpython` you see in a question below.  These identify specific builds, and aren't portable across different OSs.  So `conda env export --no-builds` excludes it and makes it a bit more portable.
    - But you would need to re-build it to install packakges built for each OS.
        - Thanks! Fellowing that, is, for example, Python 3.11 in Linux works and is built the same in different OSs (under the hood)? So when I port and re-build Python 3.11 from Mac to Windows, will there be problems?


38. When I try the exercise 2 the first command, I recieved this message:
     ```bash
     out-file : Access to the path 'C:\environment.yml' is denied.
     At line:1 char:1
     + conda env export > environment.yml
     + ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
         + CategoryInfo          : OpenError: (:) [Out-File], UnauthorizedAccessException
         + FullyQualifiedErrorId :  FileOpenFailure,Microsoft.PowerShell.Commands.OutFileCommand
     ```
    I already have the coderefinery in conda environment
    - I guess you need to move to a directory where you are allowed to make a new file.  C:\ isn't allowed for your user
    -Okay it makes sense why I am struggle, but what do you mean to move directory? I am in the coderefinery directory, but unfortunately I can not avoid the C:>
   

39. I checked the files from last week. At the end of the directory name there is info like (older code), (master), (just-before). I guess it is git that writes this, but it was very unexpected. What kind of help is that and how do I use it?
    - It's a "git-aware prompt", where the shell prompt has some info on git's status and current branch.  This happened on your computer by default?
    - Yes. I did not see it last week. It just came up now.

40. What does the text after the second =-sign mean: `python=3.11.0=hcf16a7b_0_cpython`
    - Exact hash (`h`) and build.  More specific exact identifier than version.  Note this changes on win/mac/linux, so makes it more reproducible on one computer but not portable to others
        - Thank you!

41. I am receiving a `conda: command not found error`. I tried adding the conda path to PATH but nothing changed. I even initialized conda.exe in the shell and restarted.
    - Which operating system are you on. And what terminal?
    - If you use `export PATH=$PATH:...`, that's only for the current terminal. If you restart the terminal, you need to do it again.
      - If you are on bash, you can add the export command to the ".bashrc" file. 
    I am using WSL (windows subsystem for Linux)
     - Then it's probably bash. How did you install conda? If you install it using the normal windows installer, WSL will not know about it.
     - Is there a link I should follow?
     - Check https://kontext.tech/article/1064/install-miniconda-and-anaconda-on-wsl-2-or-linux.
     - Or run `apt-get update; apt-get install wget`
     - and `wget https://repo.anaconda.com/miniconda/Miniconda3-py39_4.12.0-Linux-x86_64.sh
     - now running `sh ./Miniconda3-py39_4.12.0-Linux-x86_64.sh` should install MiniConda


42. How does Conda know where to get info to perform `conda activate <env_name>`? Is info about these environments stored somewhere?
     - yes, on my computer it keeps a list of all environments in .conda on my home folder
         - I'm on Ubuntu, found ~/.conda dir as well after I typed `conda env export > environment.yml`. But where does `coderefinery` env come from, which is activated magically by `conda activate coderefinery`?
           - The name of an environment can be specified in the `environment.yml` file, for instance `name: coderefinery`.

43. So I can see I have the coderefinery environment under my Miniconda/envs folder and I see it when I do `conda info -e`. I have put my current environment info a `myownenvironment.yml` file. But what has to happen to` `myownenvironment.yml` so it behaves like the coderefinery environment I can see in my envs folder and so it lists like an available environment I can load?
    - Oh, wait I might have found it. Its the next part of the exercise (facepalm...)

44. It is difficult to understand from which terminal a person needs to run from. There is the `cmd``, the anaconda` one, the `git bash` etc... Should I start with the anaconda terminal?
    - I recommend to always start from Git Bash on Windows in this workshop (then also the Git part will work)
    - `$conda activate bash: conda: command not found.` As you can see with git bash it is not working.

45. The "Setting path to Conda from your terminal shell" is not working. I do the command "echo ". '${PWD}'/conda.sh" >> ~/.bashrc" and when I try conda --version it does not find anything. I remember there was a problem also during the install sessions. Please let me know what to do. with windows
    - Sorry, this is hard to debug without direct directly seeing your terminal...
    - Did you restart the terminal after adding to .bashrc?
        - yes I restarted. I was in the installing session and they told
    - Can you run `echo $PATH` and paste the results?
        - do I need to print here?
        -Yes, please
        ```
        $ echo $PATH
        /z//bin:/mingw64/bin:/usr/local/bin:/usr/bin:/bin:/mingw64/bin:/usr/bin:/z/bin:/c/Program Files/Python311/Scripts:/c/Program Files/Python311:/c/WINDOWS/system32:/c/WINDOWS:/c/WINDOWS/System32/Wbem:/c/WINDOWS/System32/WindowsPowerShell/v1.0:/c/WINDOWS/System32/OpenSSH:/c/Program Files/dotnet:/cmd:/c/Program Files/MATLAB/R2022b/runtime/win64:/c/Program Files/MATLAB/R2022b/bin:/c/Users/user/AppData/Local/Microsoft/WindowsApps:/usr/bin/vendor_perl:/usr/bin/core_perl
        ```
    - Seems that conda is just not there... Can you paste the last few rows from the .bashrc file (`tail ~/.bashrc`)? 
     ```
     tail ~/.bashrc
    . '/z/'/conda.sh
    . '/c/Hyapp/Anaconda3-2022.05/etc/profile.d'/conda.sh
    . '/c/LocalData/bortolus/coderefinery'/conda.sh
    . '/c/Hyapp/Anaconda3-2022.05/etc/profile.d'/conda.sh
    . '/c/Hyapp/Anaconda3-2022.05/etc/profile.d'/conda.sh
    . '/c/Hyapp/Anaconda3-2022.05/etc/profile.d'/conda.sh
    . '/c/Hyapp/Anaconda3-2022.05/etc/profile.d'/conda.sh
    . '/c/Hyapp/Anaconda3-2022.05/etc'/conda.sh
    ```
    - There is something wrong with the echo command  you ran. Those lines are not correct, and they might even break the .bashrc file.
        - yes I remember there was a problem also during the installation session... I copied the lines from the prerequisite page 
    - The issue is it was run from the wrong folder. The instructions at https://coderefinery.github.io/installation/conda/ ask you to find the miniconda3 installation folder, and then tell you how to find a folder with a file called conda.sh. You should open a GitBash from there and run the command. You should also edit the .bashrc file and delete the extra lines.
        - that's what I did. though not in miniconda, but in anaconda. 
    - The path that was added to the .bashrc-file on the first time was /z/..., which is not correct. Mayve the "/c/Hyapp/Anaconda3-2022.05/etc/profile.d..." is correct.
        - where do I find the .bashrc file?
          - start GitBash from the start menu and run `pwd`. That should print the path to you home folder, where the .bashrc file is.
          - it's in /z/ but I can't change in C:
              - Sorry, I don't understand the line above.
    - so I have anaconda in /c/ but when I open gitbash and run pwd I am in /z/ disk
       - When you open gitbash, you will start in your home folder. That is the one you want, for now. It's where the .bashrc file is. You can open it in a text editor (if you know the name of the .exe file for the editor, type `editor.exe .bashrc`). Or you can open the folder using `explorer .` and go from there.
    - Unfortunately I need to go to a meeting, but I will ask if someone can follow up.
    - But, if you can open explorer (see above) in your gitbash home, edit the .bashrc file. In the end there are a bunch of lines starting with ". '". Delete them and add one line:
      ``` . '/c/u/Anaconda3-2022.05/etc/profile.d'/conda.sh ```     
    - :'( ok thank you for the help
    - **still not working**
       - reading the above ... also for rest of today it is not a big problem that this does not work (rest of exercises will be discussion) but we should try to get this running for tomorrow
    -this was working during the installation session. I'm sure there is a easy way to fix it


46. When uploading my `.yml` file to a public repository, would it be better to not include the hash and build for portability to other operating systems? (+1)
    - Including the hash makes it less portable, since that exact version may exist only for a given operating system. I prefer less exact versions, because that may allow it to work on other systems.
    - But even with the hashes it is useful since they are relatively easy to remove for the person who comes 3 years later. But for a project in progress it is indeed easier not to have too precise/restrictive versions. 

47. If I run the command `pip freeze` while being in the miniconda prompt. I see text that looks like `certifi @ file:///C:/b/abs_85o_6fm0se/croot/certifi_1671487778835/work/certifi`. What is the meaning of the @file and other things, while it does not specify the versions. 


48. In the anaconda and miniconda I am at C:\>, but I do not know how to move to a directory as someone said before, can you clarify? I use anaconda in windows.
    - Most likely your "home" folder is under the folder Users. So start with `cd Users`, and then `ls` (or `dir`) to see the subfolders there. There should be one which is you username.


49. "(coderefinery) C:\>conda env export > environment.yml
    Access is denied." What this means? What should i do?
    - I think you are in a directory where a environment.yml file can't be made, since you don't have permissions to write there.  `C:\`
    - how can I change the directory?
        - With the command `cd`.

50. Is there some way you can see the previous version of the environments excercise? i liked it better before. :/ I remember there was one awesome excercise where you could try out a bunch of different commands with conda where you kind of put stuff into a yml file, and then creating a new environment from that but then changing it slightly and so forth. 
    - With the power of git, we can!  Easy to see the raw source (for example) here: https://github.com/coderefinery/reproducible-research/blob/2fc3f7cb0a2e03c79ca7420358eecaf9517b0b5f/content/dependencies.md


51. How do I get the current environment? According to this: https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#determining-your-current-environment it should show an asterix, but if I run `conda env list` in Git Bash i don't get an asterix.
    - Weird... I wonder if there could be none activated now...?
        - after i activite the coderefinery environment it is clearly activated (checked by exporting environment.yml), but the asterix isn't shown
        - try `conda info` it tells you various details on the current activated environments (or if nothing is activated)
        - Thanks, that works!

52. I have made the script.sh and put in the repository. I run it using bash script.sh. But there is no output. Shouldnt i see a plot? Should i putpt in data folder? 
    - It saves straight to the data folder and is quiet otherwise.
    - it does not print any progress but generates the data files and images
        - Where can i find these images? In data folder it does not appear. 
          - Try plot/ folder next to the data/ folder
              - Ah yes, thanks!

53. Is Snakemake similar to C makefiles?
    - Yes!  Well, in concept.  That's where the name comes from at least.  (Makefiles run shell commands so can be used for any language)
    - it is the same idea but 40 years later so more nice features

54. I'm getting an error with conda:
"CommandNotFoundError: Your shell has not been properly configured to use 'conda activate'. To initialize your shell, run $ conda init <SHELL_NAME>"
    - Is this on your own computer where you installed conda itself?
    - yes. noramlly i use zsh shell, which i have my own environments that i use and works fine. ive been using bash for this course, so maybe that's a point of issue?
    - Yes, probably.  If you `conda init` in zsh it might work if you restart the shell.  Or go back to zsh, if you know it it will work (you can still `bash script.sh` from zsh)
        - okay. can `conda init bash` outputs `No action taken`, so i will work through zsh instead. Thanks for the help!

55. When I try running  bash script.sh I get "No such file or directory" error. I have cloned the repository and cd to word-count folder
    - I think you need to make the file `script.sh` from the webpage.  Copy and paste into `script.sh` using an editor.
    - yes, I forgot to add that script to the repo
        - Sorry, I am lost. From what webpage?
    - https://coderefinery.github.io/reproducible-research/workflow-management/#exercise - Under Workflow-1, it shows a script starting in `#!/usr/bin/env bash`.  This should be copied to `script.sh`
        - But I do not have the 'script.sh' file, should I create it first?

56. I did the first exercise easily, but the snakemake exercise doesn't work - or probably i am doing something wrong. I tried to run the lines of code written in step 3. while using git bash inside the "word-count" repository on my pc. It says: "bash: snakemake: command not found". 
    - It seems to me that the conda enviornment is not active, thus it cannot find the `snakemake` command.
        - I think you're right, i didn't install the conda part but kept the updated version of anaconda i already had - as it was started in your installation guides that it should be fine as well, but that you would only recommend conda instead. 
            - Indeed snakemake comes with Anaconda. 
                - How do i activate it with my own anaconda environement then? :) (The first exercise worked without trouble - that used python as well..)
                    - First run `source [PATH TO CONDA]/bin/activate`.
                        - nvm. condabin is the name, trying again.
                            - Maybe close this terminal / git bash, open a new one, and then `source [PATH_TO_CONDA]/bin/activate`. Then try `snakemake --version` just to check that it finds it.
                                - I solved it myself by looking back at some of the installation guides - it was working as it should, but i needed an extra command (almost the one you mentioned): "source activate [PATH to Anaconda3]/envs/coderefinery". Thanks for getting me on the right track for a solution for this.
                                    - Glad that you made it work.

57. I saved the script bash file, but when trying to run i get "script.sh: line 5: statistics/abyss.data: No such file or directory", followed by other "No such file or directory errors" regarding paths ending with plot.py
    - What directory did you save it to?
            - I'm guessing to wherever I am :D coderefinery???
    - I think you need to do it from the repository you cloned.  If you `ls` or `dir` there should be a `data` and `statistics` directory there.
    - Sorry, I forgot how to go to the cloned repo. Do I use the cd command for that?
        - correct.
    - Thanks!
    
58. To create the script.sh file we need to do it from the terminal on Binder, correct? If so, I couldn't use nano, vim or vi there. So how to?
    - Yes. Or some other editor.
        - That must be on Binder? Or can I do it on my folder that I cloned?
        - Which text editor exists on the terminal inside binder that I can use? I know nano, vim and vi. None of them work, so how can I create the script.sh file?
           - You can install an editor of choice within the container.

59. I created and ran the script.sh. Now i do git status and i only see the script.sh that is untracked. Why are the plots that i created with the script not there as untracked? They have not been changed?
    - If you did not delete the plots before starting (the repo included them already – maybe that was not mentioned in the script exercise) then the script produces exactly same figures and git considers them unchanged

60. Am I correct in that Snakemake is completely language independent, and works as long as you can run every step from the command line?
    - Correct.  (though it has some extra Python integration)
        - What is this additional Python integration? :) 

61. In my current project, I use a mix of Fortran and Python codes, which for example does not run on notebooks and requires a specific environment to be executed. Is it possible to save an environment in git and let the user install it in a one-line procedure? This would be useful even for myself when running from other machines.
    - The `environment.yml` thing we discussed in theory does this.  Make a `environment.yml` file that has the requirements.  In theory a user can `conda env create -f environment.yml`.  Or similar ideas for other tools.
        - Thanks! I do not have much knowledge of that, but could I do something similar to other terminal instances like C, R, Fortran versions?


62. After trying all the installations process, `conda -- version` on git bash gives me `command not found`. Not sure what to do now
    - I guess conda isn't activated... 
    - Are you working with the coderefinery environment or anaconda without the CR env?
        - From anaconda terminal I activated the code refinery environment, then I tried to "conda env export > environment.yml" and it tells me that it cannot be done. so i started trying with git bash and i have tried to make it work in bash and it still tells me command not found!

63. Snakefile and it's working looks cool but I am wondering how to write one. It looks complicated (I mean what are these? shell commands?)
    - they have very nice tutorials. but also it's not the only tool that works this way (see lower on that page) and maybe others look more intuitive. our goal is that you now know that tools like this exist where you can encode steps.
        - Yeah great, thanks
          - and it does not have to be shell commands. it can run basically "anything": shell, python, R, anything else 

64. Im a bit lost, I tried to clone the repository and after that I do the `snakemake --delete-all-output -j 1`, but  error comes like this: Error: no Snakefile found, tried Snakefile, snakefile, workflow/Snakefile, workflow/snakefile. (coderefinery). It can be that I just need to follow today and see these exercises later, but if there is some help that I could catch up with now, would be great.
      - after the cloning did you `cd` into the cloned directory? is Snakefile in the same directory where you run the command?
         - ah right, thanks! I didn't
     
65. It is still solving the environment for coderefinery env, haven't been able to do anything more than that.
      - it takes time to install for the first time but no problem for rest of today. We will need it tomorrow. Test of today will be discussions.

66. Can I open the generated images in the terminal?
    - There are some tools for that but most of them are OS specific.

67. why snake file created empty txt files in plot folder with name of book titles?

68. How do we create a good "README" for a snakemake file?
    - Hm. I guess you would comment on what commands to run and what the setup is: can run with snakemake.  Put input files in this place with this format. Run this command, and output appears [here].

69. IG_question! I do `git status` --> `snakemake --delete-all-output` --> `git status` --> `snakemake -j 1` --> `git status`. Why do the 1st & the last calls of `git status` tell there are no changes in the repo? Files were at least updated (actually, removed & created again, and `git` noticed this). `git` doesn't track time evolution of a file in repo if there are no changes in the file size / content?
    - If there are no changes to the content, it is considered the same.
        - Let me clarify, if only 1 symbol is different, but the size of a file is the same, is it considered as a change of a content?
        - Oh, yes.  The content is the important part.  I think it uses timestamps to see what to check, but then always checks content.
    - The `.gitignore` file shows `*.log` ignored.

70. Question 56 is still unsolved.
    - we're having trouble figuring it out, if we can't by the end of the day might be good to ask someone local who can look at the screen and see the status.
    - we are puzzled by these problems. we are wondering whether it's maybe the wrong terminal open?
    - What operating system are you on?
        - (I use Windows, and writing in the git bash terminal) I solved it myself by looking back at some of the installation guides - it was working as it should, but i needed an extra command (almost the one you mentioned): "source activate [PATH to Anaconda3]/envs/coderefinery". Thanks for pointing me in the right direction with your suggestions.
            - Solved now.

71. How to edit the files inside Binder? `nano`, `vim` or `vi` doesn't work. Can you give the names of the tools that we can use to edit the `*.py` files inside Binder?
    - From the Jupyter file browser you can open and save.
        - Thanks. But I was expecting to do it through the terminal.
    - The main question is "what editors does binder install by default" and maybe the answer is "none"... in which case not much to do.

72. from anaconda terminal I activated the coderefinery environment, then I tried to "conda env export > environment.yml" and it tells me that it cannot be done. so i started trying with git bash and i have tried to make it work in bash and it still tells me command not found!
    - you tried activating the code refinery environment in git bash? `conda activate coderefinery`
      - yes, command not found again; still the same

73. If I try to visualize the DAG I get an error:
```bash
$ snakemake -j 1 --dag | dot -Tpng > dag.png
bash: dot: command not found
Building DAG of jobs...
Exception ignored in: <_io.TextIOWrapper name='<stdout>' mode='w' encoding='cp1252'>
OSError: [Errno 22] Invalid argument
```
- You are piping through `dot -Tpng`. What does the command do? Where did you find it? Anyway, the `dot` command is not installed on your computer that is why it is complaining. 
    - I copied it from here: https://coderefinery.github.io/reproducible-research/workflow-management/#visualizing-the-workflow 
        - Thanks for the link. This requires the Graphviz software, which can be installed by `conda install graphviz`). It’s not a must to run this step yourself, but you may if you install `graphviz`.
            - I installed `graphviz` but it still gives the same error. 
            - Probably this needs to be figured out later, I recommend watching for now.  It might / might not work on different operating systems...

74. The best ever joke about paper peer review was recorded in [this video](https://youtu.be/NGyf0Xg20pc). Hopefully, there are no hard feelings regarding the original movie.
    - ..

### Recording computational environments
https://coderefinery.github.io/reproducible-research/environments/

75. It sounds like the instructor was talking about what is on his screen without sharing? nvm video was stuck on my end somehow
    - Something a bit strange is going on here... but seems to work overall.

76. I was wondering if the workflow is using some tool like Binder and or depends on some integration with github, it can be unaccessible in the future, right? Is there some way to use containers, dockers that is possible to rely on in the long run? 
    - Possibly.  There are other steps to help: Binder can use things other than Github.  And the binder web service uses `repo2docker` which can also be run locally.  Binder isn't actually that fancy, it uses standard reproducibility things like `environment.yml` that you want to do anyway.  So it's even more reproducible if binder disapperad.
        - Great! So one can say that github, gitlab is not enough anymore, we should use some more advanced tool, right?


77. What's the difference between a container and an environment? The container is a next-level up?
    - Yeah, pretty much.  "container" includes a lot more of the operating system libraries, which means that there is a lot less to go wrong (but also it's a lot larger and harder to make)


### Sharing code and data
https://coderefinery.github.io/reproducible-research/sharing/

78. We are supposed to follow along? with the exercise? or just watch?
    - Just watch for now, demo.

79. is the full history of the git shown on zenodo when you link the GitHub to a zenodo?
    - No, it only saves the exact specific versions you archive. But you can archive multiple versions, for example each release.

80. Does Zenodo only work with GitHub? Or other repository platforms are also supported?
    - I think the "automatic integration" may only be Github, but it's not that much harder to upload data from any other source.

81. Can I use `git` to conduct control of basically everything between my local machine and a remote one, e.g. a supercomputer where I not only run simulations, but also store data?
    - Yes!  And sync changes on both ends.  The data should probably be managed / synced separate from your main git repo.
        - Was it mentioned last week? I'm asking, since I've been using my own bash script for synchronisation based on rsync with many rules like `--include`, `--exclude`
            - We mentioned how you can sync between a local repository and a remote repository on GitHub, we also mentioned that you can define a remote that points somewhere else, but we did not actually show how to do it. But that would be `git remote add origin URL`. Also, instead of the URL you could use a path to some other local repo to be synced with.
                - I remember about GitHub, GitLab, but I missed the remote storage/synch point. Alright, it's nice that it could be used. For some reason, I forgot about it.
            
            
82. These "Digital Object Identifiers" feel a little bit like the hashes that we've seen previously. The advantage of the DOI is that it also links to where the object is, correct?
    - Yes, somehow fully managed and searchable through a central organization.
    - Though interestingly you can search for a hash in Github which makes it somehow findable.

83. What is the difference between Zenodo and GitHub in terms of data sharing? A reference to GitHub could also be shared.
    - Zenodo promises to be more permanent than Github, and the DOIs can be cited in journal articles.  (Github could too but people know it's not permanent, so they may ask for Zenodo instead).


## Social coding
https://coderefinery.github.io/social-coding/

### Discussion

#### Question 1: Why would I want to share my scripts/code/data?

**Choose many**. Vote by adding an `o` character:

- A: Easier to find and reproduce (scientific reproducibility)
  - votes: oooooooooooooooooooooooooooooooooooooooooo

- B: More trustworthy: others can verify correctness and find and report bugs
  - votes: oooooooooooooooooooooooooooooooooo
- C: Enables others to build on top of your code
     (derivative work, provided the license allows it)
  - votes: ooooooooooooooooooooooooooooo
  
- D: Others can submit features/improvements
  - votes: oooooooooooooooooooooo

- E: Others can help fixing bugs
  - votes: oooooooooooooooooooooooooo

- F: Many tools and apps are free for open source, so no financial cost for this
     (GitHub, GitLab, Appveyor, Read the Docs)
  - votes: ooooooooooooooo

- G: Good for your CV: you can show what you have built
  - votes: ooooooooooooooooooooooooooooooo

- H: Discourages competitors. If others can't build on your work,
     they will make competing work
  - votes: oooo

- I: When publicly shared, usually we time-stamp or set a version,
     so it is easier to refer to a specific version
  - votes: ooooooooooooooo

- J: You can reuse your own code later after change of job or affiliation
  - votes: ooooooooooooooooooooooooo

- K: It encourages me to code properly from the start
  - votes: ooooOoooooooooOooooooooooooooo

- L: To show how good I am
    - votes: ooooooo

- M: The journal insists! I had this experience with *Bioinformatics* journal, they required I had my C/C++ code to be publicly available on, e.g. GitHub.
    - votes: ooo


#### Question 2: The most concerning thing for me, If I share my software now

**Choose 
- A: It will be scooped (stolen) by someone else
  - votes: oooooooooo

- B: It will expose my "ugly code"
  - votes: oooooOoooOoooooooooooooooOooooooooooooooooooooooooOoo

- C: Others may find bugs and mistakes. What if the algorithm is wrong?
  - votes: oooooooooooo

- D: I will get too many questions, I do not have time for that
  - votes:oooo

- E: Losing control over the direction of the project
  - votes: ooooooo

- F: Low quality copies will appear
  - votes: oo

- G: I won't be able to sell this later. Someone else will make money from it
  - votes: oooooo

- H: It is too early, I am just prototyping, I will write version to distribute later
  - votes: oooooooooooooooooooooooooooooO

- I: Worried about licensing and legal matters, as they are very complicated
  - votes: ooooooo ooooooooooo

- J: Do I share it in the correct way? Maybe I'm sharing it in an ugly manner which will discourage others to look into the content?
  - votes: o

#### Question 3: Why is software often treated differently from papers?

Free-form answers:
- current generation of senior people didn't get where they are by making good software (+4)
- Harder to document contribution and work (+3)
- Possible to make big money with software (+1)
- Not everybody can understand your code, is not so wide audience. The most important contribution is the results from the code
- Code is harder for most people to read than a written text (+4)
- Code easier to falsify / find problems with.
- Professors think code is good when it works once, spending time on commenting etc is a waste of time (+3)
- Many simply just copy and paste and don't acknowledge the code others developed. I guess this is because for scientific papers the authorship recognition is much more understood that of a random code someone finds on a forum. (+4)
- Maybe because software citation is still not at par with paper citations for an academic career in many fields (:+2:)
- I took parts of codes from others and feel like it is not mine. I just combine it. (+3)
- Not formally "peer-reviewed" in the same way and aren't "novel results" so hard to convince admin it should be valued as academic currency (similar with methods papers being less valued even though long-term contribution may be huge) (+1)
- Code is a tool, raher then a scientific finding. It has no scientific value by itself. Rather belongs to the Methods section of a paper
    - why aren't methods valued in themselves? without good reproducible methods, science would be much slower and worse
        - That is true - but that goes for all methods, experimental techniques, data collection etc. 
            - methods and data papers are becoming more common, but are still not always valued in promotion/hiring decisions
                - I would disagree a bit on that - but i suppose that it is very regional. Addon: The methods/data collection etc. needs to be put into use/context somehow, showing the scientific mind at work, which i suppose is the reason why this is valued higher, as that often implies you have done both (collecting data/using methods and evaluated your results/discussed the scientific relevance of it) and not only collected the data. 
                    - I think usually when people write a detailed methods or data paper, it's an accompaniment to a research article that provides *more* detail to facilitate open science/reuse. I think that should be incentivized/valued more than it often is (but yes, very institution-dependent). Of course not all articles justify full complementary papers - but if a method is very novel, it may warrant its own treatment. Already common in stats.
                        - agree to some extend, but personally my methods/experimental work basically "just" resulted in a very long supplementary information (40+ pages due to figures) for the "actual" article. With novel methods it is of course another story completely and will also be valued more i would assume. 
- people dont like to read code/are not interested in the implementation/assume if it runs it is correct.

- What about the ChatGPT concern? Already heard a handful of issues from developers that codes were supposedly private but still "somehow" captured by it. (+2)
    - Just actually found the option RAIL licence in today's material, might be a solution for addressing this concern?


#### Question 4: When you find a repository with code/library you would like to reuse, what are the things you look at to decide whether you use it?


Free-form answers:
- quality (+2)
- Requirements (+2)
- Can I use it on a supercomputer
- Language (e.g. python, C++) (+1)
- Licence (+9)
- This is my concern on using other's code. If I use this code, I commit to it and implementing another one will be hard in the future. I've difficulty determining the quality (+1)
- Is there a good documentation (+1) (+6)
  - that makes it look like they *want* it to be used.
- Completeness: data and code (+1)
- Latest update (if it has been recently updated) (+4)
- Does it seem like it's in active development, is there a (small) community around the project? (+2)
- Can I verify the results in some other way, e.g. by a self-written implementation (which is not efficient but does exactly what I want)?
- Amount of activity in the repo (commits, developers, issues etc.)


### Licensing
https://coderefinery.github.io/social-coding/licensing/

### Discussion

#### Question 5: Which of these are derivative works?

**Choose many**. Vote by adding an `o` character:

- A. Download some code from a website and add on to it
  - votes: ooooooooooooooooooooooooooo

- B. Download some code and use one of the functions in your code
  - votes: oooooooooooooooooo 

- C. Changing code you got from somewhere
  - votes: oooooooooooooooooooo

- D. Extending code you got from somewhere
  - votes: oooooooooooooooooooooooooo

- E. Completely rewriting code you got from somewhere
  - votes: oooooo

- F. Rewriting code to a different programming language
  - votes: ooooooooooooooo

- G. Linking to libraries (static or dynamic), plug-ins, and drivers
  - votes: oooo 

- H. Clean room design (somebody explains you the code but you have never seen it)
  - votes: o 

- I. You read a paper, understand algorithm, write own code
  - votes: oooooo 

- J. What was the meaning of derivative works?
    - votes: looolo
    - a lot of these depend on degree
    - A lot depends on the degree and also how "generic" the parts in the original code is e.g. importing data from a file (everybody does that), but when connected in a specific way to other code the story changes. 


### Questions (continued)

84. What about a script that I made that is pieces of code that i found randomly online. Can I license it?
    - Let's raise this on stream! ("practical recommendations")
    - Can you show it as an example? the stackoverflow citation


85. Which entity sets the legal rules for licensing? We must be able this is more or less globally adhered to. 
    - Basically, governments who decide what use they are willing to use their power to stop.  Which become rules for what you can't do and rules for how to give permission to do that.  (and since laws move slowly, plenty of court fights for this)

86. Speaking of license and copyright and AI image generators. Please realise that AI image generators violate the copyrights of artists. Many artists have not agreed with the AIs training upon their work to the point that AI users can emulate the work of the original artist quite accurately. That is a big problem. 
    - That is always a possibility for anything you upload online.
    - that is not an argument to leave artists completely unprotected in this regard - compare with the music industry.
    - Music is copyrighted, yet people still torrent it. (Or use adblockers.)
    - That's the point. Music is protected with strict rules against AIs training on it, drawings are not. Visual art is free game.
    - Couldn't a music AI just scrape audio from e.g. YouTube? There's copyrighted stuff there.
    - Possibly- that's why there are serious concerns with AI scraping everything without regulation. 
    - I suppose this is an ideological thing as well: How much does one agree with the existence of copyright in the first place? But that's a bit off topic.
    - Yeah we should have more tools for artists to decide whether to allow the use of their work in training AI:s. Me personally I would allow the use of my music but maybe not all.
    - Agreed - I as a visual artist do not allow it yet I have no control over it and am forced to remove my art from the internet in that case. 
    - There are ethical concerns about AI training materials, but it's not clear/decided yet if it violates copyright. Court cases are coming and decisions may be different in different regions. "Style" is not copyrightable (and shouldn't be - copyrighting "style" would be a disaster for artists)
    - To me there is a big difference between another artist being inspired (who has learned how to draw) versus an ai scraping and people who cannot draw  running away with images that seem to be created by said artist whose work has been scraped. That is disrespectful to the artist to say the least. 
        - Yes, but that's an ethical stance - ethics and legality are related but not the same, and it's not always possible or desirable to legislate ethics. If "style" becomes copyrightable, entire genres of art are in danger. So I would hesitate to confidently declare that AI training violates copyright while these issues are still legally undecided - calling it "unethical," sure. (Although personally, I think the AI images generally only look like actual artists' work if viewed in tiny thumbnails where it's mostly a color impression - the quality as art is usually... not good)

87. Are there licenses that claim that linking to libraries constitute derivative work of the linked code? Is it generally safe to assume that linking to libraries is safe for your code's license?
    - Good question and may be beyond us answering.  The GPL license says that linking can be a derivative work, if what you make is very closely connected to the thing you are linking to (has the API guided what you make?).  You are probably too small to worry too much, but worth thinking about if you use GPL libraries.

88. What does it mean, if I write Copyright 2023? How important is it to include a year. Under which conditions should I update the year/year range?
    - What you declare (unless you say it's licensed) doesn't matter, still copyrighted. Having an accurate notice would help if you ever wanted to bring action against someone using your stuff... thus why large companies care so much about this.

89. So If I use the algorithm from a paper and i write a code about it, can I have problems with copyrights? (+1)  
    - No (which means yes, you can re-write it).  At least that's the line.  You can find many re-implementations because of this. (if algorithm was patented, which is rare, then it would matter).

90. What is copyleft?
    - Term invented for "opposite of copyright": if you use my code you *have* to license whatever else you make under the same license.  To keep derivatives free.
    - legal jujitsu - using the copyright system against itself (in a way) - invented by people who disagreed with copyright... copyleft licenses are 'viral' in that they spread their properties through 'infection' (preventing derivative works from being more strongly licensed).

91. what is the difference between the proprietary licenses and open source licenses?
    - proprietary = fully owned, no permissions.  We use it to mean things you can't reuse, modify, share.

92. How do you deal with projects that say they are released under "the MIT license" but don't include an acutal license text?
    - I would usually take that as a clear sign that they intended that.  You could defend your use in a court if someone protested.  But if you were Google maybe you'd want to be a little bit more cautious since you have big pockets...

93. when you say "you can do" you mean what a person can do using the code that has that specific licence? but he is not the author?
    - Correct. Copyright owner can always do anything since copyright doesn't prohibit them from doing anything.

94. If I create a code with the MIT licence. Hypotetically speaking, someone uses it and creates a software out of it but then the results of the softwares are wrong for some reason. Basically my initial code might have been a wip or something like that. Can he uses the fact that the code does not work properly against me?
     - Once someone pointed out that most good licenses explicitely say that there is no warranty: that the author can never be held accountable for anything that may go wrong.  See the last paragraph: https://en.wikipedia.org/wiki/MIT_License.  Yet another reason to use one
       - ok clear. 
       - edited to make more clear.

### Break until xx:08

### Questions (continued)

95. How about using generative AI in stuff?
     - Some universities already have guidelines (e.g. [Helsinki University](https://studies.helsinki.fi/instructions/article/using-ai-support-learning))
     - be critical with whatever is synthesised with these tools. For example the code generated might be protected by a strict license, but GPT or GithubCopilot won't cite the sources (or hallucinate fake sources when asked). There is an open court case against githubcopilot https://githubcopilotlitigation.com/ (and similarly synthetic images might be reproduction of copyrighted pictures, furthermore, personal data about living individuals can be produced with these technologies which can introduce other issues if the synthetic personal data is going to be published)

96. What would a fully attributed code deposit look like? If the programmer referred to 10 tutorials, the documentation, and 25 answers on Stack Overflow...it doesn't seem feasible to keep track of exactly which snippets came from where. Attribution could be longer than the script. Am I missing something?
     - If I understand this correctly, then I would probably attribute the project/repository as a whole.
         - So attribute StackOverflow rather than the individual users?
             - Oh, then I misunderstood.  Good question, I guess I would attribute each part at the point it was inserted
                - This feels very impractical in practice - if I have a bug and look at 10 different StackOverflow comments and eventually figure out how to fix it, it's hard to tell where I "got" the code in the end. Hmm.
                - If something is so small - I'm not copying directly but reading, understanding, and then putting in my own words, I wouldn't cite.  But this is indeed a very important question!
                    - Yes, it's harder (for me, anyway) to tell where to draw that line with code, I think. And code inherently has fewer ways to be put together than still work than natural language, so snippets will inevitably be repeated independently, given enough programmer monkeys with keyboards.

97. So do you think that the repository on git hub should be private when you are working on it and only when it is ready for the public, make the repository public? 
     - I would always make public from the start, since it reduces the "well when do I do it".  History will be public anyway, and this helps "keep you clean".


### Software citation
https://coderefinery.github.io/social-coding/software-citation/


98. IG_question: how to assign a proper number to a version of my software, e.g. 1.2.3 or 1.2? What defines these digits?
     - It's up to you, but "semantic versioning" is one common guide: https://semver.org/ which says what the three digits should mean.  But "they are just numbers".


## Feedback, day 4

Today was:
- too fast: 
- too slow: oo
- right speed: ooooooooooooooo
- too advanced:
- too basic:
- right level: oooooooooooooo
- needed more exercise time: 
- needed less exercise time: 
- I will use what I learned today: ooooooooooooooo
- I would recommend today to others: oooooooooo
- I would not recommend today to others: 
- too slow sometimes, too fast other times: o
- missed first part and have to go back and do exercises: o

One good thing about today:
- I liked to learn more about containers and dockers. (+3)
    - We have a dream of a dedicated containers *for scientists* lesson/workshop. Join us in CodeRefinery if you'd like to help make it possible...
        - I would love to do that! 
        - Oh, that's great!
    - Also some computing centers have their material. Here's [CSC's example](https://csc-training.github.io/csc-env-eff/#9-containers-and-apptainersingularity)
    - See also: [Reproducible computational environments using containers - Introduction to Docker and Singularity](https://www.archer2.ac.uk/training/courses/210728-containers/)
- Snakemake primer was interesting, will try it out (+9)
- Definitely saving properly the environments will be the most useful for me
- I liked the introduction to licensing and the great compilation of resources. Will use this knowledge in my own work.: (+2)
- Learned so many new and useful things today! (+3)
- R examples! :) (+2)
- very nice exercises, nice information, everything very useful.

One thing to improve for next time:
- Would like to have more hands-on exercises. Now it's mostly listening(+1)
- More about Snakemake!
- More about environments. I still did not understand what it is. (+1)
  - Let's say: "It is a defined collection of libraries (=dependencies) that your code uses."
- MATLAB examples! I mostly use MATLAB, but now there was nothing about it :(
    - Matlab has strong versioning of its environment: if you use version "RYYYY*" (e.g. R2022a) you know that another researcher with that version has the same "environment". Of course external toolboxes suffer of the same reproducibility issues (e.g. new versions of Matlab might break old toolboxes)
- It would be great if participants had time to read through and answer the questions you asked and then discuss the answers later. For me, it was hard to read/write/listen at the same time. I feel it would not get boring, even if we took more time for that.
- If people ask for MatLab, then I'll also ask for Wolfram Mathematica examples. This is the real tool for everything, widely used, well supported.


Any other feedback?
- I would like to see some examples of good/best practices documentation/attribution (e.g., how do you correctly attribute a script you write yourself?) (+7)
- An example of good citation in a repository (+1)
- Ethics and copyright law could be a whole session! Lots of gray areas/regional differences.
    - I think a session might not be enough to understand this... more like a degree is needed :) (+1)
        - Brief clarification of difference between ethics/good practices and legal requirements might be good to have, though.
            - We covered some of these topics in few videos at Aalto univeristy https://www.youtube.com/@aaltoresearchservices/videos
- I think that this course should be longer, so that everybody can be at the same phase. 6 half days are not enough for all these info.
  - Thank you for bringing this up! We have acknowledged the issue and have been considering options. Maybe a series of mini workshops?
- Is it possible to provide solutions to exercises directly beneath each question instead of all together at the end?
- loved the cartoons and jokes in the material! xD
- Thank you so much!!
- Such an incredible course, so happy! Was so sad waking up last friday to realise I have to wait till tuesday for this to continue:D

> On behalf of the CodeRefinery team: We are really happy to read all these feedback! 🥳


