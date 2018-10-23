# Heroku Deployment Checklist

## Deployment Checklist

### Dynamic Port Binding
Heroku tells us which port our app will use, 
so we need to make sure we listen to the port 
they tell us to
E.g. create PORT in index.js
    const PORT = process.env.PORT || 5000;
            ||
            ||
            \/
### Specify Node Environment
We want to use a specific version of node, 
so we need to tell Heroku which version we want
E.g. insert the following item to package.json
    "engines": {
        "node": "10.10.0",
        "npm": "6.4.1"
    }
            ||
            ||
            \/
### Specify start script
Instruct Heroku what command to run to start
our server running
E.g. insert the following script to 'scripts' 
in package.json
    "start": "node index.js"
            ||
            ||
            \/
### Create .gitignore file
We don't want to include dependencies, Heroku 
will do that for us

## First Time Deploy

# Create Heroku account
            ||
            ||
            \/
# Commit our codebase to git
E.g. using the following commands
    git add . 
    git commit -m "initial commit"
            ||
            ||
            \/
# Install Heroku CLI and Create App
            ||
            ||
            \/
# Deploy App with Git
E.g. using the following commands
    - login to heroku: heroku login
    - create heroku app: heroku create
    - push codebase to heroku: 
        + git remote add heroku https://git.heroku.com/powerful-sierra-33750.git
        + git push heroku master
            ||
            ||
            \/
# Heroku deploys project

## Subsequent Deploys

# Commit codebase to git
            ||
            ||
            \/
# Deploy App with Git

https://powerful-sierra-33750.herokuapp.com/
https://git.heroku.com/powerful-sierra-33750.git

