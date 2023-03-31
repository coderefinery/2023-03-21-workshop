+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 6"
+++

## Icebreaker questions :ice_cream:

Can we get a little space for giving feedback on stream settings, like audio, etc.? For instance, I'd say audio is still at 40%/60% or even 30%/70% between the speakers. better now?
 - Yeah, definitely. I'd say now it's at 40/60 at least

### Icebreaker question #1 What tools do you use for testing code?

  - plots (+4)
  - mini test data before running on big data
  - visual inspection after execution
  - I simply run it to see if it works - but maybe by including a plot or outputting specific parts  (e.g. lists). (+5)
  - Pytest
  - Have used unittest. Would love to use [hypothesis](https://hypothesis.readthedocs.io/) but never got around to it
      - Looks interesting!
  - a "fixed" small dataset with known "ground truth" so that if the results change a lot, then something might be wrong
  - pytest + Github actions

### Icebreaker #2 Tell us some about this course:
How did you attend (alone home/work, small group home/work/online, organized group, ...):

  - Organized group in person: oo♥oo♥oo
  - Alone at home: ooooooooo
  - Zoom group from university: o
  - Alone at work: ooooooooooo
  - TU Delft workshop: oooooooooo
      - Would love to join that one, but is was full (+1)
  - Switching between alone at home and at work: oooo
  - Partly on train: o
 
### Icebreaker #3 What would be the ideal format for this course? (e.g. like this, in-person, videos available and scheduled Q&A/mentoring sessions, etc.)

  - like this but with some scheduled Q&A/mentoring session one week after the course so that we would have time to test what we learned on our real projects and then ask for help.
      - Agreed, but maybe a bit more than one week after (I would say 2-3). (+1)
          - Yes, you're right 2-3 would be even better!
      - For those at Aalto, we have daily Q&A on these topics and beyond. https://scicomp.aalto.fi/help/
      - For those at Helsinki University there is the weekly "HPC garage" which can also cover the types of questions people might have here https://wiki.helsinki.fi/display/it4sci/HPC+Environment+User+Guide
      - at UiT (Tromso): every Wednesday 14-16 (currently in-person but we are thinking about video)
      - Are any of these initiatives public?
         - public meaning that persons from other places can also join? 
                 - Yes! :)
                 - "#help" stream at CodeRefinery chat
                        - Where can I find this "help" stream?
                            - https://coderefinery.zulipchat.com/ We will advertise this again in the outro.
                 - otherwise the weekly/daily help sessions often (have to) focus on groups affiliated with the university (have to because of limited resources)
  -  It is nice the way that you organize it. We are many participants though to be in person, but I found it a bit difficult this document, when we have questions that become very long. Also videos are really important to be available afterwards, so that we or others can try by their own. (+4)
  - I think it is great as it is now. This Q&A document is a great way of engaging people in discussion. Also those who would rather not make questions in live voice sessions. (+2)
  - I think it is pretty good as it is right now. The biggest issue I have is when there is a problem and you ask a question in the HackMD-chat, but it gets misunderstood and then you have to re-ask the question, and it might be misunderstood again, and then you may be stuck on a particular problem for ever. (If you had a conversation with someone, you could easily tell them if they misunderstand what you're trying to ask) (+1)

## Questions

## [Software testing](https://coderefinery.github.io/testing/)

(also questions about other days most welcome)

1. I cannot find the video about Jupyter on YouTube, I see only the introduction and the documentation videos. Will that video be uploaded?
    - thanks for raising this. we will double-check what happened
        - Thanks

2. I still haven't understood where we can find the material of these days and the Coderefinery chat
   - We have the lesson for the current event listed on the workshop page    https://coderefinery.github.io/2023-03-21-workshop/ 
   - Will that link be permanent?
     - Yes I think so. We also have a landing page for past events https://coderefinery.org/workshops/past/ where links to each can be found 
   - There is also lesson page where we list also other lessons https://coderefinery.org/lessons/from-coderefinery/
   - How about the chat?
     - The questions in the HedgeDoc are archived at  https://coderefinery.github.io/2023-03-21-workshop/questions/
     - The chat that was mentioned: https://coderefinery.zulipchat.com/ ?
       - Yes, exactly. You are most welcome to join the CodeRefinery Zulip chat. 

3. Got a small question about last days Sphinx stuff. Where should I ask, here or does it go somewhere else?
    - Here is OK.
    - If the dir structure is one with `docs` and one with `src`, and in `src` I have a `file.ipynb` that I want to show in my sphinx doc (which is now in `docs`). Do you have an example showing such use case? (here: (github repo) is an example where all files are in `root`, which works, but that I would ideally split up into two folders/directories.) -OP
      - Personally I think that a "good" directory structure depends on the project. Then again I am not a developer.
      - I cannot find an example but assuming you are using the "autodoc" extension to generate documentation from docstrings, then you can refer to "src" in your doc/conf.py like this: `sys.path.insert(0, os.path.abspath('../src'))``
      - Right, I found the same, but were not able to get it to work as expected, so I wasn't sure if it was really possible/intended use. -OP

4. I've had to reset my terminal a couple of times during these last 5 days. How do I get the git log from all of the days?
    - the git log stays recorded in each repository and is attached to each repository directory. in other words it does not disappear. you can navigate back to a git repository and type "git log" and it should be there (it gets saved in a directory called ".git" that is at the location of the git repository)
    - Cool. Second question regarding this one... If I can't remember where I saved my different repositories... how can I find their directory haha?
        - Hopefully you can find a good structure for your directories so that it is easy to find. Command like `find` on Linux/Mac help, but you still need to know the [partial] name of the directory. The search button in a files windows on any operating system works too, but you still need to know what you're looking for.
           - on Linux/macOS or Git Bash: `find . -type d -name ".git"` translation: from here and below (the ".") find all directories (type -d) that are named ".git"

5. I have to leave in the last 30 minutes of the Modular code development - I hope that is okay :)
    - Sure. You can always catch up by reading the lesson or watching it on YouTube.

6. With the file sh (or Snakemake) is it possible to use R script and Python script together?
    - Yes. bash scripts (the script.sh example was a bash script) and also Snakemake can execute steps and call other interpreters like R or Python. No problem to have one step using R and another step using Python and yet another using Matlab for instance.

## [Software testing, motivation](https://coderefinery.github.io/testing/motivation/)

7. It is not always easy to make a short test to do what would you suggest for that?
    - First, try to write small-ish functions and test those
    - You can also write tests for larger workflows. It's better to run those manually before releasing a new version or starting a research project.

8. Could the Turing test fall in the category of software testing?
    - In general yes, but it is not possible to automate it :smile:

9. Tests help aligning expectations.
    - Nice summary. And also help to communicate expectations.

10. Tests are code, how do you do to ensure they aren't bugged themselves?
    - Good point. In principle yes, certainly the tests can be buggy themselves. For unit testing, some safety is by construction as each test tests only a small piece of the program. For other type of tests, e.g. regression testing, one rely on a set of reference output that is supposedly the "correct" output.
    - But it is really about communicating expectations (comment 9) so at some point we need to define that this is our expectation and I define this as working/true and derive the rest from that. 
    - Its tests all the way down
      - Hm, deep below I am certain there are a pile of turtles :smile:
    - But it is a great point that we should verify whether the test actually works. One thing I like to do is to introduce a simple error into my code (and later git restore it back) and see whether the test catches it. More than once I created a test and had this confident feeling but the test was never run or was looking "the wrong way".

11. Does that mean that whenever I write a function I have to write the test function?(+1) 
    - That is a good workflow. (But I usually don't, I write a few tests at a time.)
    - You can also start by writing the test. It's often easier to know what the functions should do than it is to write them.

12. What happens (especially in academia) when you have a previously developed software without any testing functionality nor a documentation? Do you write tests for everything, because whatever you do it breaks the program.
     - Best case scenario: you add test and try to fix everything :smile: More realistically try to get the parts you need working and label everything else as "probably not correct"
     - For a larger program, a kind of testing that could be considered in first instance is is function testing where the whole code is tested
     - Someone who had the experience of using previously developed code, I would go for main function testing.

13. Have you tried GitHub copilot or ChatGPT to write tests, given a function?
     - I have :smile: It's especially important to check the code they write... But they are good for writing a template for the test, that you only tweak a little to get it right.
     - I have also tried the opposite: wrote a test first and let the GitHub copilot or ChatGPT write the implementation based on the test.

14. What is the difference of software testing to unit testing?
    - Unit testing is a type of software testing. Unit testing is when you test a single function, class or similar. (A single unit of the code.)

## [Software testing, concepts](https://coderefinery.github.io/testing/concepts/)

15. Do you think you would understand from the testing function what is wrong in the main function code? (of course if something is wrong in the function)
     - the first thing we will notice is that something is wrong and that is already good info. then about what exactly is wrong: maybe we have a couple of tests that test different aspects and maybe 4 of them work and 1 of them fails and based on that we can maybe already deduce where the error might be. this will also guide us towards not making the tests too big otherwise we only know that everything works or everything fails. this guides us towards the right granularity of tests which is a process. it's good to start with something and later adjust. difficult and unreasonable to try to make everything perfect from start.

16. Code coverage: what it means if it is one number is better? How would you do code coverage?
     - if the percentage is higher, then it means a larger portion of the code has been "visited" when running the test set.
     - how to do it: I would use tools like codecov or coveralls
     - would this be for Python? yes

17. Answer to 15 seems not completed?
    - Thanks for notifying. We will have a look and augment the answer
      - yes I got distracted while typing in my office :-)

18. [Here](https://coderefinery.github.io/2023-03-21-workshop/questions/), you have two `Questions and notes from workshop day 4`, and not a single one `Questions and notes from workshop day 5`.
    - Thanks for notifying us. Actually it is published there but both day 5 and day 4 reads as day4. We will fix this.
    - Fixed [Here](https://coderefinery.github.io/2023-03-21-workshop/questions/).

## [Software testing, testing locally](https://coderefinery.github.io/testing/pytest/)

## Exercise https://coderefinery.github.io/testing/pytest/
- You can work on everything on that page, there is one optional if you want.  This is a short test of pytest.
- If you can't do it, it's OK, we do something else next.

**How was the exercise?**
* it worked: ooooooooooooo
* didn't work: 
* needed more time:
* didn't try:
* too much time: ooo
* trivial : ooo

19. It is not working . It displayes the following message:
```bash
pytest -v example.py
========================================== test session starts ==========================================
platform linux -- Python 3.11.0, pytest-7.2.1, pluggy-1.0.0 -- /home/iker/Software/anaconda3/envs/coderefinery/bin/python3.11
cachedir: .pytest_cache
rootdir: /home/iker/CodeRefinery/Software-testing/python-example
plugins: anyio-3.6.2
collected 0 items                                                                                       

========================================= no tests ran in 0.00s =========================================
ERROR: file or directory not found: example.py
```

  - Did you edit a file `example.py` or another Python script?
  - I just copy the script you are giving us.
  - did you save it as `example.py` ?   It can't find it.  if so, are you in the same directory?
  - Yes and Yes.
  - Solved.
     - Good it worked out!
    - Great! Could you give a short explanation what the problem was (in case somebody else has similar problem)?
    - I changed to superuser to do some stuff. i create the example file there. Then I change back to my user for some reason so then it was not working. My fault. 
    - One hint in case someone has problems, first activate coderefinery at anaconda, then go to git bash and activate again the coderefinery and then create the directory and the file. At least this was my case and it worked. And don't forget if you see PS C:> in anaconda to change directory (user/yourname)

20. In the excercise point 4 they introduced a change and showed the output. I don't see in the output what is wrong. assert add(2,3) == 5, it is correct right?
    - We don't see the change.
        - the exercise says notice how pytest is smart and includes lines that failed.
    - I guess they changed `+` to `-`.

21. Again, I had to start with: conda activate coderefinery
    What happens, and do I need to be in the right directory?
    Now pytest -v example.py works fine, but not before the initiation.
    - You need to be in the directory where you want to run the tests, typically that is in a [sub-]directory of your code. By activating the coderefinery environment, the corrects PATHs to the conda, python, and other commands will be set accordingly. My point is that you do not need to be in the coderefinery conda env directory.

22. The solution says that "1e-7 can be a bit arbitrary", but how does pytest.approx work then? Does it not use an arbitrary small constant?
    - It actually just uses 1e-6 by default. You can change the tolerance by adding a parameter. (Documentation at https://docs.pytest.org/en/7.1.x/reference/reference.html#pytest-approx).
    - It is also arbitrary.
    
23. Can the tolerance be passed as an argument to the test?
    - You can pass a tolerance to approx as `1.00004 == approx(1, rel=1e-3)`. (Documentation at https://docs.pytest.org/en/7.1.x/reference/reference.html#pytest-approx)
    - Great, thanks. But could you pass that argument into the test to "finetune" many tests globally?
    - You can add arguments to the pytest call (see https://docs.pytest.org/en/7.1.x/example/parametrize.html). You could also add a configuration file that all tests read to save the parameters.

24. Do I understand this correct that software tests are essentially some particular cases including the ''crazy'', critical ones, e.g. big numbers, large numbers, etc., on which the soft is checked?
    - Yes. They are indivual cases where you can check the output. They never guarantee that the code works in all cases, but if the logic is simple enough (for unit tests), you could cover all possible cases.
        - The same as at the [leetcode](leetcode.com)?
    - It is often better to exclude really weird cases that you don't actually need. For example if one of the parameter is infinity or NaN, the code can just give up and return an error message.

25. What is the -v for in 'pytest -v example.py'?
    - "verbose", it makes it print more about what's going on. Instead of saying that 1 or 2 tests worked, it will then print the precise list of test names and whether they worked or not.
    
26. What if I want to reduce `python -v <name>.py` to `./<name>.py`, is it enough to insert in the Python code the directive `#!/bin/python` or `#!/bin/python3` or so? What about the `-v` option, how to make included in a short version of the python code call command?
    - On most terminals that is enough. On linux and mac, you need to make the file executable (chmod +x filename).
        - Clear. What about the `-v` option? How to I include it in a command `./<name>.py`?

27. Does aiming on high coverage add runtime overhead on the code? LIke defining sum, multiply etc as own functions.
     - It should only add to the test runtime, not the main code.

28. How was it again that i could learn more about pytest/get the help pages?
    - `pytest --help`
        -thanks!

29. I think it would help more to discuss the exercise right after giving time to do them. Having a break right after also having time to do exercises makes the pacing feel a bit slow. (+1)
    - Agreed. I like the format in which the teacher performs the exercise and explains what is happening. And we can follow along if we want. Now when I performed the exercise I have no feedback on it.  
        - incidentally feedback from other workshop we got we got criticized for doing that because then it felt like doing it twice and we were asked not to repeat it again. it is not easy to find a good balanance but some form of discussion where we point out possible pitfalls and go through the essential steps is probably good.
    - Must not be easy to please everyone I guess, appreciate the efforts though! 
    - As co-organizer I really appreciate the feedback and I agree that the pacing then feels differently. One thing we tried to do more of this time is to give more exercise time and less "instructor talking time", based on feedback that last time there was not enough time for the groups to interact and no space for the team leads/ helpers to do anything and they felt under-used and it felt for them like not a good use of their time. But now from an individual learner perspective it can feel slow and "empty" at times. Difficult balance and all feedback appreciated on how to improve and re-balance.

30. Could we do breaks an exercise in one. At least anonce the breaks before the exerciese so we don't have to be back just to here that we are going to a break.
    - Or could we please not? :D
    - Or could we be back, but also get something more than just "ok now break"? Like some reflection about the exercise and the questions that appeared?
    - Can we make a poll for what is best (in the feedback of the day?)
    - Thanks for good suggestions! we should better communicate the plans. One reason why we didn't glue exercise and break into one thing is that at least past experience shows that breaks are then not taken and exercise expands into the break. But I see how it helps to know when to be back for the real content. 
    - Yeah both options have different pros and cons :D Maybe we do a poll? Or some third out-of-the-box solution 🤓

## [Software testing, Automated testing](https://coderefinery.github.io/testing/continuous-integration/)

31. It's fixed, thanks! (+1)
    - better? yes

32. Where is :cat: ?
    - :-)

