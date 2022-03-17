# brettlungal.github.io

## Purpose
* The puropose of this README is to describe the practical steps of how to host and format a resume using Markdown, VS Code, Jekyll, and Github Pages

## Prerequisites
* A markdown formatted resume
* Visual Studio Code
* Github Account
* Windows 10/11 or MacOS
* knowledge of CLI operation

## Instructions

* ### Step 1 - Create a Git Repo
    1. Navigate to the [Github Website](https://github.com/)
    2. On the left hand side of the screen click the green button that says "New"
    3. Name the repository username.github.io where username is your github username. Example: my username is brettlungal so my repository name is brettlungal.github.io
    3. Select "create README.md" and create the repository

* ### Step 2 - Install Ruby
    * #### For Windows
        1. Navigate to the [RubyInstaller](https://rubyinstaller.org/downloads/) and download the latest version of ruby x64 with devkit
        2. Open the ruby installer, select "Accept This License" and press next
        3.  Verify the path where Ruby will be installed, and make sure "Add Ruby executables to your PATH" and "Associate .rb and .rbw with this Ruby installation" are checked
        4. Select the Ruby base files and Ruby RI and HTML Documentation boxes and press install
        5. Once Ruby is finished installing ensure "Run ridk install to setup MSYS2 and development toolchain" and click finish
        6. Once ridk installer opens in a terminal, type 1 and press enter
        7. Next type 3 and press enter and the installer will fetch and install further requirements
        8. Once both are done, exit the terminal window and open a new command prompt
            * do this by opening the start menu and searching "command prompt" and running the command prompt application
        9. Enter the following commands one at a time and press enter after each to verify ruby and gem was successfully installed
            ```bash
            ruby -v
            ```
            ```bash
            gem -v
            ```
    * #### For MacOS
        1. MacOS comes with Ruby and Ruby Gems pre-installed. To verify this run the following command
            ```bash
            ruby -v
            ```
            ```bash
            gem -v
            ```

* ### Step 3 - Install Jekyll
    * #### For Windows
        1. Run the following command to install jekyll with the gem package manager
        ```bash
        gem install jekyll bunder 
        ```
        2. Verify jekyll was installed correctly with the following command
        ```bash 
        jekyll -v 
        ```
    * #### For MacOS
        1. Install gem using the Gem package manager with the following command
            ```bash
            gem install jekyll bundler
            ```
        2. Validate the installation was complete with the following command
            ```bash
            jekyll -v
            ```
* ### Step 4 - Create New Jekyll Project
    1. cd into the directory containing your markdown files you want to host using jekyll
    2. run the command jekyll new projectName - where projectName is what you want to name your project
    3. you'll notice the previous created a directory in the pwd named your project name - it contains all relevant files for your static website
    4. cd into that new directory by typing cd projectName where project name is what you named your project

* ### Step 5 - Run Your Project From LocalHost
    1. run the command "bundle add webrick"
    2. run the command bundle exec jekyll serve
    3. open a web browser and in the navigation bar enter "localhost:4000"

* ### Step 6 - Add Your Markdown Resume To Jekyll Main Page
    1. Navigate to the file named "index.md" in the jekyll project directory
    2. Remove all of the content in index.md and copy/paste in your markdown formatted resume into index.md
    3. Add the following content to the top lines of your index.md after pasting in your markdown formatted resume
        ```yaml
        ---
        layout: home
        list_title: ' '
        title: Your Title
        ---
        ```
    4. Replace "Your Title" with any title you would like for your webpage, the most common would be your first name and last name

* ### Step 7 - Push The Project To Git
    1. in a CLI cd'd into the directory that contains your jekyll project run the command "git init"
    2. run the command "git add ."
    3. run the command git commit -m "commit project to repo"
    4. git branch -M main
    5. git remote add origin https://github.com/brettlungal/brettlungal.github.io.git
    6. git push -u origin main

* ### Step 8 - View Your Static Website On Github Pages!
    1. navigate to https://username.github.io where username is your github username to view your public static webpage!

## More Resources
* [Markdown Tutorial](https://www.markdowntutorial.com/)
* [Modern Technical Writing: An Introduction to Software Documentation by Andrew Etter](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)
* [Jekyll Documentation](https://jekyllrb.com/docs/)

## Authors and Acknowledgement
* Author
    * Brett Lungal
* Acknowledgements
    * Rhushabh Patel
    * Xianfeng Lang
    * Sangil Han
    * Yelizaveta Yashin


## FAQ's
1. My jekyll theme appears running locally but not when hosted on github pages?
    * This is a common issue when pushing a jekyll project to github pages and the issue comes from the _config.yml file. To fix this issue you must change the "url" field to be the url of your github page. Example: url: "username.github.io". You must also set the baseurl value to an empty string. Example baseurl: ""
2. Why do I need to install Ruby to do this if im not programming?
    * Jekyll is built using ruby, and ruby's package manager Gem is how we acquire the jekyll library from the internet