Welcome to Exercism Team Six!

Let's set up your workstation so you can get contributing :)


# Mac OS X

## Workstation Pre-req

### XCode

First, open up a terminal.  You can do this by finding the terminal application on your Mac.
One way to open it is to open Spotlight (click the magnifying glass in the upper right hand corner),
then type in "Terminal" and hit "Enter".

Run this command from within your terminal:
```
  $ xcode-select --install
```

You will see a window pop up, click the "Install" button, then Agree to the license
agreement, then once the software installs hit "Done."

### Ruby

We are going to install Ruby using [rvm](https://rvm.io/).  You could also use
[rbenv](https://github.com/rbenv/rbenv) or [chruby](https://github.com/postmodern/chruby),
but these instructions will focus on rvm.

First, you will need to run a command to allow rvm to install on your workstation.

```
  $ gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
```

Then run this command to install rvm itself.

```
  $ \curl -sSL https://get.rvm.io | bash -s stable
```

Now, let's see what versions of ruby are availabe with rvm.  Run this command
to see the list.

```
  $ rvm list known
```

We are going to use ruby 2.3.0.  To install it from rvm, run this command

```
  $ rvm install 2.3.0
```

Now our system has the correct version of Ruby installed!

### Postgresql

Next, let's install [Postgresql](https://www.postgresql.org/).  There are
two ways to do this

This is likely the easiest way - downloading and running the [Postgres app](http://postgresapp.com/)
I recommend this way for simplicity of both installing and running Postgres.

Or, you can also run this command to install it with homebrew - a helpful installer included with Mac OS.

```
  $ brew install postgresql
```

### Node

Now, let's install Node.js, which is used to render the front end
of the exercism.io application.

```
  $ brew install node
```

## Github

### Create a Github Account

Head on over to [Github](https://github.com/) and create an account.

### Create an SSH key, then add it to your Github account.

Follow [these instructions](https://help.github.com/articles/generating-an-ssh-key/)

### Fork the exercism.io repo

While signed into github, head on over the the [exercism.io repo](https://github.com/exercism/exercism.io)
and click the big green "Clone or download" button in the upper right hand corner.

After making your fork, Github should redirect you to a repo called your_github_username/exercism.io.
This is your fork of exercism.io, where you can make changes, then submit them to the exercism.io project.

### Clone your fork

Now, making sure you are one you fork of exercism.io, click the green "Clone or download" button toward
the upper righthand quadrant of the screen.

[Insert screencap here]

You should see a small menu drop down.  It should have the text "Clone with SSH".
If not, click the link in the upper right hand corner of the drop down that says "Use SSH."

Copy the ssh address (it should look similar to this: git@github.com:nellshamrell/exercism.io.git).

Now, head on back to your terminal and run this command (substitute your own ssh address for your clone)

```
  $ git clone git@github.com:nellshamrell/exercism.io.git
```

This will copy the code base to your workstation.  Now change directories into the code base with
this command.

```
  $ cd exercism.io
```

## Configuring the App Codebase

Now, we will run a script to automatically setup the application with default settings.  Run it with this command.

```
  $ bin/setup
```

This will do a lot of stuff - including installing the needed gems, creating the development data base, create the test database, and run the test suite.

You will see the message "sh: lineman: command not found" that appears at the end of the run.  Let's go ahead and install that.

```
  $ npm install -g lineman
```

## Running the Application

Now, let's run the application

In your terminal, run this command:

```
  $ bundle exec foreman s -p 4567
```

This will run a local server and allow you to view the site in your browser.

Now, open up a browser and go to this url:

http://localhost:4567/

And you should see the exercism.io site running!  This is your local copy of the site where you can see changes.

(Note: I am intentionally not setting up login just yet in these instructions - we will work on a few other things first that don't need a login and then we will come back to that)

# Linux

Coming Soon

# Windows

Coming Soon