33. So are supposed to just watch now or? (+1)
    - watching is enough. this is only preparation for exercise

34. Where is the link of the repository on GitHub?
    - For Python https://github.com/AaltoRSE/PyTestingExample and for R https://github.com/AaltoRSE/RTestingExample
    - Using the opportunity to mention GitHub search that can find repositories and users etc.

35. Are they troubleshooting or is this the lesson already?
    - The lesson is currently happening (sorry for the late reply).
        - No problem, but yeah it feels like suddenly this is going at 100 mph

36. Could someone repeat what we are doing? it is too quick
    - Preparing for Exercise CI-1 in https://coderefinery.github.io/testing/continuous-integration/#continuous-integration
    - The steps demonstrated now will be part of the exercise session

37. What is meant by all checks passed in github action? I it the tests that we check locally and is done on GitHub?
    - Yes, precisely. The same tests can be run locally as well as on GitHub.

### Exercise https://coderefinery.github.io/testing/continuous-integration/
- We demoed the first three steps, now try those + the rest yourself
- Do what you can, you can continue later (we don't continue with this later).

**How was the exercise?**
* it worked: oo
* didn't work: 
* needed more time: o
* didn't try:
* too much time: 

38. Why do we not provide the test file name in pytest in step 2? like before? 
    - Because pytest automatically detects tests that are "in the right place". So you only need to indicate a test file if it is not in the expected places. If it's named ``test_<xyz>.py`` it will be used as a test.
        - does it finds test* in current directory
            - if it starts with `test_` yes.

39. What is the file _pycache_? ` (use "git add <file>..." to include in what will be committed)
        __pycache__/`
    - when you run python code, and import packages etc, python creates a cache, and this is put into the `__pycache__` folder. Most repositories actually put this in their `.gitignore` because it's something you don't want in a repo.
    
40. The instructions say to uncomment a line in ```example.py``` but there is no such file in the repo?
    - It should read `test_functions.py`
        - So just "remove" one line by adding # in front of it?
            - Yes. Lines in which the first non whitespace character is # are considered comments by the python interpreter. 
    - But is says "uncomment" and there are no comments in the `functions.py` file
        - Sorry again. `test_functions.py`. 

42. Why the name at the first line is "name: Python application" as opposed to "Python package" in the tutorial? Because there is another option  of Python package in GitHub action.
     - hmmm. I see. I wonder how the starting templates differ. Maybe you can compare both and summarize changes here?     
     - I think python package includes a way to release on PyPI/pip.  Like a library to be reused.

43. A comment: The R testing instructions have a trailing "\`" at the end "Rscript -e 'testthat::test_local()'\`"
    - Thanks for reporting 

44. I'm on step 3 and I'm trying to enable the automated testing, but when I pushed the commit, I got this error message: The 'HampusRN/example-ci' repository doesn't contain the '.github/workflows' path in 'main'. Why?
    - and that file exists locally on your computer? and it has been "git add"-ed and committed?
    - Nope! I don't think I saw any step about that, let me check...
       - ah wait sorry my answer above was misleading. in the instructions we commit via the web interface after selecting a starting workflow (the green button "Commit new file")
   - Okay; regardless, now I seem to have the file anyways, although I got the error message... strange!
       - let me look ... yes looks good now

45. I'm on Step 3 and the Github page has the below lines 
         permissions:
          contents: read
     appearing before the jobs: ; should I push it down under the jobs: or insert the line 'pull-requests:      write' after the permissions: whereever it is ? 
    - Just add it wherever the permissions are set. - thanks !

46. Automated tests pass, but I do not see any coverage.xml showing up. 
    - The coverage doesn't show up anywhere but in the action if you push/commit directly to main. We intentionally did not add things like codecov. If you want a coverage report you will need to create a pull request to your main branch. Then a report will be generated and shown in that pull request.
        - I tried pulling to main too, but this also does not create a coverage file. The pull succeeds with the message that everything is up to date. Would that be a wrong configuration then?
            -  Pull request, not "git pull" , i.e. you have a branch that you try to pull into your main. 
                -  I see, thanks!
            
47. I'm doing the R version. Does subfolder tests go under rtestingexample/R or under rtestingexample? 
    - rtestingexample/tests, as in the template.
        - checking ...
    
48. The last [instruction](https://coderefinery.github.io/testing/continuous-integration/#fork-and-clone-an-existing-example-repository) of Step 1: if we created our own repo and cloned, then why do we need to fork and clone an existing example one if it's exactly the same? Where to clone an existing example repo, into our own created repo?
    - You don't that's the alternative approach.
        - OK, I don't remember this was mentioned.

49. git question: if i do git status it checks if my git is up to date with my local repo. How do i check if it is up to date with my remote repo (github)?
     - You need to pull in from the external repo first. If you have files that are being edited, and therefore risk to be overwritten by the pull, git will prevent the pull to go through.

50. The page has: "Next uncomment the code in example.py under “step 5”". But there is no **example.py**. Did you mean **test_functions.py**?
     - Sorry. outdated instructions. This file is now called test_functions.py. I will open issue at our lesson repository.

51. Where is the template: see question 47?
     - working on it ...
         - https://github.com/AaltoRSE/RTestingExample

52. In step 3 the coding modifications are not similar to what I have as template, there are no permissions section so do I have to add it as is?
    - if in doubt: Just copy the complete action. 

54. Why can I not create issues in the forked R testing repo? The bottom is deactivated?


## [Automated testing, test design](https://coderefinery.github.io/testing/test-design/)

53. Is it possible to carry out automatic testing in a repo with several languages. E.g. python, R, bash? 
    - Yes it is. Combining Python, R, and bash tests goes fine. One common combination is that you have automated testing for the code (in Python, R, C++ or other language), and also for building the documentation (for instance Sphinx-based documentation)
    - Any references I could use? I have an untested repo written mostly in R, but with some python and bash functions and I would like to implement this.

54. In step 3, we get an error for the command ` pytest --cov-report "xml:coverage.xml"  --cov=.` . Error:  pytest: error: unrecognized arguments: --cov-report --cov=. Error: Process completed with exit code 4. Is there anything that we are missing?
     - There is a package missing in our https://github.com/coderefinery/software/blob/main/environment.yml I think. sorry for that. creating an issue.
      - This is locally, right? Or on github? It was run on github
      - It seems that pytest-cov is missing in the environment
        - My bad, sorry. Didn't think about adding it to the env when creating the tests.

55. I can understand how to test functions, but how would you test a GUI?
    - There are frameworks for this, but in my experience it's never very easy. You can test the functionality by testing the functions that are triggered when the user clicks a button. But to test the actual GUI, you would need to use something that automates mouse clicks and detects where to click.

56. Should we complete the exercise till step 11?
    - If time allows, yes please do so

57. Could you give an example of integration testing?
    - If the program is a physics simulator, for example, an integration test would start from a given setup, run for a realistic amount of simulation time and check the output.
    - You could run an integration test for the Pi calculation we used earlier. This would mean checking that the output of the whole program is close enough to pi after a large number of steps.

58. "Create Coverage" has not been run in my repo. Is this correct or did I push incorrectly?
    - if you push, it won't run. It only runs 

59. Very useful exercise to know how push, pull and merge branches work with git(-hub)!

## Modular code development starting questions

We will start here: https://coderefinery.github.io/modular-type-along/

A. What does "modular code development" mean for you?
- No idea what modular stands for... (+4)
- Build codes as shorter pieces/modules that are easier to test, fix and reuse (+4)
- Dividing your project into segments, each with their own purpose (+2)
- Moving away from large, linear scripts, and moving towards dividing scripts into functions and classes within 'external' modules (+2)
- Modules, almost like lego blocks, that can be put together in different systems so that they are not statically connected to the system. Aka you can take some of it and use it elsewhere
    - They are not **blocks**, but **bricks**! :D
        - Oh wow, how important :D
            - I live in DK, and, trust me, arrogant Danes wouldn't be happy :D :D :D
- Self-contained functions (modules)
- Structured codes developed in a sequential and proper way

- Developing different chunks and then "merge" them so they can work together in a task.

B. What best practices can you recommend to arrive at well structured,
   modular code in your favourite programming language?
- Still don't know what it is (+1)
- Start with pseudocode to define my problem/idea
- Break down your parts first into e.g. classes and modules that will make sense and then do pseudocode (+1)
- Think about what processes/algorithms/equations you might use more than once, then make it into a function. If you use this function in more than one script, maybe make it into an external module
- No concrete idea. Would be nice to get to know some best practices, if possible


C. What do you know now about programming that you wish somebody told you earlier?
- Use an IDE instead of nano... (-4) (+1)
  - How 'about: "In addition to Nano"?
  - Instead of Nano, there is Vim :D
    - And there is Emacs.
- Breaking up problems into small boxes that can easily be addressed on their own (+1)
- What CI is! so many have been talking about this and I never really understood it before now (+1)
    - I have the same feeling about Python & C++. I learned C, bash, Perl, Wolfram Mathematica, but never reached neither C++ nor Python, but they are so popular in softdev & research, respectively
- Learn about time and space complexity (+1)
- That I should just start using python instead of MatLab even though the university were using MatLab when I started (now they use python). (+2)
    - MatLab? Python? Better try Wolfram Mathematica ;)
    - Noo, matlab is the best :D :D :D (+2) (-0o2)
        - Well, I like MatLab in itself, but companies here all use Python as a standard, since it is free - so much more versatile and usefull in that sense (more uses it). (compared to MatLab)
            - It depends on the company; e.g. Ericsson uses C/C++
                - Well, I was comparing to MatLab :) MatLab can be better in some cases than Python, but I still wish I learned the other because it is free and therefore used more widely (I also think it is a bit easier to go from python to MatLab than the other way). Currently I use both, but are most comfortable in MatLab!
