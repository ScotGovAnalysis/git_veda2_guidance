# Changing the model data

Bob wants to update the model data. In this case, he updates syssettings.xlsx with a change to the ~TimePeriods pdef (but it could be any data file(s)). He will do this in his local repo on a separate branch. When he is happy with the changes, he will push the changes to the remote. Alice, can then quality assure the changes. When both of them are happy, they can merge the changes into the main model.

Bob and Alice's workflow is such that the changes to datafiles and Veda interface files are carried out on separate branches. 

1. Before starting to work, Bob makes sure that the local version of the main branch is in sync with the remote/origin

```
git pull --rebase origin main
```

2. Create a development branch for making the changes. Alice and Bob have agreed a naming convention for branch names: dev_<descriptor_of_change>. Bob is updating the syssettings pdef table and creates a branch "dev_syssettings_pdef". 
```
git branch dev_syssettings_pdef
git checkout dev_syssettings_pdef
```
If Bob wants to work on the branch immediately after creating it, these two commands can be combined in a single command
```
git checkout -b dev_syssettings_pdef
```

3. Update datafile.xlsx, then add and commit the changes in the repo
```
git add syssettings.xlsx
git commit -m "update syssettings.xlsx with change of pdef5 "
```
4. To test the changes in TIMES/Veda, it is recommended to create a new branch that comes off of dev_syssettings. This allows Bob to run Veda as needed without affecting the repository. Their agreed naming convention is that all temporary branches start with the string "temp"
```
git checkout -b temp_syssettings_pdef
```
Bob can checkout the parent branch at any time to make additional changes to the data. When he is finished working on the temporary branch and is happy with the data, he checksout dev_syssettings_pdef and deletes temp_syssettings_pdef.
```
git checkout dev_syssettings_pdef
git branch -D temp_syssettings_pdef
```
(The -D is needed for a branch that has not been merged. An option -d can be used for branches that have been merged)

5. Push the changes to the remote. Before pushing, make sure that the branch is up to data with origin.

```
git checkout dev_syssettings_pdef
git pull --rebase origin main
git push -u origin dev_syssettings_pdef
```

6. Go to the project location on GitHub, and complete the details of the pull request. This will notify the collaborators that there are changes to be reviewed. 

7. Alice QAs the changes by fetching the branch to her local machine.
```
git fetch origin
git checkout -b dev_syssettings_pdef origin/dev_syssettings_pdef
git merge main
```
She leaves comments on the pull request page, and either Alice or Bob can push additional commits to the branch

8. When all issues are settled, the branch can be merged. This can be done via the GitHub pull request page, or locally and the main branch pushed
```
git checkout main
git merge --no-ff dev_syssettings_pdef
git push -u origin main
```
