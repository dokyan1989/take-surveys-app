# Heroku Deployment Checklist

## Deployment Checklist

01. Dynamic Port Binding
Heroku tells us which port our app will use, 
so we need to make sure we listen to the port 
they tell us to
E.g. create PORT in index.js
    const PORT = process.env.PORT || 5000;
            ||
            ||
            \/
02. Specify Node Environment
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
03. Specify start script
Instruct Heroku what command to run to start
our server running
E.g. insert the following script to 'scripts' 
in package.json
    "start": "node index.js"
            ||
            ||
            \/
04. Create .gitignore file
We don't want to include dependencies, Heroku 
will do that for us

## First Time Deploy

01. Create Heroku account
            ||
            ||
            \/
02. Commit our codebase to git
E.g. using the following commands
    git add . 
    git commit -m "initial commit"
            ||
            ||
            \/
03. Install Heroku CLI and Create App
            ||
            ||
            \/
04. Deploy App with Git
E.g. using the following commands
    - login to heroku: heroku login
    - create heroku app: heroku create
    - push codebase to heroku: 
        + git remote add heroku https://git.heroku.com/powerful-sierra-33750.git
        + git push heroku master
            ||
            ||
            \/
05. Heroku deploys project

## Subsequent Deploys

01. Commit codebase to git
            ||
            ||
            \/
02. Deploy App with Git
E.g. using the following commands
    git add .
    git commit -m "changed greeting"
    git push heroku master

https://powerful-sierra-33750.herokuapp.com/
https://git.heroku.com/powerful-sierra-33750.git

# OAuth Flow

01. Client | User clicks 'Login' 
    || (Direct to localhost:5000/auth/google)
    \/
02. Server | Forward user's request to Google
    || (google.com/auth?appId=123)
    \/
03. Google | Ask user if they grant permission
    || 
    \/
04. Google | User grants permission
    || (Direct to localhost:5000/auth/google/callback?code=456)
    \/
05. Server | Put user on hold, take the 'code' from the URL
    ||
    \/
06. Server | Send request to google with 'code' included
    ||
    \/
07. Google | Google sees 'code' in URL, replies with details about this user
    ||
    \/
08. Server | Get user details, create new record in database
    ||
    \/
09. Server | Set user ID in cookie for this user
    || (Kick user back to localhost:3000)
    \/
10. Client | Logged in!
    
11. Client | I need some resources from the API
    || (Cookie automatically included)
    \/
12. Server | Ah, this request has a cookie with user id equal to 123

# The Theory of Authentication
See lecture 29

# Signing in Users with OAuth
See lecture 30

- Redux-form
- Stripe
- Passport.js
- Mongoose
- mLab
- heroku

https://dsajfqheiwqhixcnvdsfhajk.localtunnel.me/api/surveys/webhooks
https://powerful-sierra-33750.herokuapp.com/api/surveys/webhooks