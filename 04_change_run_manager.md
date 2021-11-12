# Changing the Veda run manager settings

Alice is working on a run with a new constraint. She changes the run manager settings in her Veda interface. She adds a scenario group and case. For Bob to have access to these run manager settings, she needs to commit the changes to her local repo and push to the remote.

The following procudure is used to do this on a new branch called dev_new_constraint. Alice commmits the changes for the scenario group and case creation using two commits to distinguish the changes in the version history. She then pushes the branch to the remote.

1. Create a git branch
```
git checkout -b dev_new_constraint
```
2. Add the scenario group in Veda

```
git add AppData/Groups.json
git add AppData/Cases.json
git commit -m “add new scenario group to solve new costraint”
```

3. Add the new case to the repo
```
git add AppData/Cases.json
git commit -m "add new case to run new scenario"
```

4. Alice runs the case. This changes the "Edited On" entry of AppData/Cases.json (which Alice sees, by running ```git diff```). Alice does not want to keep these changes in the repo. So she runs 
```
git stash
git stash clear
```

5. When the changes are ready to be pushed to the remote, follow the steps to push the branch dev_new_constraint, create a pull request as in [03_change_model_data](https://github.com/DataScienceScotland/git_veda2_guidance/blob/main/03_change_model_data.md).
