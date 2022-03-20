# brettlungal.github.io

## Purpose
* The puropose of this README is to describe the practical steps of how to host and format a resume using Markdown, VS Code, Jekyll, and GitHub Pages

## Prerequisites
* A [Markdown](https://www.markdowntutorial.com/) formatted resume
* Visual Studio Code
* GitHub Account/ Saved GitHub Credentials
* Windows 10/11 or MacOS
* knowledge of CLI operation

## Instructions

* ### Step 1 - Create a Git Repo
    1. Navigate to the [GitHub Website](https://github.com/)
    2. Click the green button on the left side of the screen that says "New"
    3. Name the repository username.github.io where username is your GitHub username. Example: my username is brettlungal so my repository name is brettlungal.github.io
    3. Select "create README.md" and create the repository
    > We use distributed version control for documentation because Etter says that it increases the likelihood of contribution and makes it easier to achieve.

* ### Step 2 - Install Ruby
    * #### For Windows
        1. Navigate to the [RubyInstaller](https://rubyinstaller.org/downloads/) and download the latest version of ruby x64 with devkit
        2. Open the ruby installer, select "Accept This License" and press next
        3. Verify the path where Ruby will be installed, and make sure "Add Ruby executables to your PATH" and "Associate .rb and .rbw with this Ruby installation" are checked before continuing
        4. Select the Ruby base files and Ruby RI and HTML Documentation boxes and press install
        5. Ensure "Run ridk install to setup MSYS2 and development toolchain" and click finish
        6. Type 1 to select the first installation and press enter
        7. Type 3 and press enter to select the second installation and press enter
        8. Exit the terminal window and open a new command prompt
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
    > Etter emphasizes the importance of using static site generators for easily creating more complex documentation websites, Jekyll runs on the Ruby programming language and therefore requires it to be installed on your computer.
* ### Step 3 - Install Jekyll And Create A New Jekyll Project
    1. Install Jekyll using one of the two below instructions based on your Operating System.
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
            1. Install Jekyll using the Gem package manager with the following command
                ```bash
                gem install jekyll bundler
                ```
            2. Validate the installation was complete with the following command
                ```bash
                jekyll -v
                ```
    2. Run the following command to create a new Jekyll Project - replace projectName with the name of your project
        ```bash
        jekyll new projectName
        ```
    3. Change directory into the folder that jekyll just created for you that contains all of the project files
        ```bash
        cd projectName
        ```
    > Etter recommends using a static website generator like Jekyll because they turn lightweight, simple markup files and turn them into beautiful, functional documentation websites
* ### Step 4 - Run Your Project From LocalHost
    1. Run the following command to add webrick to your jekyll bundle.
        ```bash
        bundle add webrick
        ```
    2. Run the following command command to start the local web server to view your changes locally as you make them.
        ```bash
        exec jekyll serve
        ```
    3. Open a web browser and in the navigation bar enter "localhost:4000"
    > As previously noted, Etter emphasizes the significance of being able to use a static site generator for hosting beautiful documentation. This step allows you to view your changes to your jekyll website locally before commiting them to git to be hosted publicly. Allows for quicker development time when writing your markdown formatted files.

* ### Step 5 - Add Your Markdown Resume To Jekyll Main Page
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
    4. Replace "Your Title" with any title you would like for your webpage, the most common would be your first and last name.
    > We use markdown because Etter suggests using a lightweight markdown language that is easy to read and write, and markdown the the most widely used markup language

* ### Step 6 - Upload Jekyll Files To GitHub
    * #### Option 1 - Manually upload files to GitHub
        1. Navigate your browser to the GitHub repo you created in step 1
        2. Click "upload an existing file" in the blue banner displayed on screen
        3. Open your computers file explorer and find your Jekyll project files
        4. Select all of the files in the folder, then click and drag them to the drop zone in GitHub
            [![Drag Files Gif](https://i.gyazo.com/0ff2d19f3a21d5ed769e9b8906c6549b.gif)](https://gyazo.com/0ff2d19f3a21d5ed769e9b8906c6549b)
        5. Click "Commit changes" to complete the upload to GitHub
    * #### Option 2 - Push Files Using GitHub CLI
        > :warning: **Warning**: This is a much more advanced way of adding files to GitHub and requires GitHub CLI to be installed and configured beforehand.
        1. Run the following command to initialize git in your Jekyll project folder
            ```bash
            git init
            ```
        2. Run the following command to mark all of your Jekyll files to be added to git
            ```bash
            git add .
            ```
        3. Run the following command to commit the marked files to git, and give it a message associated with the commit
            ```bash
            git commit -m "commit project to repo"
            ```
        4. Run the following command to ensure you are on the main branch of your git repo
            ```bash
            git branch -M main
            ```
        5. Replace "githubUsername" with your GitHub username and run the following command to link your folder to your git repo you created in step 1
            ```bash 
            git remote add origin https://github.com/githubUsername/githubUsername.github.io.git
            ```
        6. Run the following command to push your Jekyll static website to GitHub to be hosted publicly
            ```bash
            git push -u origin main
            ```
    >Etter says that this method of storing documentation allows all of the documents to stay up to date and in sync, as well as allows for offline work!
* ### Step 7 - View Your Static Website On GitHub Pages!
    1. Navigate to https://username.github.io where username is your GitHub username to view your public static webpage just as shown below!
        ![Image from Gyazo](https://i.gyazo.com/d3e2477b2e281b4c4fb6d1ad37102fa9.gif)
    > Etter says that static webpages are the best way to host documentation for people to view as it is simple to migrate, has no external dependencies, and can be updated and evolve as the product evolves. Etter noted that a pdf that someone downloads can go stale and out of date easily, thats where static webpages come to save the day!

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
1. My jekyll theme appears running locally but not when hosted on GitHub pages?
    * This is a common issue when pushing a jekyll project to GitHub pages and the issue comes from the _config.yml file. To fix this issue you must change the "url" field to be the url of your GitHub page. Example: url: "username.github.io". You must also set the baseurl value to an empty string. Example baseurl: ""
2. Why do I need to install Ruby to do this if im not programming?
    * Jekyll is built using ruby, and ruby's package manager Gem is how we acquire the jekyll library from the internet