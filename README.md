# Lab Coding Practices/Onboarding

## Intro
This README compiles the coding practices that we **should** use in the lab. Do as I say, not as I do or something like that - but I am actively updating repositories towards following these guidelines. In addition, this repository will include information about the software we have in the lab, what they are used for, and links to each repository for easy access.


## Coding best practices
There are a few coding standards I've learned which make code readable and correct, and technical documentation systematic and light-weight. I have seen these standards enforced first-hand in industry and recommend a read.

Since its not set what the best format for organizing code is, for now I will just refer to a link which has a few of the many standard practices in readable code: https://code.tutsplus.com/tutorials/top-15-best-practices-for-writing-super-readable-code--net-8118


### Visual Studio Code - Great code editor for almost everything
I highly highly highly ... highly recommend using VSCode as it supports many useful extensions and languages, is fast, has an integrated terminal, and can connect to servers and its file system. I talk a bit more about extensions below but here's a list of useful extensions for our use case:
- Black and Flake8 - formatter and linter discussed below.
- Rainbow CSV - we use CSVs a lot and this makes CSVs much easier to read in a text editor.
- Remote-SSH - SSH to server; can connect to sol and sunlab, as far as I've tested. Haven't gotten corona66 to work.
- Jupyter


### Formatters and Linters
I cannot stress how efficient it is to use a formatter and linter while writing code. A formatter automatically adjusts your code to adhere to a coding style - it ensures your code is *consistently formatted*. Issues with indentation, spacing, braces and parentheses are a thing of the past with formatters. For python I recommend a formatter called Black.

Linters analyze your code for potential errors and stylistic issues:
- Syntax errors
- Overweight code - patterns in code that can cause maintainability issues (e.g., unused variables, overly complex methods etc.)
- Potential bugs - e.g., logic errors such as always-true/false conditions
For linter, I recommend Flake8


### Pytest
https://docs.pytest.org/en/stable/

For python code, we really should be writing unit tests for everything. Especially so if you're "guiding" your code writing with a bit of AI here and there. Please use pytest - you write small, isolated unit tests for **EACH** of your individual functions and pytest will find those unit tests, the associated function that it tests, and run them for you. Not only will pytests help you make sure your code (or chatGPTs) is actually behaving as it should, it also lets OTHERS know that you know it works.

The way pytest works is it will automatically look for any files whose name has "test_.py" or "_test.py", and also looks for any functions that start with "test_". Within the function, you use assert() to test a behavior. In addition, you can use *fixtures* which basically add variables with a certain value to be used in your tests.

Just do it.


### Diataxis for documentation
Follow this link to learn more: https://diataxis.fr/#

Diataxis is a system that differentiates the *different forms* of technical documentation and how we approach them. Copying from the website:
"Diátaxis identifies four distinct needs, and four corresponding forms of documentation - tutorials, how-to guides, technical reference and explanation. It places them in a systematic relationship, and proposes that documentation should itself be organised around the structures of those needs.
Diátaxis solves problems related to documentation content (what to write), style (how to write it) and architecture (how to organise it)."

In fact, one procedure I was **encouraged** to do at Moderna was to copy the relevant diataxis page into chatGPT and have it write documentation for me in the language of diataxis.


### Version control with git
We don't use git in this lab as often as we should. Here's a quick rundown of git, what it does, and how it's used: https://rogerdudler.github.io/git-guide/

The key to using git:
- Commit often
- Use branches for features, bug fixes, experiments, etc and merge them.
- Encourage code review with pull requests.

### Environment management
You might find that having the wrong version of something is an extremely common occurrence in this field. Do you and everyone else a favor by using **virtual environments** and exporting the environment.yml file for others to use. This prevents *you* from having multiple competing versions of something, and helps *others* easily rebuild your specific environment to run your code.

I recommend using conda for this: https://docs.conda.io/projects/conda/en/stable/#
Or better yet, exporting your entire environment as a container to docker! https://www.docker.com/resources/what-container/


## Contact
If you would like more resources on anything else related to coding practices, you can contact me at jzt320@lehigh.edu. I'm more than happy to share tutorials, discuss our lab's software and work, or do some pair programming. Feel free to also contribute your thoughts here.