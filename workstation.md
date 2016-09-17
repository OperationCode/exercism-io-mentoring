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

For now, ignore the message "sh: lineman: command not found" that appears at the end of the run.

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

## Installing Ubuntu
### Download Ubuntu 16.04
Download the iso image of Ubuntu from http://releases.ubuntu.com/16.04/
I used the Desktop image for 16.04 located at http://releases.ubuntu.com/16.04/ubuntu-16.04-desktop-amd64.iso
Check the md5 checksum to verify your download. The checksum for this release is 40a36ab0192cae9be125298abba4d684
More information on verifying checksums can be found at https://help.ubuntu.com/community/HowToMD5SUM

### Installation Procedures
Once you've verified the checksum of the iso, burn it to a disc and put it into the computer you want to install ubuntu on. You need to configure your computer to boot from the disc.

Warning: When you install Ubuntu using these procedures, it will completely erase your current OS and all files. If you simply want to try Ubuntu, it is recommended you install to a virtual machine instead. Some helpful instructions can be found here http://www.psychocats.net/ubuntu/virtualbox
Note that you may need to "Enable Virtualization" in your bios. More on that here: https://forums.virtualbox.org/viewtopic.php?f=1&t=62339

Once it loads, click "Install Ubuntu"
I left the boxes for "Download updates while installing" and "Install third party software..." unchecked.
Choose "Erase disc and install Ubuntu" and click "Install Now"
Choose your timezone, keyboard layout/language, name, computer-name, and password.
Restart the computer when instructed.

## Setting Up Exercism Repository
### Install git
Open a terminal and run 
```bash
sudo apt-get install git
```


### Create an ssh key and add it to your GitHub account
Follow [these instructions](https://help.github.com/articles/generating-an-ssh-key/)

### Clone your fork
See above instructions for mac. 
Type git clone and then the name of the repository like so:
```bash
git clone git@github.com:nellshamrell/exercism.io.git
```
Then change directory into the code base:
```bash
cd exercism.io
```

## Installing Ruby
We will be using rvm. Download rvm with these commands:
```bash
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
```
```bash
\curl -sSL https://get.rvm.io | bash -s stable
```
```bash
echo "source $HOME/.rvm/scripts/rvm" >> ~/.bash_profile
```
In order to use rvm on ubuntu, you need to have a login shell. In the terminal's menu at the top of the screen, select Edit->Profile Preferences. Select the Command tab, and check the box that says "Run Command as Login Shell".

Now, you must restart your terminal for rvm to work. Type `exit` then hit `CTRL-ALT-T` to reopen the terminal.
Now, typing `rvm list` should display the following
>rvm rubies
>
>#No rubies installed yet. Try 'rvm help install'.

For this project, we will use Ruby version 2.2.2. Install it using 
```bash
rvm install ruby-2.2.2
```

Type `rvm list` again and it should display

>   rvm rubies
>
>       ruby-2.2.2

Now we have rvm and the correct version of Ruby installed.

We have to set it as the default version to use now. Execute the following command:
```bash
rvm --default use 2.2.2
```

## Installing Node
```bash
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs
```

## Installing and setting up PostgreSQL
```bash
sudo apt-get install postgresql postgresql-contrib
```
The setup script also requires another related package, so let's install that now
```bash
sudo apt-get install libpq-dev
```
You need to set yourself up as a postgres user. Do so with this command:
```bash
sudo -u postgres createuser --superuser $USER
```
Run postgres with the following command
```bash
sudo -u postgres psql postgres
```
You should see the postgres prompt come up. It looks like
>postgres=# 

In the postgres prompt, ensure your user was created. Do this by typing in `\du`:
>postgres=# `\du`

This will display the table of users. It should include a user called postgres and another called the same user as your username:

> Role name |                         Attributes                         | Member of 
>-----------+------------------------------------------------------------+-----------
>
> username  | Superuser, Create role, Create DB                          | {}
>
> postgres  | Superuser, Create role, Create DB, Replication, Bypass RLS | {}

Press `q` to exit the table.

Next, we need to set a password for the new postgres account. It is easiest to use the same password that is specified in the exercism.io/config/database.yml because the setup script will ask you for several passwords in a row without mentioning which password is for which database user. Open the datbase.yml file with your favorite text editor (I'm partial to gedit): 
```bash
gedit ~/exercism.io/config/database.yml
```
and either change the password to whatever secure password you prefer, or note what the password in the file is. If you choose to edit the database.yml file, remember to create a `.git/info/exclude` file so your changes don't get committed to the database. Go back into postgres using `sudo -u postgres psql postgres` and at the postgres command prompt enter `\password username` where you change username to your username. Example:

>postgres=# `\password aaron`

This will prompt you to type in a password. Set the password to match the database.yml file's password.

We need to leave postgres running in the background, so open a new terminal window to continue set up.

When you are finished running the application, you can close out of postgresql with `\q`.


## Run the setup script
Ensure you are in ~/exercism.io
```bash
cd ~/exercism.io
```
Now run the setup script:
```bash
bin/setup
```
Setup will complain that lineman is not found. This is ok for now.

## Running the Application
Now, let's run the application
In your terminal, run this command:
```bash
  bundle exec foreman s -p 4567
```
This will run a local server and allow you to view the site in your browser.
Now, open up a browser and go to this url:
http://localhost:4567/
And you should see the exercism.io site running!  This is your local copy of the site where you can see changes.
(Note: I am intentionally not setting up login just yet in these instructions - we will work on a few other things first that don't need a login and then we will come back to that)

# Windows

Coming Soon