- The importance of proper documentation, ways to do debugging and that we should try to make it open source and shareable
- Some hold that readable code is better than good code. My recommendation is to comment more rather than less. (+1)
- It is possible to break up files into smaller functions too much, a project can become unreadable given too many files.
    - [From viewer, not staff] That sounds interesting, could you expand?
    - [Reply] I worked in an industrial project with literally ≤15-line program files, written by a coder who separated files way too much. It was not possible to grasp what the files were doing.
        - [Reply] I see, that's a good point, thanks!
- Revise your code regularly, as you go along
- How to develop large projects, how to write makefiles, how to code in C++, how to get used to classes and OOP in general, a proper, convenient code dev app with GUI, how to use git, what are templates, what are function pointers ...
- Learn how to use APIs

ℹ️ Here is now some amount of discussion between defferent tools. Let's remember the code of conduct and let's not speak bad of any tool. There are plenty of different tools available and they all have their use cases + people can have their favourites even tho they are not the most handy in your opinion.


## Questions/suggestions on what we should do next

60. How do i download the temperatures.csv from the Github page? 
  - go to here: https://raw.githubusercontent.com/coderefinery/modular-type-along/master/data/temperatures.csv then right click -> download
  - or: using wget: `wget https://raw.githubusercontent.com/coderefinery/modular-type-along/master/data/temperatures.csv`


