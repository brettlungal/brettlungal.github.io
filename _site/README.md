# COMP3040-Assignment-2

## Step 1 - Install Ruby
* Navigate to the [RubyInstaller](https://rubyinstaller.org/downloads/) and download the latest version of ruby x64 with devkit
* Open the ruby installer, select "Accept This License" and press next
* Verify the path where Ruby will be installed, and make sure "Add Ruby executables to your PATH" and "Associate .rb and .rbw with this Ruby installation" are checked
* Select the Ruby base files and Ruby RI and HTML Documentation boxes and press install
* Once Ruby is finished installing ensure "Run ridk install to setup MSYS2 and development toolchain" and click finish
* Once ridk installer opens in a terminal, enter 1 and press enter - it will now begin installing stuff
* now enter 3 and press enter and the installer will go and install more requirements
* Once both are done, exit the terminal window and open a new command prompt
* type "ruby -v" to verify ruby is setup corrctly, and "gem -v" to verify gem is setup correctly

## Step 2 - Install Jekyll
* type "gem install jekyll bundler" and press enter to install jekyll
* type "Jekyll -v" to verify jekyll was installed correctly

## Step 3 - Create New Jekyll Project
* cd into the directory containing your markdown files you want to host using jekyll
* run the command jekyll new projectName - where projectName is what you want to name your project
* you'll notice the previous created a directory in the pwd named your project name - it contains all relevant files for your static website
* cd into that new directory by typing cd projectName where project name is what you named your project

## Step 4 - Run Your Project From LocalHost
* run the command "bundle add webrick"
* run the command bundle exec jekyll serve
* open a web browser and in the navigation bar enter "localhost:4000" 