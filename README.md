## This is a step by step guide to creating, pushing, and testing a repo that contains packages, classes, and utilities ##


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

-  *Just checking that it can be imported here*

  19 - Go back to git bash and add the new files you've created:

-  `git add lambdata_moviedatascience/`

-  `git status`

-  `git commit -m "added some proof of concept utility functions"`

-  `git push`

  20 -
