Only do this after completing [workstation.md].

# Intro

Exercism.io uses Github for authentication and authorization, rather than maintaining a database of usernames and passwords.  This means someone can use their Github credentials to log into Exercism.io.

We're going to setup your local development environment so that you can login to it.

## Allowing your Github account to talk to your local dev environment

Log in to your Github Account.

Then head on over to https://github.com/settings/applications/new

* For Application Name, enter something along the lines of "Exercism-dev"
* For Homepage URL, enter http://localhost:4567
* Application Description is optional, but feel free to enter something along the lines of "My Exercism Dev Environment"
* Then, for Authorization Callback URL, enter http://localhost:4567/github/callback

Then click the big "Register Application button"

You will be brought to a screen which displays "Exercism-Dev" at the top.

Copy down the values for "Client ID" and "Client Secret".  These are what will allow your local dev environment to talk to your Github account.

## Setting up your local dev environment to use your Github account

Head on over to your terminal and make sure you are in the directory for your fork of the exercism.io code.

Now, open up this file with your favorite text editor.

If you are using atom, open it with

```bash
  $ atom .env
```

If you are using vim, open it with

```bash
  $ vim .env
```

Once you open it, you should see text that looks like this:

.env
```bash
export PORT=4567
export EXERCISM_GITHUB_CLIENT_ID=abc123
export EXERCISM_GITHUB_CLIENT_SECRET=abcdef123456
# export EXERCISES_API_URL=http://localhost:9292
```

Now, change the EXERCISM_GITHUB_CLIENT_ID from "abc123" to the "Client ID" value from the Github application you just created.

Then, change the EXERCISM_GITHUB_CLIENT_SECRET from "abcdef123456" to the "Client Secret" value from the Github application you just created.

So, if my "Client ID" value was "112233" and my "Client Secret" was "aabbccdd", that file should now look like this:

.env
```bash
export PORT=4567
export EXERCISM_GITHUB_CLIENT_ID=112233
export EXERCISM_GITHUB_CLIENT_SECRET=aabbccdd
# export EXERCISES_API_URL=http://localhost:9292
```

## Applying the changes to your local dev environment

Now, start your local dev server with this command:

```bash
  $ bundle exec foreman s -p 4567
```

(If it's already running, stop it with CTRL+C, then run the command)

Now head to your browser and navigate to http://localhost:4567

Then click the "Login with Github" link in the upper right hand corner.

You will be prompted to enter your Github username and password (if you are not already logged into Github).

You will be prompted to allow your application to access your account.  Click "Authorize Application."

And you will be redirected back to your local dev environment, now logged into your local environment of Exercism!
