# Preparing your Debian Buster Distro for Jekyll Development

NOTE: This was tested on #!++ running Debian Buster using the Bourne Again Shell (BASH)

The first step will be to remove ruby and install dependencies.

```terminal
sudo apt remove ruby```

Before installing dependencies, update apt.

```terminal
sudo apt update``` 

Next, install dependencies.

```terminal
sudo apt install git curl libssl-dev libreadline-dev zlib1g-dev autoconf bison build-essential libyaml-dev libreadline-dev libncurses5-dev libffi-dev libgdbm-dev```

Now we will curl the sources and install ruby. Warning, this could take some time to compile and there is a period at the beginning of the process where there is no on screen output. I suggest grabbing your favorite tea and have a cuppa!

```terminal
curl -sL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-installer | bash -```

Next we add $HOME/.rbenv/bin to your PATH. 

```terminal
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc```

And put a line in your ~/.bashrc file to start ruby.

```terminal
echo 'eval "$(rbenv init -)"' >> ~/.bashrc```

Restart BASH with the new environmental variables.

```terminal
source ~/.bashrc
```

Now we install the latest stable release.  At the time of the writing of this article it was 2.7.1.  Be sure to go to https://www.ruby-lang.org/en/ to check on the latest stable.

```terminal
rbenv install 2.7.1
```

Now we set it as the global default version for our ruby environment.

```terminal
rbenv global 2.7.1
```

Verify the ruby version.

```terminal
ruby -v
```

Output should look similar to this:

```terminal
ruby 2.7.1p83 (2020-03-31 revision a0c7c23c9c) [x86_64-linux]
```

Lastly, we install rubygems.

```terminal
sudo apt install rubygems
```