61. there is a typo in the plot_temperatures function
    - It was already fixed

62. should your plot_temperatures function also get a mean as input?
    - yes! great input

63. Should this also be made more general by using the FMI API? For example giving only the timeframe to download instead of a specific file which the user could not have.
    - What does FMI stand for?
        - Finnish Meteorological Institute
            - ah yes! :-)
            - I would be interested to know how to implement this, but I think it might be out of the scope of the course?
                - https://github.com/pnuu/fmiopendata (Python only)
                - Thank you!


64. Perhaps tell plot_temperatures function how many num measurements to use to calculate mean
      - Thanks! We inferred this information from the length of the list

65. Plot_mean has a typo in the argument given.
      - Thanks

66. Where would you say the balance between rigid functions and customizable functions are? (I know it depends a bit, but a small discussion maybe?) e.g. what about making it possible to change the color for each plot? Line type? etc.
      - Great question. it is a process.

67. I'm missing the tests in this script or are the test in a separate script?
      - Nice suggestion. noted. We will get there.

68. Does the order of defined functions matter? For your example you can call the plot_mean function (in the second plot_data_and_mean function) because you've created it beforehand, right?
       - in our case the order of functions does not matter
           - So it will still work if you reverse the order of the functions?

69. Why not to add mean as an argument to plot_data (and thus plt.axhline into plot_data)?
    - Thanks

