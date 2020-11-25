# Cloud API with Heroku

We're going to use Heroku to host our API in the cloud to make it accessible from anywhere.

## Steps

1. Create account at [https://www.heroku.com/](https://www.heroku.com/)
2. Create a new app
3. Download the [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)
4. Add the *requirements.txt* and *Procfile* files (from this directory) to your api project directory.
    - *requirements.txt* - tells Heroku which third party libraries are required
    - *Procfile* - tells Heroku how to run your app
5. Deploy your app to Heroku. You should see instructions in your dashboard looking similar to this:

    ```python
    heroku git:remote -a <your app name>
    git push heroku main
    ```
6. Your dyno should now be started and running. You can see any logs (build logs and the messages you normally see in your terminal) by clicking *More → View Logs* from your Heroku dashboard.
7. Try to load one of your endpoints (click *Open App*) from the Heroku dashboard to link to the base URL, then add your endpoint to this.
