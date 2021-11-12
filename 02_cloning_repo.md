# Cloning the remote repo to local machine

Bob is working with Alice on the TIMES model. He needs to get a local copy of the model by cloning the remote repository. This local repo will be kept in sync with the remote repo. cal machine. Bob needs to take the following steps:

1.	Log onto GitHub and navigate to the repo. To get the repo URL, click on the green “Code” button, and copy to clipboard.
2.	On his local machine,  navigate to the folder where he wants the model to live (e.g. veda_models). There is no need to create a subfolder for the model as one will be created by the clone.
3.	Right click, and select “Git Bash here”
4.	At the command prompt type
	
	```git clone <repo_url>```

   The repo URL can be pasted with Shift-Ins, or rightclick-paste


If he is going to work on the repo immediately, Bob needs to change directory into the repo folder on Git Bash using

```cd <repo_name>```
