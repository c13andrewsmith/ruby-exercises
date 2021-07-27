# Ruby Exercises

This is a collection of exercises to practice various aspects of Ruby.

Practicing in this manner (small, bite-sized problems that you can do repeatedly) is a _fantastic_ way to solidify programming concepts.

Each folder in this repository is a set of related exercises. Open up the folder and read the README to learn more about them.

## Structure of this repository
- Each folder contains a `README.md` file that provides a summary of what skills you will develop with these exercises
- Each exercise file within the folder will begin with comments providing more detail on:
  1. How you need to manipulate or work with this file to complete the exercise.
  2. Some exercises will require you to manipulate the "current" file and run it. Other exercises will require you to create _new_ files and then reference those files for the "current" file to work.

## Recommended Approach
  + Data Types
    - Strings
    - Ints and Floats
    - Collections
      + Arrays
      + Hashes
      + Nested Collections
  + Problem Solving
  + Initialize
  + Objects and Methods
  + Iteration
  + Enumerables
  + Data Types/Collections/**Advanced Nested Collections**
  + Mythical Creatures

## Setup

### 1. Clone this repository

You don't need to fork this repository; clone it to your laptop

in your `/turing` directory on your laptop (or whatever directory you want this repository to live inside of), run:

```
// using ssh keys
git clone git@github.com:turingschool/ruby-exercises.git
// using https, if the above doesn't work:
git clone https://github.com/turingschool/ruby-exercises.git
```

Once this command runs, you'll now have a "local" copy of this entire repository, living right on your laptop.

### 2. From the command line, `cd` into the `ruby-exercises` directory.

First, let's get a Ruby version management tool on our machines.

## Set up Ruby Environment Manager: [rbenv](https://github.com/rbenv/rbenv#homebrew-on-mac-os-x)

Over the years, Ruby has evolved through various version releases over time that contain new features and upgrades. Version 0.95, the very first, was released in 1995, and at the beginning of year 2020, we're at version 2.7.

Generally, programs written in one version of Ruby will run just fine on another version, but sometimes incompatibilities can be encountered, meaning that particular program needs to be run with a specific version of Ruby.

Additionally, very useful tools called "gems" are out there that were created specifically to help developers code (specifically, the `pry` gem is very handy) and we cannot utilize these without first installing and configuring `rbenv`.

To solve potential compatability issues, we'd like to be able to install and manage multiple versions of Ruby on our system. We would also like to be able to use gems across different versions of Ruby. These are the kinds of things `rbenv` handles.

#### Installation

Here is a video walk-through that may be helpful for the following steps. Check it out!

Keep in mind that the steps in the video are correct, but we want you to install **ruby version 2.7.2**, per the written instructions below.

[![Walkthrough RBENV and Ruby](images/rbenv-ruby-thumbnail.jpg)](https://youtu.be/3DtqMlK8In0 "Video Walkthrough for RBENV and Ruby Installation")

Similar to Homebrew, rbenv provides a script to get everything installed. Open a terminal with Spotlight search (`Command + Space`) and enter these commands:

```
$ brew update
```
Wait a few moments for `brew` to check its current version and make sure it is ready to be used.

```
$ brew install rbenv
```
Wait again, as brew installs rbenv.

```
$ rbenv init
```

The output from your terminal should be something similar to:

```
$ rbenv init
.
.
.
# Load rbenv automatically by appending
# the following to ~/.zshrc:

eval "$(rbenv init -)"
```

This output is telling you that you will need to add the above line (beginning with `eval`) to your "bash profile".

To do this, in your terminal, enter:

```
$ atom ~/.zshrc
```

This command will open up your `ZSH Runtime Configuration` file in Atom so you can edit it. Copy the line `eval "$(rbenv init -)"` and paste it at the END of the `.zshrc` file, and save it.

Check to see if you did this step correctly by switching back to your terminal and typing `cat ~/.zshrc`. You should see `eval "$(rbenv init -)"` at the bottom of the output.

After, *close your terminal and reopen it.* This is a very important step since the bash profile is loaded each time a new terminal window is opened.

Now, check to make sure rbenv was installed properly. In your terminal, type:

```
$ rbenv versions
```

It should give you a version number rather than an error message.

More information about rbenv can be found [here](https://github.com/rbenv/rbenv#homebrew-on-mac-os-x).

### Use rbenv to install a certain version of Ruby

Now that we have rbenv installed, we're going to use it to install a specific version of Ruby: Ruby 2.7.2. This is the version we will use in the Backend Program.

If you need another version it'll be the same procedure, just replace `2.7.2` in the instructions with whichever version you want.

Install it with:

```
$ rbenv install 2.7.2
```

It will take a while to finish installing, and print a _lot_ of text to your terminal.

When it's all finished, type:

```
$ rbenv versions
```

and you should now see `2.7.2` listed.

Be careful, there are two different rbenv commands, `version` and `versions`. The first shows you _your current ruby version_. The second shows _all installed versions_.

Switch to your newly installed version with

```
$ rbenv local 2.7.2
```

Now enter:

```
$ ruby -v
```

This shows us what version of Ruby we are running. You should see something like:

```
ruby 2.7.2p137 (2020-10-01 revision 5445e04352) [x86_64-darwin20]
```

You can ignore everything after the `p` in `2.7.2p1137`- the first bit shows us we are running Ruby 2.7.2, which is what we want to verify. If you got something different than `2.7.2`, such as `2.5.3`, go back through the Rbenv installation, make sure you have you successfully edited your `bash_profile`, restart your terminal, and try again.

#### Setting the Default Version

You can tell rbenv which Ruby version you want to use by default. Let's do that with terminal command:

```
$ rbenv global 2.7.2
```

Now, let's make your terminal aware of this update with command:

```
$ rbenv rehash
```

### 2. Install `bundler` gem

run `gem install bundler` in your terminal

### 3. From the command line, run `bundle install`

You _should_ see something like this:

```
$ bundle install
Fetching gem metadata from https://rubygems.org/........
Resolving dependencies...
Using bundler 2.1.4
Using byebug 11.1.3
Fetching coderay 1.1.2
Installing coderay 1.1.2
Using diff-lcs 1.4.4
Using method_source 1.0.0
Using pry 0.13.1
Fetching pry-byebug 3.9.0
Installing pry-byebug 3.9.0
Fetching rspec-support 3.10.1
Installing rspec-support 3.10.1
Fetching rspec-core 3.10.1
Installing rspec-core 3.10.1
Fetching rspec-expectations 3.10.1
Installing rspec-expectations 3.10.1
Fetching rspec-mocks 3.10.1
Installing rspec-mocks 3.10.1
Fetching rspec 3.10.0
Installing rspec 3.10.0
Bundle complete! 3 Gemfile dependencies, 12 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
```
If you see that, great!

If you get an error like:

```
zsh: command not found: bundle
```

you need to install the `bundler` gem. Run:

```
$ gem install bundler
```

If this command throws an error, you either:
  1. Don't have `rbenv` properly installed
  2. You've not yet installed a version of Ruby.

Please check that you've followed [mod0 setup instructions](http://mod0.turing.io/setup-instructions)
and this guide to [install rbenv and a version of ruby](https://github.com/turingschool-examples/backend_module_0_capstone#environment).

> Hey, hold up. What is this `bundle` thing, and what does it do? what does `gem install bundler` do?

Great question!

`bundler` is Ruby's [package manager](https://bundler.io/). If you want to install extra code that works with Ruby, you'll use `bundler` to do it. Once you _have_ the `bundler` installed, it is "used" by typing `bundle` into your terminal.

It is used in conjunction with the `Gemfile` and `Gemfile.lock` files you see in this repository, to manage Ruby gems.

Here's an exhaustive amount of information about gems, if you're so inclined: [guides.rubygems.org/what-is-a-gem](https://guides.rubygems.org/what-is-a-gem/)

-------------------

Once `bundle` has run successfully, open up the first test!

```
$ cd data-types/strings
$ atom .
```

And read through the `README.md` for further instructions!

If you want to view the instructions in your web browser, you can view them here: [data-types/strings/README.md](https://github.com/turingschool/ruby-exercises/tree/main/data-types/strings)


----------------------------------
