# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

# Ruby version
## Install homebrew 

	/bin/bash -c "$(curl -fsSL /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

## Install ruby using homebrew 

	brew install ruby

## Install rbenv with homebrew

1.Install rbenv:  

	/bin/bash -c "$(curl -fsSL /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

2.Set up rbenv in you shell : 	

	rbenv init

3.Close your Terminal window and open a new one so your changes take effect.

4.Verify that rbenv is properly set up using this rbenv-doctor script:

	$ curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash

where you will see:

	Checking for 'rbenv' in PATH: /usr/local/bin/rbenv
	Checking for rbenv shims in PATH: OK
	Checking 'rbenv install' support: /usr/local/bin/rbenv-install (ruby-build 20170523)
	Counting installed Ruby versions: none
		There aren't any Ruby versions installed under `~/.rbenv/versions'.
		You can install Ruby versions like so: rbenv install 2.2.4
	Checking RubyGems settings: OK
	Auditing installed plugins: OK	

## Set up and run the whole thing

	vim ~/.bash_profile
	ls -a	
	export PATH="$HOME/.rbenv/bin:$PATH" eval "$(rbenv init -)"
(https://stackoverflow.com/questions/10940736/rbenv-not-changing-ruby-version)

## To upgrade to the latest rbenv and update ruby-build with newly released Ruby versions, upgrade the Homebrew packages:

	#list all available versions:
	$ rbenv install -l
	#install a Ruby version:	
	$ rbenv install 2.6.3
 
## Once you've installed some Ruby versions, you'll want to install gems:
Bundle install OSX: 

	gem install bundler	
	Bundle install

## Add to the PATH on Mac OS X 10.8 Mountain Lion and up
1.Open up Terminal.

2.Run the following command:

	$ curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash

3.Enter your password, when prompted.

4.Go to the bottom of the file, and enter the path you wish to add. (prepending /.rbenv/shims to your $PATH)

5.Hit control-x to quit.

6.Enter “Y” to save the modified buffer.

7.That’s it!  To test it, in new terminal window, type:
echo $PATH
Then, You should see something similar to this (including the path you’ve added!):

	$ echo $PATH
	~/.rbenv/shims:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/share/dotnet:~/.dotnet/tools:/Library/Frameworks/Mono.framework/Versions/Current/Commands


## 'An error occurred while installing pg (0.17.1), and Bundler cannot continue’
Solution:

1.Install Postgres:

-Download   ➜   Move to Applications folder   ➜   Double Click
(If you don't move Postgres.app to the Applications folder, you will see a warning about an unidentified developer and won't be able to open it.)

-Click "Initialize" to create a new server

-Configure your $PATH to use the included command line tools (optional):

	sudo mkdir -p /etc/paths.d &&
	echo /Applications/Postgres.app/Contents/Versions/latest/bin | sudo tee /etc/paths.d/postgresapp

2.And then in terminal install using homebrew with the configuration:

	gem install pg -- --with-pg-config=/Applications/Postgres.app/Contents/Versions/latest/bin/pg_config

# Database creation
	rake db:setup
	rake db:migrate

