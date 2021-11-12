# Initialise a TIMES model as a git repo

Alice is working on a TIMES model and will use git version control. The model files are contained in a folder called ``times_model''.

Alice needs to initialise times_model as a git repository, add the model files to the repository, and setup a remote repository on GitHub.

She takes the following steps on a Windows PC:

1. In a file explorer window, navigate to ``times_model/''
2. Right click and ``Open Git Bash here''
2. In the terminal type
     ```
     git init
     ```
3. Create a .gitignore file. This is a text file that can be created in notepad. The file needs to be saved in the ``times_model/'' folder and not have any file type suffix. Under windows, the filetype can be removed by right clicking on the file in windows explorer, selecting rename, and removing the suffix.

The text below is the recommended text for a .gitignore to be used in the veda-workflow recommended here. It also ignores R project-associated files in case these are used in the workflow.

```
# File,           	Veda Window, 	When updated, 	             Git track\\
# ==========================================================
# FrontEndFormFormSettings,	Front,	Front end? When VEDA updated maybe?,	N
# NavigatorSettings,	Navigtor,	When model reloaded,	 		N
# BrowseFormSettings,	Browse,	     When Browse used,				N
# MasterFormFormSettings,	Item Details,	When RES opened/navigated,	N
# Cases,		Run manager,	Cases selected for a run,		Y
# Settings,		Run manager,	Run solver settings edited,		N
# Groups, 		Run manager,	Scenario groups edited,			Y
# ResultsFormSettings, 	Results,	Results window opened,			N
# ResultViews, 		Results,	When results table opened,		N
# ResultViewsDetails,	Results,	When results table opened, 		N
########################################################


#Ignore the setting for each veda view

AppData/*FormSettings.json
AppData/NavigatorSettings.json
AppData/Settings.json

#Ignore the results views from repo
AppData/ResultViewsDetails.json  

# Uncomment to ignore saved cases.
# AppData/Cases.json

#R-project 
.Rproj.user
.Rhistory
.RData
.Ruserdata
```

4. In git bash, add and commit the change
```
git add .gitignore
git commit -m "initial commit"
```

5. In git bash, add and commit all the other files to the repo
```
git add .
git commit  -m "Initial commit of all model files"
```

6. On GitHub. Create a new repository and set as public/private as approproate. **DO NOT** initialise the repository with any of the options
7. In git bash on the local machine, copy and paste the lines from GitHub under the heading **"...or push an existing repository from the command line"**
```
git remote add origin https://github.com/<git_username>/<github_repo_name>.git
git branch -M main
git push -u origin main
```

After a page refresh, the files should now appear in the GitHub repo.


