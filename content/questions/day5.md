+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 5"
+++

## Icebreaker questions

### Icebreaker Q1: What tools do you use for writing code?
- Gedit / Vim with plugins, VSCode
- Emacs, Atom, VS Code
- Jupyter (+20)
- Rstudio (+12)
- R (+2)
- VisualStudio Code (+8)
- MATLAB (+4)
- VSCode + Jupyter notebooks (+4)
- Sublime
- bash (+2)
- Spyder (+5)
- PyCharm (+3)
- Nano (+1)
- Notepad++ (+2)
- VSCode + Vim (+1)
- Keyboard (+1)
- NeoVim with Lazy plugins
- used to use Matlab but have moved to python
- will be learning Python... what to use?

### Icebreaker Q2: What tools do you use for debugging code?
- bash (+1) : `bash -x`, Perl: `perl -d`
- print statements :) (+11)
- pdb (python) (+1)
- `import pdb ; pdb.set_trace()` or `import IPython ; IPython.embed()`
- MATLABs inherent debugging tool (+2)
- R
- RStudio (+1)
- eyes (+6)
- PyCharm debuggint tool (+2)
- mini test data
- Mel9 
- Coffee (+9)
- A rubber duck (+2); one lives in my computer bag
- DAP
- Spyder´s variable viewer (+4)
- I should use VS code debuggıng but I rarely do
- the remaining shreds of my sanity (+3)
- Jupyter Notebook (+3)
- carbs

### Icebreaker Q3: Are you already using Jupyter for some projects?
- Never used it, since never used neither Python, nor R. Besides, I have a poor feeling about Jupyter, namely the concept is borrowed / stolen from Wolfram Mathematica concept of *cells*.
- yes for quick interactive prototyping, but then I move to non-interactive python scripts (+3)
- yes for writing drafts so that I can control every step, then I switch to a normal python script (+3)
- yes, Python for sentiment analysis, while R for all statistical analyses
- I have never used it; what is it even used for? (+3)
- yes, almost every day (+1)
- no(+4)
- No, but some of my collages they are, and I think that it's is a really useful tool. 
- No, but some of my collages they are, and I can't force myself to like it
- No, but I might start if I like it
- Started with it while switching to Python, but am looking for alternatives (partly for better Git integration)
- Yes, I have been using it intensely for over a year now and created my entire robot workflow on Jupyter. 
    - 'Robot' workflow?
    - Yeah, I am doing literate programming to create workflows on the Opentrons robots only using Jupyter. 
- yes, for any short programming, especially if I need to explain it better to myself. Really like the Markdown possibility



## Questions

1. Is there a link on explanation on how to install `jupyter` on `git bash`?
    - Usually it would be done through `conda`. For the purposes of this course, run it through the `coderefinery` anaconda environment.
    - Can I do these commands in CR anaconda?
 
    ```bash
        mkdir  jupyterlab-demo
        cd jupyterlab-demo
        jupyter-lab
    ```
  
