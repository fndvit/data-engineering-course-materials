# Week #9 - Running R scripts

## R on Heroku

1. Create a new directory for your project with a `hello.R` file in it. 

    ```r
    print("hello world")
    ```

    And an *empty* `init.R` file (this will indicate to the Heroku R buildpack that this is an R project). 

    Your project directory file tree should look like this

    ```
    yourprojectdir/
    |- hello.R
    |- init.R
    ```

2. Initialise this directory as a git repo, commit your R files
3. Create a new Heroku app and use the Heroku CLI to link your local repo to Heroku (instructions on your Heroku dashboard)
4. Add the R buildpack to your Heroku project

    ```python
    heroku buildpacks:add https://github.com/virtualstaticvoid/heroku-buildpack-r.git
    ```

5. Deploy the app to Heroku
6. Manually run your R script on Heroku. You should see the output in your terminal.

    ```
    heroku run Rscript hello.R
    ```

## R in Python

1. Add an app.py file to your project:

    ```python
    import subprocess
    import os   

    this_file = os.path.abspath(__file__)
    os.chdir(os.path.dirname(this_file))

    subprocess.run(["Rscript", "hello.R"])
    ```

    Your project directory file tree should look like this

    ```
    yourprojectdir/
    |- app.py
    |- hello.R
    |- init.R
    ```

2. Run your Python script and you should see the output from your `hello.R` script
    - Windows you'll need to add your R bin folder to PATH (ask me for help with this)

## R in Python on Heroku

1. Add Python to your Heroku buildpacks list:

    ```python
    heroku buildpacks:add heroku/python
    ```

2. Commit your changes to git if you've not already
3. Deploy your app
4. Manually execute your Python script on Heroku and you should see the output of your `hello.R` script:

    ```python
    heroku run python app.py
    ```