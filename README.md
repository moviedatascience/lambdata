# :heart_eyes:	 Packages guide :heart_eyes:

## This is a step by step guide to creating, pushing, and testing a repo that contains packages, classes, and utilities

###### Disclaimer: Windows only, things will be different (read: easier) in linux or macOS :sweat:


[Day 1 package creation walkthrough](#create-package)

[Useful Definitions given on Thursday](#useful-definitions-or-example-questions)

# Create Package
1- In Git Bash check to make sure you have conda and pipenv by typing:

- `which conda`

- `which pipenv`

2 - create a repo in Github.com with the following features:
  * Name

  * MIT License

  * README file

  * Public

  * Python gitignore

3 - Navigate to the github repo url, copy url, and run the following cmd into git bash:

 - `git clone <https://github.com/moviedatascience/lambdata.git>(copied URL)`

4 - Change directory to lambdata by running the following code in git bash:

- `cd lambdata`

5 - Open in atom by typing in git bash:

- `atom .`

6 - Create pipenv by running the command:

- `pipenv install numpy pandas`

Reminder: You can edit the Pipfile manually, but

***Never edit the Pipfile.lock file, that's very bad***

7 - Push the updates to github by running:

- `git add .`

then

- `git status`

then (once your updated files have all turned green)

- `git commit -m "some update message"`

- `git push`

8 - Configure the git repo?? (honestly not sure why this is a thing)

- `git config --global user.name "moviedatascience"`

- `git config --global user.email "moviedatascience@users.noreply.github.com"`

- `less ~/.gitconfig`

9 - Create the package directory by running the command:

- `mkdir lambdata_moviedatascience`

Then nagivate into that directory by running the command:

`cd lambdata_moviedatascience`

10 - Create the initiation file by running the command:

- `touch __innit__.py`

*the __init__.py file lets people know that the folder is a package*

**you can also just manually add files via text editor**

11 - Add docstring at the top of your __init__.py file

12 - Import pandas as pd and numpy as np into your __init__.py file

13 - Add sample code of ONES and ZEROS

  -  #sample code

    ONES = pd.DataFrame(np.ones(10))

    ZEROS = pd.DataFrame(np.zeros(50))

  -  *Global variables are in all caps*

14 - Launch subshell by running command either in anaconda prompt or atom prompt:

-  `cd lambdata`

-  `pipenv shell`

15 - Check that your package can be imported and read by testing:

-  `import lambdata_moviedatascience`

-  `lambdata_moviedatascience.ONES`

-  `from lambdata_moviedatascience import ONES`

and run those to verify

16 - Go back to git bash and create a utility file by running:

-  `cd lambdata_moviedatascience`

-  `touch df_utils.py`

17 - Add the following to your df_utils.py file

-  """" utility functions for working with dataframes"""

          import pandas

          TEST_DF = pandas.DataFrame([1, 2, 3])"

18 - Go back to anaconda prompt and run:

-  `from lambdata_moviedatascience import df_utils`

  *Just checking that it can be imported here*

19 - Go back to git bash and add the new files you've created:

-  `git add lambdata_moviedatascience/`

-  `git status`

-  `git commit -m "added some proof of concept utility functions"`

-  `git push`

20 - Create test pypi account at:

<https://test.pypi.org/>

21 - Install twine in your anaconda prompt using:

`pipenv install -d twine`

22 - Create the setup.py file in the lambdata directory:

`touch setup.py`

### Note: setup needs to be under the parent directory as it allows users to install the package

23 - Add the following text to the setup.py file:

```
"""
A collection of DS helper functions

"""

import setuptools

REQUIRED = [
     "numpy",
    "pandas"
]

with open("README.md", "r") as fh:
   LONG_DESCRIPTION = fh.read()
   setuptools.setup(
   name="lambdata-moviedatascience",
   version = "0.1.1",
   author = "moviedatascience",
   description = "a collection of data science helper functions",
   long_description = LONG_DESCRIPTION,
   long_description_content_type="text/markdown",
   url="https://lambdaschool.com/courses/data-science",
   packages=setuptools.find_packages(),
   python_requires=">=3.5",
   install_requires = REQUIRED,
   classifiers=["Programming Language :: Python :: 3",
   "License :: OSI Approved :: MIT License",
   "Operating System :: OS Independent",
   ]
   )
  ```

24 - Create package using Twine in anaconda prompt:

```
python setup.py sdist bdist_wheel

```

25 - Use twine to upload

`twine upload --repository-url https://test.pypi.org/legacy/ dist/*`

Then enter your username and password from the test pypi account you created earlier


26 -
27 -
28 -
29 -
30 -
31 -
32 -
33 -
34 -
35 -
36 -
37 -
38 -
39 -
40 -


# Useful Definitions or Example Questions

---

* What does a __constructor__ do in a Python class?

  * Used to initialize a class

* Why would you use __inheritance__ in one of your scripts?

  * To reduce the amount of code you're writing and cuts down on the amount of code copying you need to do.

* What is the syntax for using __inheritance and instantiating a new class__ from a parent class?

  * Class TicTacToe(Game):

* What are the benefits of using __docker__?

  * Allows you to test in a virtual environment without breaking something important

* _Unit Tests_ are better because they save time by running all functions at once instead of running each function one at a time.

  * also helps on larger projects when you change code to make sure your original code still works