70. Is it not required to have a main() function as the entry point ? Is it not a best practice?
    - Good advice. noted. we will get there.

71. typo: "indputfile" in the read_data function.
    - Thanks

72. In Python, functions `sum` and `len` are available by default, not as a part of another package like, e.g. `plot`, are they not?
    - Yes

73. num_measurements in the function read_data is not an input of the function. Shouldnt this be an input?
    - Solved

74. Labels only shown in the first plot?
    - Thanks! Fixed

75. Perhaps it's good to name the file other than 'Untitled.ipynb'.
    - Thanks

76. Separate functions & other elements in different cells in Jupyter. Split can be done with `ctrl`+`shift`+`-` (at least in mac)
    - Thanks I will raise this

77. Figure could have a grid() added for clarity
    - For many scientific journals, grid in plot is considered as bad manners

78. In Python, is it possible to customise plot labels, legends, ticks, e.g. their font, size, colour, log base for log scale?
    - Yes, with Matplotlib.
        - And also other things, e.g. plot range, plot sizes ratio, figure frames, customised line colours, thickness, dashing, symbol types?
            - You can do a lot of things with it: Check https://matplotlib.org/ for examples.
            - https://matplotlib.org/cheatsheets/
    - Suggested learning material for Matplotlib https://aaltoscicomp.github.io/python-for-scicomp/ and
