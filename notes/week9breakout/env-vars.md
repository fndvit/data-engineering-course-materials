# Week #9 - Environment variables

1. Create an app.py file to read an environment variable

    ```python
    import os

    TEST_VARIABLE= os.environ.get('TEST_VARIABLE')
    print("TEST_VARIABLE: %s" % TEST_VARIABLE)
    ```

2. Run this file to demonstrate that the environment variable is not set (outputs `None`)

## Setting environment variables in your VSCode environment

1. Open this project folder in VSCode
2. From VSCodes command pallette:  `Debug: Open launch.json`. Replace the contents of your `launch.json` file with the following:

    ```python
    {
        "version": "0.2.0",
        "configurations": [
            {
                "name": "Run application",
                "type": "python",
                "request": "launch",
                "program": "app.py",
                "console": "integratedTerminal",
                "env": {
                    "TEST_VARIABLE": "thisisatest"
                }
            }
        ]
    }
    ```

3. Run your file using the *Run* menu (Run → Start Debugging). You should see from the output that the environment variable has now been set.

## Setting them from terminal (OSX and Linux only)

1. If you're not using VSCode you can set the environment variables manually before running the application on the terminal. Run this on your terminal:

    ```
    TEST_VARIABLE=thisisatest python app.py
    ```