- Basically yes.  If the environment is activated.
- How do you get it activated? `conda init` ...?
- `conda activate coderefinery` if you have the `coderefinery` environment created. If not, read more [here](https://coderefinery.github.io/installation/conda-environment/#).
- I had it working yesterday but now I get an error `command not found`. How can I find/activate the environment that I should have already? I have it in the list when typing `conda env list`.
- Good check. Then `conda activate coderefinery` should work, assuming it's the correct name for the environment.
- But it doesn't, it gives me an error
    ```bash
        CommandNotFoundError: Your shell has not been properly configured to use 'conda activate'.
        If using 'conda activate' from a batch script, change your invocation to 'CALL conda.bat activate'.
        To initialize your shell, run $ conda init <SHELL_NAME>"
    ```
- Are you using miniconda or Anaconda?
- Anaconda3, and when I run the test code to see if I have everything ready for the course it checks okay that "good to go". Should I be in a specific directory? I also have the `environment.yml` in my directory and it is named as "coderefinery" when I look at it.
- It might be too late to solve now... you might need to ask somenone locally to take a look.  If using anaconda3, you still may need to make the coderefinery environment + activate it to get our versions.
- What operating system are you on?
- One suggestion would be to open a new terminal and see if the problem persists. Or alternatively use Anaconda Navigator. All packages that we use should be available.
- if linux/mac: `source activate coderefinery`
- if windows: `activate coderefinery` maybe?  I'm not sure
- `source activate coderefinery` worked! Such a simple solution, thank you for your time! I am using `git bash` in Windows.


## Jupyter
https://coderefinery.github.io/jupyter/

2. Is there an easy way run the notebook as a Python script through the Python interpreter "outside" of JupyterLab?
    - Usually, you would export the code to standard Python.  What is in the cells is standard Python, you mainly need to put it in plain text form to be executable.
    - By this question, did you mean to run the notebook as a Python script through the Python interpreter "outside" of JupyterLab?
        - That's right, this is what I meant. I have rephrased the question :-)

3. Is there a way to conveniently integrate `R`, `Python`, and documentation into one notebook?
    - The `rpy2` library may offer a solution. More info [here]((https://pypi.org/project/rpy2/). [This blog](https://anderfernandez.com/en/blog/how-to-program-with-python-and-r-in-the-same-jupyter-notebook/) may be useful as well.
        - What about running `Python` within `R` (using an R Markdown notebook)? Is that possible?

4. Should instructor #1's sound be softer still? (+1)
    - Thanks! I will relay to instructors ...
    - Yes, the sound is too loud compared to [name=Teemu's] in our video conference room...
    - And someone is spinning a spinner? There is some background noise
    - Thank you, that solved the issue
    - Now it is just fine!(+1)
    - Thank you for trying to solve it - even if it interrupts, it is still nice for a full day of listening that it is more balanced!


### Notebook interface
https://coderefinery.github.io/jupyter/interface/

5. Do notebooks offer variable viewer, like `Matlab` or `Spyder`?
    - Is this for debugging? Like a variable inspector?
    - Yes, they do and I've seen it.  It might be an extension or built in ... I don't remember how to get to it...
    - There is also this one: https://github.com/lckr/jupyterlab-variableInspector but I haven't used it yet, only watched the demo.

6. How do these components look like in Google Colab?
    - Pretty similar in concept but I think they have re-done a lot of it behind the scenes.

7. Code along? Or not?
    - Demonstration, watch only.

8. What's the difference between `jupyter-lab` and `jupyter-notebook`?
    - `jupyter-notebook` was there first and later `jupyter-lab` got developed, which can do a bit more than only notebooks: easier navigation, several notebooks opened at the same time, tabs, terminal, extensions, plugins.

9. Markup vs markdown?
    - markdown: one specific syntax (actually a whole group of related but different ones)
    - markup: general term for adding in extra syntax markers to text that affect display.  There are many different types of markup syntaxes

10. What does (*) mean near Control button in the shortcuts?
    - Is that the symbol for the corresponding key on a Mac keyboard? (Linux person answering here so I am not sure ...)
    - Yes, it's the command key.


### A first computational notebook
https://coderefinery.github.io/jupyter/first-notebook/

### Exercices until xx:55
https://coderefinery.github.io/jupyter/first-notebook/#an-example-computational-notebook
- Use this time to start the notebook, see if it works, and try to do as much of this sample notebook as you can.
- If you already know notebooks well, see some of the more advanced triks and ideas (if needed there are interesting things to look at in the optional episodes).

I am:
- done: ooooo (+1)
- not trying:
- need more time:
- doing advanced stuff:
- had problems:oo


11. What is an Iframe?
    - `iframe`: it's embedding one web page into another webpage.  In this case we are saying "embed this other web page in notebook so that you can refer to it more easily".
        - we need to run this command in the jupyter-lab, you mean?
            - oh yeah , cool it works

12. I have copied the ## relevant formulas into the cell and ran it with shift-enter, but it gives me a syntax error. How do I let notebook know that it is all markdown? 
    - What's the last line(s) of the error message? line before?
        - ```bash
            Cell In[3], line 3`
            square area: s = (2 r)^2$
            SyntaxError: invalid syntax
            ```
        - You are likely running the cell as a code cell. Change it to a Markdown cell. In the menu bar, where it says "Code", click, dropdown, select "Markdown".
            - Ah yes, got it, thanks!

13. What's the potential advantage of opening Jupyter notebook from Jupyter lab other than opening it directly by typing `jupyter-notebook`?
    - `jupyter-lab` is a different interface for `jupyter-notebook`.  Both read the same file format but lab is a newer interface (e.g. multiple tabs in one window). Is this what you were asking?
        - Yes, thanks!

14. Yesterday, the instructor (the one with the cat) mentioned you had so much feedback, ~80 ``<smth>`` of text. Is `<smth>` KB or MB? :)
    - It was KB.

15. `jupyter-lab` answers: `command not found`
     -  I got it. Needed to do: `conda activate coderefinery`
        - great :-)

16. The result is 3.116. Not as accurate as I thought.
    - Does it get better with more points/throws?
        - Yes, it is better, but with 10k points it is still far. :-( Another think I am finding is that after change the value of the points I have to rerun all the  code blocks. Is there any way to update all the remaining blocks after when changing the value of points ??
        - Yes. I can't remember the shortcut right now (learner here), but just press the "fast foward" double arrow in the top - it will restart the kernel and rerun all cells (basically deleting all saved variables and running everything from the top again). (with 100k points i get 3.1424 - but will always change between runs, since it is with random generated values. to get a good estimate I would suggest using 1kk, but don't plot that ;))
            - Ok, done. Thanks for the tip. ;-) with 200k 3.1416 exactly. Perfect.

17. This has bugged me for some time now, but is there a way to make the images centered rather than on the far left?
    - You mean now images in a Markdown cell?
      - Yes!
         - As far as I know, Markdown does not have concepts/means for that (please somebody correct me if you know) but one thing that one can do, is to use html styling inside Markdown but I haven't tried this. 
             - Alternative: maybe this one has more styling options: https://jupyterbook.org/
                 - Awesome, thank you! :)
                    - OK, I think I have tried the html method and i tworks ok. I was wondering if it was possible using Md.

18. I got an error:
```bash
 ModuleNotFoundError                       
 Traceback (most recent call last)
 Cell In[1], line 4
       1 # importing modules that we will need
       3 import random
 ----> 4 import matplotlib.pyplot as plt
 
ModuleNotFoundError: No module named 'matplotlib'
```
- Are you using the CodeRefinery conda environment?  It should have this included.
    - Ah, got it! I'm still not totally caught up on `conda`... it is working now.
       - There are also tools that automatically activate environments once you step into a directory. e.g.: https://direnv.net/ - maybe this can be useful one day, not saying that we should start adding more layers now :-)

19. What does it mean in [first-notebook](https://coderefinery.github.io/jupyter/first-notebook/#an-example-computational-notebook), `markdown cell`? Do Jupyter cells have different type? How to change it?
     - there are two types: code cell for code (Python or other language) and Markdown cell for documentation. one way to switch is above in the notebook tab I see a "Code (arrow)" where I can switch between Code, Markdown, and Raw (not sure what that will be) - did you find it? There is also a keyboard shortcut to toggle ... (don't remember it though)
         - Yes, I found a `code` button. Thanks!
    - keyboard shortcut to switch between cell types is "m" and "y"
        - I'm not sure about the shortcuts, just press "m" / "y" when in a cell to switch the cell type?
            - You need to have the cell selected but can't be writing in it for the keyboard shortcut to work.
                - Oh, I see now, got it.
                    - esc + m gives Markdown, esc + y gives code, esc + enter opens the cell for writing again.

20. Is there a simple way to look into the docs of functions of libraries inside Jupyter-Lab?
     - In the top menu, select Help -> Show Contextual Help, then place yoursef over a function etc (eg. ax.scatter) and see the docs there. Also you can SHIFT+TAB over a function etc. and a popup with the docs appears.

21. I have difficulties with shortcuts. All Ctrl-Enter and Shoft-Enter work but the capital letters alone keep writing to cells. How should I run the capital letter shortcuts (Windows 11)?
      - With the cell selected, press ESCAPE to go into command mode. Click on the cell to go back to edit mode. Cells are modal.
          -THNX!

22. Since we talk about jupyter notebook today, it will be nice to mention the google colab. I saw that you will talk about how to share the notebook. What are the advantages and disadvantages when we have a large amount of data that are not stored in our computer but remotely?
    - I think we'll mention.
        - But I guess the advanges are like everything with cloud: convenient for getting started, but it's someone elses computer. The conditions can change at any time, less security, more cost.
            - Nice with Colab is the collaboration option. Tried a few _years_ ago, not as real-time as I would have wanted.

23. What are static notebook and dynamic notebook?
     - Not completely sure what the context was but you can browse a notebook on GitHub but then it is "static" (you can't modify it live and change values) but then you can also run a notebook through Binder and then it is dynamic and looks like if I ran it on my computer and I can add cells and modify values and test how the notebook will adapt.
         - Here is the notebook: https://github.com/coderefinery/jupyter/blob/main/example/darts.ipynb (static version, later we will learn how to share notebooks which are dynamic and can be modified). This was the context just below the exercise.
            - Ah yes, so my answer was then relevant :-) Later we will learn how to share a notebook that others can run AND modify without installing Jupyter on their computer.

24. How do you abort running a code?
     - Top menu: Kernel -> Interrupr Kernel, or alternatively press the little "stop" square near the "play" icon.

25. I'm not sure if I understand the use case of Jupyter lab. Can it be used for sensitive data?
    - Since it's running on your own computer, it's as secure as your own computer. Which is one reason for it vs similar cloud services.
    - But more broadly, it's about an easy way to do things interactively. It's not good for everything, but conventient for certain things.

26. How to properly close the Jupyter notebook session in a browser that was started by `jupyter-lab` command in a Linux terminal? Close the tab and `Ctrl+c` in the terminal?
    - To shutdown the JupyterLab session completely: File -> Shut Down. To just close the notebook you are editing just close the tab, but the kernel remains active, to shut it down Kernel -> Shut Down Kernel (or in the Kernel management side panel (black circle with white seuqre inside). If you CTRL+C in the terminal it will also kill the JupyterLab session and the web browser will tell you that can not connect or something similar.

27. Ctrl+q doesnt work for closing notebooks?
     - CTRL+C kills the whole JupyterLab session.
         - In Git Bash? Or in Jupyter itself?
           - In Git Bash
     - Remember to save your work before that.

28. How can I use git bash now, while jupyter is running? I cannot type anything in git bash.
    - Can you just open another git-bash terminal?
        - Yes.
            - Then that's the way to go. Alternatively, you could probably try running jupyter in the background, but this would lead to outputs from jupyter being written to that terminal. What you can do (but with quite some effor) is running jupyter as a daemon, but For your local system I would not recommend it, but just have one terminal running it. 


### Notebooks and version control
https://coderefinery.github.io/jupyter/version-control/
Demo: don't type along yet.


29.  Bigger font in the terminal please! Much better, thanks.
     - Thx for the feedback.

30. Did you create that `yml` file?
    - I am guessing it is this file: https://github.com/coderefinery/software/blob/main/environment.yml ? This is the file we install the `coderefinery` environment from. But I was distracted and did not see how the instructors got to that file.


31. I don't see the `yml` file in my folder.
    - It's put there specially, I think from installation instructions, don't worry.
    - I guess it'd be the `coderefinery` environment file they provided for the setup.
       - Indeed. you don't need it here but I guess the instructor prefers to keep the environment file close to the project because they have many other environment files on the disk. RB: I do this personally the same way. 

32. I got an error trying to run `jupyter labextension install @jupyterlab/github`:
```bash
"An error occurred.
ValueError: Please install Node.js and npm before continuing installation. You may be able to install Node.js from your package manager, from conda, or directly from the Node.js website (https://nodejs.org)."
```
- I wonder if that is already included in the CodeRefinery Conda env. -> It's indeed.
    - I'm using the `conderefinery` env.

33. I read a small piece of text regarding OpenCommit, an AI generator of better commit messages to git. Any thoughts on that?
    - I have not checked yet -MJ
        - This is the link of [it](https://www.npmjs.com/package/opencommit)
          - Looks cool! I wonder how accurate the commit messages then are. At least they look as "good commit messages" in the screenshot there.
    - I might say "if the message can be generated from the code, maybe it's not useful.  More useful is *why* it's made: the human side.  what bug fixed?  how found?"
        - Are we humans doing better? Many commit messages are exactly like you described, too vague and really focused on what have changed. Would be nice to have some sort of good practices for commit messages, so we all could improve on that.
          - Some resources on good commit messages: https://initialcommit.com/blog/git-commit-messages-best-practices, https://www.freecodecamp.org/news/writing-good-commit-messages-a-practical-guide/, https://www.gitkraken.com/learn/git/best-practices/git-commit-message

34. How do I paste something into nano?
    - what OS?  It's a question of what terminal you have, try right clicking, middle clicking, or left&right clicking at same time.
        - Windows, right click worked.

35. How do you get that cool green checkmark or red X for the git folders?
    - try searching "checkmark in shell prompt".  It shows the exit status (success/failure) of each command. There are many interesting prompt customizations!  Also "git-aware prompt".  I'm not sure exactly which one is being used here...
        - Thanks, I'll have a look!

36. Surprising correspondence between a Wolfram Mathematica notebook and a Jupyter notebook! The same cells concept, raw files in both look in the same way! Even the working documents in both are called in the same way, namely **notebook**! How it that possible?
     - One got inspired by the other? :-) and that's OK in my view since Jupyter is open source code and is inspiration for a number of similar tools. But I don't know the history here and I am not sure who was first.
     - Mathematica was first, but I agree, nothing wrong with basing on good concepts from other systems.

37. Could we have a break? (+1)
     - We will raise this. Yes.
     - We will have break in a few minutes.

38. How can I close the notebook and access the bash terminal again? After I open the notebook, I can't use the terminal to type anymore. Any command I need to know? Even after using ctrl+c, I do not seem to be able to type in the terminal.
    - Try Control-C to quit the Jupyter process.
    - Open another terminal :-) If you ctrl+c you'll kill the JupyterLab session completely.

39. How do you use git commands inside the jupyter environment?
    - Either in the terminal on jupyterlab or using plugins/extensions (as demonstrated now) where one can stage/commit/... on the side bar.
        - What is the terminal on jupyterlab? And I could not follow the instructions as demonstrated.
            - Is a terminal emulator. In the "Launcher" tab, go to the bottom, in the "Other" section press the "Terminal" icon.
    - in Jupyter you can also run bash commands in a code cell if you start the line with `!` eg. `!ls`.


### Break until xx:27
Then we;ll discuss the Binder service before going to documentation.


40. I tried refreshing the notebook and it does not want to load. It says in the browser below waiting for localhost. Maybe because I was using Git Bash and it lost connection? I still have git bash open with a connection to jupyter-labs. Weird. 
     - You likely CTRL+C in the terminal where you ran "jupyter-lab" thus killing your JupyterLab session.
         - I CTRL+C in the terminal just now and funny thing is that it started the connection. I used another terminal to set up git. Maybe thats why? 

41. I found this session very useful so far but the last section was a little fast for me :) 
     - Thanks for the feedback.

42. Sorry, now I'm confused. Will there be an exercise for the section "Notebooks and version control" after the break? Or do we go straight to the next lesson?
     - This was a demonstration. After the break we will have an exercise on how to share notebooks.

43. Wolfram Mathematica has its own editor to type in commands, perform cells, etc. What about Jupyter, are there only web browser based tabs for editing or is there an app with editor I can install on Fedora/Ubuntu?
    - I'm not aware of any specific editors but you can open/run/edit notebooks in Visual Studio Code (with the right extension). [instructions](https://code.visualstudio.com/docs/datascience/jupyter-notebooks)
    - Spyder also has some extensions that allow you to run jupyter notebooks.
    - [JupyterLab Desktop](https://github.com/jupyterlab/jupyterlab-desktop) – I think also open source so I don't know about the support.
        - Do they all support cell-based view?
          - Don't know about spyder. JupyterLab Desktop looks the same as in web browser and I think VSCode has cells but looks different
              - :+1:

44. How do I create the `.gitignore` file in the jupyter lab terminal? I cannot use `nano`.
    - I think "new text file" (and then renaming to `.gitignore`) would work.  I hope that jupyterlab doesn't hide the files begining with `.` (hidden files)
    - `nano` works for me
    - Also in Jupyter (with Git stuff installed) you can in the commit view / staging area just right-click a file and select "add to gitinore"
      - New text file does not work, nano either and I cannot see where I can add to gitignore in the commit view
        - I am curious because all those should work. The issue might be somewhere else. Anyway needs more information to be able to debug.
            - This is what I get:
    ```bash
    (base) C:\Users\20225533\AppData\Local\anaconda3\envs\coderefinery\jupyterlab-demo>nano requirements.txt
    'nano' is not recognized as an internal or external command, operable program or batch file.
    ```
    - Use another text editor that you have installed on your computer.

45. After I close my server using ctrl+c, I still cannot type in the terminal. Can you please explain how can I use the same terminal?
    - It might still be running, waiting for some other process. Try using ctrl+c multiple times in a row.
    - It might be asking you if you actually want to shut it down (as in type "yes" or "no"), but the message get's lost in the output.
    - I sometimes have to type ctrl+c multiple times.


### Sharing notebooks on Binder, exercise until xx:44
https://coderefinery.github.io/jupyter/sharing/

46. How do I push the notebook to the git repository? And is it only the notebook or the whole folder I need to push? (+1)
     - The notebook file and `requirements.txt` need to be pushed
     - How to push:
       - `git init`
       - `git add mynotebook.ipynb`
       - `git add requirements.txt`
       - `git commit -m "adding notebook and requirements file"`
       - Now either follow instructions from github or:
       - `git push GITHUBADDRESS master` (assuming the branch name is `master`)
- I did this, but it is not showing in GitHub. I see compare & pull request. But when I click it says there isn't anything to compare. However I see a changed file down but can't do anything with it... (+1)    
    - Any error messages?  Did you create a repository on GitHub and use that?
- Yes, I have created a repository on GitHub. Pushed it there and now it says `master` had recent pushes 6 minutes ago. But now what? I don't see the notebook file in github. I have to pull? but how?
    - If you like you can share github address here and I can look? But no pressure. https://github.com/user/githubrepo
- I have the same, or a similar, problem: https://github.com/user/githubrepo.git
    - Looking .... yes there is only a README. I believe the README was created by GitHub and you did not push your local commits.
    - If the repo only contains a README:
        - in the web browser "Add file" directly on GitHub and add here notebook and requirements.txt (then you don't need to `clone` and create commits locally)
- I think the `push` worked, I have to `pull` now right?
    - By worked you mean the notebook is now on GitHub? 
- No, but GitHub says `master` had recent pushes 9 minutes ago and git bash did not give me an error. So normally if I push it should directly show in the GitHub repository? Or do is have to `pull` from github? 
    - Yes, if you `push`, it should show up there (maybe you need to reload browser page), no `git pull` needed. The `git pull` would be used if you want to get changes from GitHub to your computer.
- Still struggling to understand why it is not working. If I `git push` again from the terminal it says:

```bash
git push git@github.com:user/githubrepo.git master
Enter passphrase for key '/c/Users/user/.ssh/id_ed25519':
Everything up-to-date
```
- Everything up-to-date according to git. So weird... Of course I can add file in GitHub. But I want to learn to do it using git bash.
    - Did you stage the file `git add .` and commited your changes, `git commit -m "my first notebook"`? Check with `git status` that you have a clean working directory.

47. Do we do the `git push` at anaconda or at git bash? It was not clear.
       - git bash (we need a terminal that knows about git)
       - or: terminal in the jupyterlab should also work

48. Can you share an example solution once the exercise is over?
       - yes good idea, working on it ...
         - repo from 3 years ago: https://github.com/bast/binder-example
         - let's see whether the rendered Binder still works: https://mybinder.org/v2/gh/bast/binder-example/HEAD 
            - testing ... suspense ... reproducibility being stress tested ... 
              - drumroll .... it works! a repository I haven't touched in 3 years still runs and does the same thing thanks to `requirements.txt` and Binderization
              - except an image that was loaded from another web address which moved
       - Thanks!

49. How do I get away from jupiter lab in the terminal ctrl q is not working?
    - Try "control-c", maybe multiple times quickly.
    -THANK YOU!
    
50. See question 46. how to continue after push?
    - looking ...

51. I am not able to connect to my repisotory:
```bash
"Failed to add the host to the list of known hosts (/u/.ssh/known_hosts).
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository."
```
- Have you been able to `git push` last week or is this first time you try?
- I have been able to do all exercises until now, also the `git push``, clone` etc.
- Try `ssh -T git@github.com` in the terminal, does it gives an error?
- It gives:

```bash
The authenticity of host 'github.com (<ip-address>)' can't be established.
ED25519 key fingerprint is SHA256:...
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Failed to add the host to the list of known hosts (/u/.ssh/known_hosts).
git@github.com: Permission denied (publickey).
```
- Mmm, strange. I'd open a fresh terminal and try `ssh -T...` again.
- Same error.
- Strange as you say you could access other days. I'd check the public key in the GitHub interface (setup instructions). It should be in `/u/.ssh/*.pub
- I don't have access to `ls -al ~/.ssh`. I think it might be because I am not at the university now for the first time during the course and it could be related for me needing to be in the university's connection to have access/permission to some files, since I am on the university's computer. Could these rights have some effect?
- I don't see how, but it seems so :-)

52. I am confused of how we managed to add the jupyter notebook in GitHub. I undestand that we need to clone etc, but then when I did git add "jupyter notebook", I get the error message `fatal: pathspec 'calculating_pi.ipynb' did not match any files`.
    - That error indicates that the file has either a different name or is perhaps not in the same folder? 
        - The name is correct but in anaconda I had a diferent path directory than the one in git bash. Is it possible to share a link with instructions probably? Solved :) I found the jupyter notebook in git bash and I saved in the directory connected to GitHub.
            - Well done!

53. Can I use the Binder integration on GitLab too?
    - Yes, GitLab, Zenodo, figshare, dataverse, ... the Git repository can be in principle anywhere if it is publicly accessible. But it is a good idea to put it into a place that won't disappear in 2 years.

54. Binder gives an error - saying that I should check the URL, no idea where the error is.. 
    - It was set to private on GitHub... whoops...

55. I cannot do a pull request to merge `master` into `main`, why? It just says 'there is nothing to compare' (but there clearly is, if you check out the `master` branch vs. the `main` branch) https://github.com/user/BinderSharingDemo.git
    - The two branches look unrelated: https://github.com/user/BinderSharingDemo/network.
    - It looks to me like `main` was created by GitHub and then `master` was pushed from a different local `git` history.
        - Yes, so what? I don't know how else I would have done it.
    - In this case GitHub does not know how to relate them during a pull request. You can typically either push a `master`/`main` branch from local to GitHub or to create it on GitHub and clone it to computer but here you did both :-) recovery: I would on GitHub use "Add file" button to add the files to the main branch directly in the browser and then I would delete the `master` branch. There are also command line options to recover if you are interested.
            - Aha, so if I push the master from git bash to GitHub it makes a new branch because in GitHub the branch is called main? How do i push the master branch from git bash to the main branch in github? 
            - Rename the master brach to main: `git branch -m main` (being in the `master` branch of course)
                - Yes, thanks! This is very useful and kind of unlogic that GitHub is called `main`` and git bash is called master` by default. 
                  - I configure also my local git to create new repos with `main` as branch to avoid this mixup. search for "defaultBranch" on the web.
                      - I tried pushing again after renaming the branch to main. Now it gives me an error:
    ```bash
    ! [rejected]        main -> main (fetch first)
        error: failed to push some refs to 'github.com:pvand/Share_exercise.git'
    hint: Updates were rejected because the remote contains work that you do
    hint: not have locally. This is usually caused by another repository pushing
    hint: to the same ref. You may want to first integrate the remote changes
    hint: (e.g., 'git pull ...') before pushing again.
    hint: See the 'Note about fast-forwards' in 'git push --help' for details.
    ```
- `git pull`, fix conflicts if any, then push
- after `git pull` I get this:
    ```bash
    * branch            main       -> FETCH_HEAD
    fatal: refusing to merge unrelated histories
    (coderefinery)
    ```
 - I have the same problem!
    - Or `git push -f` to force-push. Warning!  It will lose whatever has already been pushed, so make sure you know what's going on.
    - I recommend the following recovery: on GitHub open the default page and add the two files using the "Add File" button. The reason that many people report these problems (see also next question) is that they created one git history through GitHub and created a different git history in their command line with `git init`.
    - Unfortunately this may have gotten beyond what we can answer this way.  You might need local support to look at the screen and see - are you at one of the partners?
    - OK, thanks for the answers, I will try the above suggestion. 

56. Complete failure - I was able to set up repos and push fine the other day.
```bash
git push -u origin main
To github.com:user/darts-demo.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com:user/darts-demo.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
   - This looks to me like you have a `main` branch on GitHub created by GitHub (you maybe created the repo and asked to add a README) and you have a `main` branch locally with a different history and now git/GitHub does not let you accidentally wipe out the remote main history
       - Ah, I think that was it. It's working now.
          - Great!

57. I get the error in binder `Could not resolve ref for gh:username/coderefinery/HEAD. Double check your URL. GitHub recently changed default branches from "master" to "main".` Is it because my repo is private?
      - Ah, yes. If it is private, then binder can't see it and find it.

58. How we do get the conda enviroment file into the file repository? Will this be used when running the notebook through binder? 
      - Y,es instead of `requirements.txt` you can add `environment.yml` and Binder will use it. Example of this: https://github.com/coderefinery/software
        - Where can I get the `environment.yml` from?
          - You mean this one? https://github.com/coderefinery/software/blob/main/environment.yml
          - Yes, thank you! I thought I could find it on my system somewhere once I already the conda environment installed. Do you have any courses on conda environemnts in coderefinery that I could use to learn a bit more? 
            - This is a good one: https://carpentries-incubator.github.io/introduction-to-conda-for-data-scientists/ (not from us)
            - Awesome, thank you!

### Sharing dynamic notebooks on Binder
https://coderefinery.github.io/jupyter/sharing/#sharing-dynamic-notebooks-on-binder
- Do what you can, the time is a bit shorter so if you can't finish, it's OK, we will move on to something else and then you can return later.

I am:
- done: ooo
- not trying:
- need more time:o
- had problems:ooooooooooo

### Wrap-up Q&A.

### Notebooks in other languages
https://coderefinery.github.io/jupyter/first-notebook/#notebooks-in-other-languages

## Documentation
https://coderefinery.github.io/documentation/

### Discussion
#### Why is project documentation important? Why?
  - because you never remember what you have done after a year or two!! (+5)
  - after just 1 day! :D (+3)
  - So that you yourself and other users know what the code does (especially when not running it for a while yourself)
  - so that others dont have to waste too much time figuring your code out for their own use (+3)
  - To make it reproducable as well as useable for others when you aren't available (+1)
  - To know what and how the work was done. 
  - So that the code is reusable and published open source

#### How would you describe a useful documentation?
  - There are at least two groups, users of a software and developers of a software. The granularity of useful documentation is different for the two groups, e.g. users are not expected to read in-line code documentation. 
  - You can understand the code without testing it
  - You can understand the code and learn from it for other uses
  - A documentation with which you can run the code (+2)
  - Clear and organized. Detailed. Uses same steps than the code.  
  - Can be followed to recreate a working state that the documenter once had.
  -  something other than "this part works but i don't know why"
   - Providing a Readme file and in-line commenting using #
   - states exactly where the commands need to be run (e.g. local terminal, container, web interface etc..)

#### How can you motivate your colleagues to contribute to the documentation?
  - Buying candy!
  - Tell colleagues the fact that this just IS the way the lab/group does it (document well)
  - with great effort (+2)
  - Illustrating the efficiency and outcome of doing it from the get-to (+1).
  - Force people to document each other's projects, it raises questions that the implementer didn't have. (+1)
  - Sharing the need and knowledge of why documentation is important. Maybe making them attend workshops like these
  - Asking them stupid & silly question regarding their contribution to the code so that they understand the importance of a proper documentation

### Question (continued)

- Audio is great! thanks :) (ps, we miss kitty ;( )
  - It's resting... hopefully it drops by before the end of the day...
      - Aww, important for kitty to recharge batteries
          - It came to me in the morning so might not come too soon...

59. Does `environment.yml` do the same as `requirements.txt` (but then using `conda` instead of `pip`)? In other words, can you opt for the former instead of the latter?
    - for the coderefinery environment, or in general?
    - for coderefinery enviroment: yes, in principle.  we haven't tested `requirements.txt` so much
    - in general: they do roughly the same thing, but `environment.yml` can include much more software (like support libraries), so the environments are more self-contained.
- Ok. So when sharing a notebook via Binder, an `environment.yml` file is sufficient?
    - Yes. Binder will use either `requirements.txt` or `environment.yml` (it recognizes also other files). But yes, that file will be enough.
- This applies in general for other people that use your repo? Or should you have both for pip-users to use `requirements.txt`?
    - Some python-centric projects often prefer `requirements.txt` but both solve the same problem. You could provide both but typically will only provide one (it's harder to test and support both at the same time).


### Break until xx:10


60. So when I did the exercise for sharing notebooks: The last step took me to the jupyter place and I had to myself click on the files there to see what they had in them. Is this what we wanted to happen? 
     - Yes. One can let the binder link also link directly to the notebook instead of the overview. But this was the point of the exercise: being able to share a notebook with others who only need a browser
    -OK thanks!
       - See "Path to notebook file (optional)" at https://mybinder.org/.

61. Please help answering Q55. 
     - Looking ...

62. Just one, maybe idiot, question. When we add the binder launcher on our repository, where our code is being run? So, in case I want to install `R` and `Julia` on the Jupyter, I can do the same way we did earlier, on the terminal of our computers? Or should we do on the terminal from the jupyter environment?
     - It is a good question! It is running "in the cloud" - more specifically: inside a Docker container that is created and later destroyed again.
     - If you want to share an `R` code via Binder: https://coderefinery.github.io/jupyter/sharing/#sharing-r-markdown-studio-projects
     - `Julia` example: https://github.com/binder-examples/demo-julia
     - In short: Binder will look for specific files and you need to add specific files to install dependencies Binder-side
        - Many thanks!
           - One nice thing about binderizing something (not sure it was mentioned) is that it forces me to find out what the dependencies even are because otherwise it won't run on Binder at all while it may still run on my computer ("runs on my machine"). It forces me to document dependencies which is a good thing to have in future.

### Writing good readme files
https://coderefinery.github.io/documentation/writing-readme-files/

63. Is it preferred to use commands in Git Bash or in the Jupyter lab terminal? Or just your preference?
    - Just preference.  Both have times they are more convenient.

64. If changes are made by a user in Binder, can these changes be viewed by others?
    - No, everything is lost in that case.  Unless you save them, of course...

65. I must have been distracted, sorry. But why did we jump directly to "writting good README files"?
    - We never have time for everything, we sometimes choose the most interesting things to discuss (and the rest is easier to read later).
    - So it's not that we are too slow (we/you are not!) but that we want to have more in the read-later material than we can and want to highlight in the 3.5 hours we have.


### Exercise: Write a basic README until xx:31
https://coderefinery.github.io/documentation/writing-readme-files/#exercise-basic-readme
- Do what you can, there are three alternatives you can look depending on your interests.

I am:
- done:ooooo
- not trying:
- need more time:
- had problems:


66. How does GitHub recognises README.md and renders it? Is it a keyword? 
    - Any `.md` etxnsion is rendered as Markdown.  Same for other extensions.
        - What if I have multiple `.md` files? Will it all get rendered on GitHub? Sequentially?
            - Ah. In the repo default view, it looks for `README.*` (first?  only?). But you can click on any file and that specific view does render that file according to extension.

67. How can I see the other readme files created by other users?
    - some public projects:
    - numpy: https://github.com/numpy/numpy
    - jupyter: https://github.com/jupyter/jupyter
        - no I mean created within the exercise.
        - good idea!  Let's see if anyone shares below... 
    - If you want to share what you made, add a link here:
        - https://github.com/user/githubrepo.git

68. Could you redirect me to the page that explains how to fork again?
    - on any github repo find on top right a button called "Fork" - is this what you meant?
    - In git-collaborative: https://coderefinery.github.io/git-collaborative/distributed/#exercise-part-1-creating-a-pull-request

69. In general would you recommend to rename the GitHub branch `main` to `master` or rename the git branch `master` to `main`? To ensure compatibility between both. 
    - Sort of up to you, what you want.  But github + local git repo should be consistent...
        - Well, the push from my local git `master` branch to GitHub did not work. Because GitHub branch is called `main`, it made a new branch on GitHub called `master`. This is quite annoying and I want to be ahead of this next time. 
        - Oh yeah.  So, change one of them.  Either locally (`git branch -m main`, you might want to check `git set upstream branch`) to make local, or change the default branch on Github.

70. I forked the "coderefinery-githubrepo-example" but how do I then clone it to my computer?
    - You can `git clone <repo-url>` in a folder on your local system
    - Thanks! how do I then use `git push` to push my changes to the GitHub repo?
    - Make changes to the files then `git add .` then `git commit -m "message"` then `git push`
    - Thanks! I still cannot push my changes though. It says: `fatal: Authentication failed for 'https://github.com/username/coderefinery-githubrepo-example'`
    - make sure that the URL of the remote corresponds to you GitHub repository; to check the defined remotes: `git remote -v`.

71. I added the readme.md file to my directory on GitHub but the markdown commands are not showing nicely i.e. ## and # and the lists. What's wrong?
    - would you like to share the repo link?
    - (github link)
       - thanks! don't worry we will redact addresses before publishing Q&A later today 
       - you need a space after the "#": "# Rendering well", "#Not rendering well"
        -Thanks!
           - It's like in this document here. it is essentially the same "markup" language


### Typealong Sphinx basics
https://coderefinery.github.io/documentation/sphinx/#exercise-sphinx-basics

72. I missed this (was trying to fix a sphinx problem): seperate source and build directory or not?
    - We suggest to use the same directory this time, but both options work.

73. How do I solve this?
    - error message:
```bash
PS C:\Users\user\AppData\Local\anaconda3\envs\coderefinery\doc-example> sphinx-build . _build
Running Sphinx v5.0.2

Extension error:
Could not import extension myst_parser (exception: No module 
named 'myst_parser')
PS C:\Users\user\AppData\Local\anaconda3\envs\coderefinery\doc-example>
```

- Are you in the CodeRefinery conda environment + activated?
    - Yes
- Most likely it's not activated somehow. I see you are in that directory but that's different from activation.
    - Still a problem. I am in the jupyter terminal. on the conda terminal it does not work either 
- In the terminal (either of the two) on the left side it should indicate in which environment you are in. Something like "(coderefinery)" - does it say that? I am trying to make sure we are actually inside an activated coderefinery conda environment since the error above complains about not finding a module which should be there: https://github.com/coderefinery/software/blob/35a61b4d1f013e44224530f9d4409b5f2a5acef8/environment.yml#L21

74. When I use `sphinx-build . -build` I get the error:
```bash
usage: sphinx-build [OPTIONS] SOURCEDIR OUTPUTDIR [FILENAMES...]
sphinx-build: error: the following arguments are required: outputdir, filenames
```
Did I miss a step?
    - You need the name of the build directory after "-build":
        `sphinx-build . -build _build` (if the build directory is called `_build`)
        - Oh nevermind, it is working now, thanks!


### Exercise until xx:05
https://coderefinery.github.io/documentation/sphinx/#exercise-sphinx-basics
- Do what you can, the next part will start form a model repository.

I am:
- done:oooo
- not trying:
- need more time:
- had problems: 


75. Should the `feature-a.md` file go under the source directory?
     - No, at the same level as `index.rst`
     - (which might be the source directory?)

76. I have earlier built sphinx doc with `make html` command. How is the `sphinx-build _build` different? 
    - Basically the same, the `make` method automates some.  If you look in `Makefile` you can see how.
    - We suggest `sphinx-build` in the exercise since it works on any OS without `make` installed.

77. Question regarding jupyter notebooks: Could one attach the notebook plus output as appendix section? And if so how?
    - to the Sphinx project?  Yes!  The `myst-nb` extension does this: https://myst-nb.readthedocs.io/en/latest/index.html
    - I mean in an overleaf project.
    - Ah.  That I'm less sure of, you probably need to export it in a way that LaTeX can read.  Search around and see what you can find.
    - Also possibly interesting/relevant: https://jupyterbook.org/

78. Can you elaborate on the difference between ReadTheDocs and Sphinx?
    - Sphinx is the thing that goes source → HTML
    - ReadTheDocs is online service that automates it: has users and projects, gets Github notifications and automatically rebuilds, provides the web servers.  It runs sphinx (or other things) for you.
    - Follow-up: Does readthedocs support other tools for documentation creation? 
        - Mkdocs I think.  The "GitHub pages" method we will see next can do almost anything.
    - Follow-up 2: Does readthedocs have tools to generate docs on its own or deos it rely on those other "engines"?
        - Those other engines.  (some customization.  RTD releases sphinx_rtd_theme which is also usable without RTD, like we do.)
    - Thanks!

79. Perhaps in the instruction the `_build` folder will be created after running the executable sphinx, right?
    - Yes.

80. Unfortunately, I have created the feasure-b but it does not show in the webpage. Why is that, do you think?
    - Hm. Is it linked in the index? No.
    - Try adding to the toctree.
```bash
(coderefinery) C:\Users\user\AppData\Local\anaconda3\envs\coderefinery\doc-example>sphinx-build
usage: sphinx-build [OPTIONS] SOURCEDIR OUTPUTDIR [FILENAMES...]
sphinx-build: error: the following arguments are required: sourcedir, outputdir, filenames"
```
- For the sphinx-bulid problem: is it being run like `sphinx-build . _build` ?
- toctree where I need to add it? toctree does not work
```
.. toctree::
  :maxdepth: 2
  :caption: Contents:

  feature-a.md
```
- Works now. Thank you.
- Great!

81. Is there a way to show line numbers in nano? I ask since I received the following message:
```bash
sphinx-build . _build 
Running Sphinx v5.3.0

Configuration error:
There is a syntax error in your configuration file: invalid syntax (conf.py, line 19)
```
- Try `nano -l FILENAME` (seems this is a newer version, see if it works...). or alt+shift+F3 ?
- This hasn't worked.

### Deploying Sphinx to Github pages
https://coderefinery.github.io/documentation/gh_workflow/
(if this is too fast, you can also watch it as a demo and try later)
(this is actually what CodeRefinery does for almost all of its websites!)

82. kitty yay :heart_eyes_cat: : ooo
    - Pspsps

82. Is it normal that the GitHub documentation updates with a delay? My first edit showed up there only when I pushed the second edit. Thanks, I was expecting it to show up immediately -- it's there now.
    - after push, click at "Actions" on top of repository page to see whether it is still building. this can take minutes (which is not a problem in real projects)
    - When building with GitHub pages, the whole GitHub action that is contained in the documentation.yaml is run. This is what takes some time, even for a small document.
    - Then it has to copy to web servers.  Then distribute through the world.  Then expire the old version.

83. So GitHub pages does not build the docu but host static websites?
    - Yes. it will happily serve html built by whatever (there are so many different tools). but then the building can be done as part of GitHub Actions.
    - Thanks!

84. Can you explain the deploy action in the yaml file and the use of the gh-pages branch?
    - Easier question first: gh-pages branch is standard branch name for github pages to serve from. historically it had to be called like that but these days you can configure to serve html from any branch. one thing that I invite you to verify I that it really created a branch called "gh-pages".
    - The Deploy part of the action reuses an action written by somebody else
       - Link for that building block: https://github.com/peaceiris/actions-gh-pages
       - We include it with: "uses: peaceiris/actions-gh-pages@v3"
       - And that action "building block" uses variables which we define under "with" 
       - In short we could have written all ourselves but we reuse good building blocks written by others that can be reused in many similar projects
    - Did this answer the question?
        - Well, I need to read through that, including the actions. It seems strange to me, that using such a "headline" feature of GitHub requires so much custom code.
        - The upside of it is the flexibility to implement basically any action possible.

85. How to remove the public documentation?
    - The GitHub pages website?
        - Yes.
           - One way is to remove the repository, then it's gone.
           - Less desctructive: go to settings and pages where you can disable it again.
               - Found the option "Unpublish...". Thanks!


## Feedback, day 5
Tomorrow, we have one more interactive lesson on testing (using Git/Github Actions more + coderefinery Conda environment).  Then one which is "sit back and watch."  Together they are a great summary and worth watching by almost anyone!

Today was:
- too fast: ooooo
- too slow:o
- just right speed: oooooooo
- too advanced: oooo
- too basic:
- good level: oooooo
- I will probably use what I learned today:ooooooooooooo
- I probably won't use what I learned today: oo
- I would recommend this to others: oooooooo
- I will certainly have to spend another few to several hours to go through the workshop content by myself: oooooooooo

One good thing about today:
- I got to see advanced tools to help with documentation (+3)
- I was challenged today, which I like (+1)
- I found very useful the jupyter lab connection with git and the dynamic notebooks. Also is a better way to version control the notebooks (+4)
- I liked to learn how to integrate binder on github (+1)
- I liked to learn first time about MarkDown: simple but complete introduction.

One thing to be improved next time:
- It is difficult to follow with so many tabs opened. Would it be possible to compress the info without too many links and something linear? Since to do everything take more that 6 half-days, would it be possible to shrink the lessons for the proposed time? (+1)
- The tools were perhaps a bit advanced (+1)
- It feels like some things weren't properly explained in detail, like typical beginner's errors for when pushing and pulling to and from GitHub (something I suppose we should already have learnt, but judging from the amount of people that had problems with it, it seems we didn't learn it well enough)
- Explain why it is a good idea to do things (+1)
- Would have been nice to learn more about the individual tools that are connected to make GitHub pages work. I was not sure which entity does what. (sphinx, CI, pages)
- I definitely would like to have all the basics terms & motivation explained in a better way, more detailed one: why would one need Jupyter lab, git, Sphinx, yaml/yml/json files & etc., maybe referring to real cases (+1)
- motivation for using sphinx
    - as a Sphinx newbie, can tell you: to create, e.g. online documentation, html pages, from source files; just like one creates pdf documents from TeX source code
- The sphinx part could be slower and with more examples on different templates, where to get more tools to customize the content.
- how to delete all the generated examples (+1)

Any other comments?:
- Have a break as the schedule says
    - Yes, we definitely need to do that better.  I should have raised it much earlier.
- I was never convinced that 'sphinx' really is worth learning. Is this industry standard? Does everybody use it? I have never seen it before. (+3)
  - There are many things people use, but especially in the Python community (but not just that), you start seeing it all around.
- Still confused when we should use sphinx. Understanding the point of the readme.md was very easy. But when is this not enough? when do we need to use notebook and binder or sphinx? (+1)} And when should we use jupiter notebook + binder and when sphinx? (+1)
- Would have been nice to together go trhough  good examples of a) readme.md and when that is sufficient, b) jupiter notebook +binder and when was that appropriate c) sphinx and why was this now more appropriate (+1)
- Feeling inspired by you guys/girls & course content to dream bigger (I am not there yet skill wise, maybe never and that' ok, but I think my dream is to be a research software engineer). Thank you for that! :) 