https://aaltoscicomp.github.io/python-for-scicomp/data-visualization/
    
79. How about we add some docstrings and demonstrate the Python help function?
    - An excellent suggestion!
      - mentioning here that you can add docstrings to functions as
        ```python
        def function():
            ```
            docstring describing what the function does
            ```
            code inside the function
        ```
    - You can also see the [pandas docstring guide](https://pandas.pydata.org/docs/development/contributing_docstring.html)

80. It seems you are running temperature plotting file which should not exist anymore?
    - o no. I think the file has changed name

**Unfortunately points 81 - 90 got lost while migrating contents to the archive HackMD**

90. Nobody is calling the main() (+4)
    - Thanks :-)
    - We always need at least one functions with side effects
    - And a few more eyepairs watching the same code always helps
    - "This was all planned"

91. `if __name__ == "__main__":`
    - That would have been good. but is very python specific so we won't focus on this one too much
    - Would be nice to have this explained here tho 🤓
        - This is a good resource: https://realpython.com/if-name-main-python/ 

92. Show line numbers in the notebook's cell (+1)
    - Is it actually possible?
       - I think it is but I don't remember how

93. break: now. 
     - Thanks

94. Should the version be specified?
    - For long-term usage a good idea, for development where you are ready to fix things that go wrong, leaving off is OK.

