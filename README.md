# Associate Tutorials

The Tutorials in this repo were compiled for associate scientist on-boarding.

## Set-Up
You only have to perform these steps once to set up the project on your machine.

Create a python virtual environment specifically for this project. With conda, the command is:
```
conda create --name assoc-tutorials python=3.8
```
Activate the environment.
```
conda activate assoc-tutorials
```
Install necessary dependencies.
```
conda install jupyter 
```
Now you're ready to clone the repository.
```
git clone https://github.com/ValkyrieIntelligence/vlk-associate-tutorials
```
Navigate to the repository you just cloned and checkout your own branch.
```
cd vlk-associate-tutorials
git checkout kln-eda-branch
```

## Additional Rules and Guidelines
In order to get the best out of the template:

* <b>Never commit changes to the master branch.</b> Always work on your own branch prefixed with your initials (e.g. brj-napa-eda)
* Please don't remove any lines from the .gitignore file provided (you may add if necessary).
* Don't commit any data to the repository.
* Don't commit any credentials or local configuration to the repository.
* Name your notebooks with your initials (i.e kln-eda-example). Do not edit other users' notebooks.
