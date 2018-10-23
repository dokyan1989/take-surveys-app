# Heroku Deployment Checklist

## Deployment Checklist

### Dynamic Port Binding
Heroku tells us which port our app will use, 
so we need to make sure we listen to the port 
they tell us to
E.g. create PORT in index.js
    const PORT = process.env.PORT || 5000;

### Specify Node Environment
We want to use a specific version of node, 
so we need to tell Heroku which version we want
E.g. insert the following item to package.json
    "engines": {
        "node": "10.10.0",
        "npm": "6.4.1"
    }

### Specify start script
Instruct Heroku what command to run to start
our server running
E.g. insert the following script to 'scripts' 
in package.json
    "start": "node index.js"

### Create .gitignore file
We don't want to include dependencies, Heroku 
will do that for us

## First Time Deploy

# Create Heroku account
# Commit our codebase to git
# Install Heroku CLI and Create App
# Deploy App with Git
# Heroku deploys project