95. When should you include `requirements.txt` and when `environment.yml`?
    - Great question. Either we will discuss or somebody can comment
    - requirements.txt is Python only, so that might make some choices easy.  Though other languages have their own things.
    - environment.yml has more in it: conda includes other libraries, so is more self-contained and portable.  Often, environment.yml is used for scientific stuff.

96. Is there an option to create the `environment.yml` automatically?
    - There are ways to export what is currently in the environment.`conda env export --from-history` is interesting since it makes an environment.yml file out of just what you actually asked.

97. I have a question about environments in Linux. Suppose, I've created a conda environment and have activated it. From now on, each software package which I install, e.g. via `apt`, `pip` etc., is a part of only this environment and won't be available of I deactive the environment?
    - Close, but only for `conda install` and `pip`.  Other things like apt don't know about it.
    - conda: `pip` and `conda` use it (probably things for other languages, too)
    - python virtualenv: only `pip` uses it.
        - right ... so, if I want another person to have my environment, then I save it via, e.g. `pip freeze > requirements.txt`, send the result file to that person, and then he restores my environment on his machine by `pip install -r requirements.txt` -- does it work like this?

98. Is it better to have several files with one function each of a single file with all the functions?
    - This is a question of preference and depends to some extent on language. For example, in R you should have one function per file. In Python, a file is a "module", which is usually a collection of related functions and classes.  
        - And in C / C++, it's even two files: *.c / *.cpp and *.h ...
    - Ah ok, I work a lot with R too, and I think it is usually better to have individual files, but then you need to source each file at the beginning of the script. I normally do it by iterating through a list of files, but not sure if there is a better way to do it, equivalent to from in Python.
      - In Python (and some other languages), you can have a `__init__.py` file in a folder. Then you can `import` the _folder_ and that will actually import the `__init__.py` file. You would often have multiple `import` statements in `__init__.py` that import the most important things. So this allows importing many files in one go.
      - Sounds interesting, I will look into possible alternatives of this for R then. Thank you! :)
        - Guess this is a package in R? Or maybe there is something in between a package and an individual function file.
        - It is more like a pipeline. I have a bash file that test command inputs and calls R scripts that contain the pipeline, but inside the pipeline I have several functions written in separate files. 

99. Often I receive a (jupyter) Python code with all modules that need to be imported and all functions defined in the first cell. I continued this practise, but is it better to write functions in unique files instead of in the first or second cell?
    - If the functions can  be reused in a different jupyter-file, I would suggest moving them to a separate file. That way you can develop and test them in one place.

100. Why are there files in Python with names starting & maybe also ending from/by the underscore or even two? Do they have special meaning? E.g., `__init__.py`, why not just `init.py`?
     - Often Python uses two underscores for names that are "part of the language", or that the user never writes directly. So you never import `folder.__init__`, you can import `folder` instead. If a class has a function called `__init__`, you don't call it. It gets called when you create an object of that class.
       - For another example, `__str__` can be function in a class. It will be called when you try to convert it to a string. So if you print an object of the class, Python will call the `__str__` function.
     - A single underscore in front of a name hides it. When you ask Python to list the functions in a file, it will not list functions that start with `_`.
     
101. Is it really necessary to test functions that come from a library i.e. functions you did not create yourself?
     - typically not necessary

102. Maybe a better test for a file like this could be something like if the file includes a column "temperatures" at all etc.
     - Thanks, good suggestion

103. Wait, what was the @click? I missed it.
     - It is one of many libraries that can add a command line interface to Python: https://click.palletsprojects.com/
         - Thanks! Not heard of it before :)
            - other alternatives for Python: docopt, argparse, optparse

104. If you have time keep going with the current session, interesting to follow :D 

105. Can I seek support if not from Aalto?
     - The CodeRefinery Zulip chat is a good and active channel. You are welcome to join at https://coderefinery.zulipchat.com/ Please refer also to the discussion at Icebreaker question #3 in the top of the document for mentioning of local support at other universitites.

## Feedback, day 6

We will paste a Zoom here that you can join to talk to the instructors, after we are done.
- We hope that you had a good workshop and we got you started on a good path.  There is so much more to learn, and we hope you can keep working.

Today was (multi-choice):
- too fast: oo
- too slow: o
- right speed: oooooo
- too slow sometimes, too fast other times: ooooooooooo
- too advanced:
- too basic: oo
- right level: ooo
- needed more exercise time: o
- needed less exercise time: 

