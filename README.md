# README for Module P4 - cintel-04-local

## 1. Project Title

Publish Interactive Reactive App

## 2. Project Description

This project will closely follow the typical workflow of a real interactive development project. In Module 4, we create a repo in GitHub, clone it down, create a local project virtual environment in the .venv folder, activate our .venv virtual environment, and install all the packages we need.

Once the project virtual environment has everything required, we can open the project folder in VS Code, open a terminal, activate the project virtual environment (so we have access to the packages we installed into .venv), and run our app. We edit and rerun as often as needed - remember to activate your project virtual environment each time you work on the project.

## 3. Dependencies

### Prior to starting this project, ensure that the following assignments have been completed:

- [CC4.1: Orient and Engage (Professional Tools, Install Python)](https://nwmissouri.instructure.com/courses/58020/assignments/935693)
- [CC4.2: Install & Configure VS Code for Editing & Engage](https://nwmissouri.instructure.com/courses/58020/assignments/942456)
- [CC4.3: Install & Configure Git for version control](https://nwmissouri.instructure.com/courses/58020/assignments/942454)
- [CC4.4: Starting a Local Python Project & Engage (It's crazy!)](https://nwmissouri.instructure.com/courses/58020/assignments/944537)
- [CC4.5: Running Python in VS Code (Envs and Terminals) & Engage](https://nwmissouri.instructure.com/courses/58020/assignments/944538)

### Completing the aforementioned assignments will result in a project repo named `cintel-04-local`, with the following files

 - `README.md`
 - `.gitignore`
 - `requirements.txt`
 - `penguins/app.py`

## 3. How to Install and Run the Project

Upon completion of the dependencies, you have created the repo in GitHub and cloned it to your local machine. You created a local project virtual environment in the .venv folder, activated it, and installed necessary packages. 

Then, you should be able to open your project folder (cintel-04-local) in VS Code. Open a terminal and activate the project (anytime you open a new terminal) and run the shiny app in your terminal.

````python
shiny run --reload --launch-browser penguins/app.py
````
While the app is running, that terminal is fully occupied.
Open a new terminal to run other commands.

## 4. Build the App

### Action 1: Verify App Runs

Once the new browser launches, verify the Shiny app is successfully running. Debug and errors and fine tune before continuing

### Action 2: Build Client-Side App
 - We will build the app to the docs folder of our repository and test it locally.  

 - With your project virtual environment active in the terminal and the necessary packages installed into our .venv project virtual environment, remove any existing assets:

 ```python
 shiny static-assets remove
 ```
 - use shinylive export to build the app in the **penguins** folder to the **docs** folder:

 ```python
 shinylive export penguins docs
 ```
 - After the app is built, serve the app locally from the docs folder to test before publishing to GitHub Pages. In the terminal, run the following command from the root of the project folder with the project virtual environment active:

 ```python
 py -m http.server --directory docs --bind localhost 8008
 ```

 - Open a browser (tested with Chrome) and navigate to http://localhost:8008Links to an external site. - or whatever URL it tells you - to view the web app in the docs folder running locally

 ### Action 3: Git Add / Commit / Push to GitHub

  - After editing project files, and testing your web app in the docs folder, use Git add/commit/push changes to the main branch of the repository. Note that if a terminal is serving an app, it is not available for other commands. Run the following commands from a new or available terminal to git add/commit/push changes to GitHub. Replace "Your commit message" with a meaningful message about the changes you made to the project files. Run commands one at a time and wait for each to complete before running the next. The add space dot in the first command is very important - it means add all the files in this folder to source control.  The dot means "this folder and everything in it". You must include the dot and you must leave a space before it. 

```python
git add .

git commit -m "Your commit message"

git push -u origin main
```

### Action 4: Publish GitHub Pages for the Repo

This is a one-time step. We need to set up your GitHub repo (in the cloud) so that it will host with GitHub Pages. The first time you set up an app to use Pages, navigate to the repository on GitHub and configure the settings to publish the app with GitHub Pages. After configuring the repository once, each time you push changes to the main branch, the app will automatically update.

1. Go to the repository on GitHub and navigate to the **Settings** tab.
2. Scroll down and click the **Pages** section down the left.
3. Select branch main as the source for the site.
4. Change from the root folder to the docs folder to publish from.
5. Click Save and wait for the site to build.
6. Eventually, be patient, your app will be published and if you scroll to the top of the Pages tab, you'll see your github.io URL for the hosted web app. Copy this to your clipboard. 
7. Back on the main repo page, find the About section of the repo (kind of upper right).
8. Edit the "About" section of the repository to include a link to your hosted web app by using the Pages URL. 

When Finished

When you finish, you should have a working, unique version of a penguin dashboard that you can work with locally on your machine and have published for free on the web. It should have several inputs including a drop down to select a column for display that works and a checkbox group for species that is used to reactively filter the species shown on the charts. It should use a reactive calc to filter the dataframe and use the filtered dataframe for your tables, grids, and charts. 

### Action 5. Change the Browser Tab Title

Back on your machine, in VS Code, open the new docs folder. Edit **docs/index.html** - find the line that has the **<title>** and **</title>** opening and closing tags. The inner text between these two tags will appear in your tab. It's currently the same for everyone. Make this unique. 

Replace the title with your own short custom title - it will display in the browser tab when your app runs.