For the course (multi-choice):
- I learned things I will use: oooooooooooooooooooooooo
- I would recommend this to others: ooooooooooooooooooooo
- I should have taken this earlier: ooooooooooooo
- I shouldn't have taken this earlier:

One good thing about today / this course:
- That automatic debugging tool in GitHub seemed very cool and useful! (+2)
- The concept of testing and how to design a test (beyond just checking that code compiles and runs)
- pytest
- Reiterating over use of git commands for github, git push, pull, merge etc. (+1) 
- A nice glimpse into many useful tools.
- Overall the course was really great! Many thanks for putting the effort to make such nice content and for free to everyone! (+1)
- Modular coding is very smart, I should have started earlier with it
- Github actions
- Accessible intro to Git/version control for people without a dev background

One thing to be improved about today / this course:
- I would have liked to learn more and understand more about the debugging tool in Github. Now it felt like we just pushed a lot of buttons and copy-paste:d some code. I would not feel confident I could set it up myself for another project: o (+1)
- One thing that could be improved with the course, according to me, is more going through what is good and common practice. Sure it is good to learn all different things git can do, but I still don't feel confident what I *should* do. For example, should I always fork first, clone later, make modifications locally, then push to fork, and then make a pull request? Is that what everyone does? (+1)
  - We hope to have a "workflows course" someday that would show more of these actual practices.  We're having trouble finding time to prepare it, though...
      - That would be great!! :D (+2)
  - I personally would recommend to fork for larger projects with multiple collaborators. If it is your own project (even on a shared group-repository), just cloning and pushing/pulling is perfectly fine.
- Honestly today was the day that I felt more disconnected to the content. The *just watch* mode of teaching when writing code live is not so engaging. (+1)
- It felt like we didn't properly talk about common beginner's mistakes, so that could be improved. With multiple problems I had, the answers were a bit like "oh so you did <this obvious beginner's mistake>? You shouldn't do that", which could have been avoided if we simply had talked a bit more about common things one should *not* do.
- I would like to understand better how to use Python coverage and how to create GitHub workflows.
- It seems we skipped a large part of testing (test design). 
    - Yes, we did move over this pretty quickly. We did discuss some possible approaches to some of the issues, but didn't have the time to go into all details. Feel free to do the exercises for the Test development part, the solutions also give quite some information.
- I think git practice is the main motivation of joining the workshop, so a slight increase in focus on using that in all the extra things we learn here, so that we get more familiar with the different steps of pulling, pushing etc. (+4)
    - An idea could be to give a bit bigger assignment/exercise here in the end, that learners could do in the following weeks after the course (git heavy of course), and then have one day of lesson in 2-3 weeks, where you follow-up on that exercise.
- It would have been nice to talk more about git-integration with other things, like overleaf, matlab, eclipse, etc.

Any other comments:
- Thanks for everything, this workshop was really great and I learned a lot! (+10)
    - Not sure about "learned" a lot, but certainly "saw" and "heard about" a lot, so now I'm excited to elaborate more on these topics (+2)
- Having attending a bunch of other workshops on GitHub this was by far the best! I honestly feel that I learned in 2 weeks what I've been struggling to learn 2 years :P Thanks for everything (teachers and the support team alike)! And thanks so very much for uploading the recordings too - I takes away the stress of trying to digest everything during the lessons. Oh, yeah, and the cat :cat: 
- Great teachers :) (+9)
- Thank you for the workshop, I've learned that I should have been using Git all along! :')
- Although the descriptions that are available for people to read are helpful, talking about them at the considerable length that was done might be time that is better spent on the exercises and walkthroughs. (+1)
- This (modular coding)  actually gets just started if one person publishes more than one project containing code. First, how do you manage complex dependencies; how do you transfer parts of a project to the next saving copying/retyping the code.  
- Do you have more courses during summer which also provides study credits?
- What should we do next as a participant in Finland to get the course credits?

Suggestions about the course format:

- Maybe add Zoom-help in the breaks (or at some other point)? Some problems were really hard to solve in the chat, verbal communication was needed.
    - There were several helps organised by individual universities. We did in the past offer general zoom help for registered users, but the rooms essentially were quiet all the time, so we stopped doing it and moved it to the universities.
- This was great overall, I need to stress that. But I do think the daily schedule could be shorter, either by less/shorter pauses, by splitting across more days, or something alike. This takes a lot ouf a working day.
- It would be great to have compact cheat sheets for material from earlier days (e.g. how to push things correctly to GitHub, how to use branches, ...) that is used again in later lessons. It is kind of difficult to find this type of info quickly while working on a problem. (+4)
- I think it worked great the way it was. Thank you so much for this! Would just love to have a mentoring/help session in a few weeks so could have time to test these things on our real projects.
- The code checkpoints in the examples were a great idea. As in, newbie students who accidentally broke something git-wise, could catch up to the main workshop by cloning working checkpoint examples. (+1)

- I'm still confused about who we are supposed to email for the certificate? (I am from the University of Helsinki) I've got the instructions of the "homework" but it just says return via email?
    - On the website it's written: Your submission can then be sent via email to scip@aalto.fi by the 15th of April 2023 and you will receive the certificate by the middle of May.
        - Ok thanks!
