# Intro
Open an existing EOS Smart Contract repo created using the [VSCode New EOS Contract](https://github.com/EOSPowerNetwork/vscode-new-eos-contract) repository.

# Prerequisites
1. VSCode installed on your development PC
2. [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) VSCode extension has been installed
3. You've previously created an EOS Smart Contract using the [VSCode New EOS Contract](https://github.com/EOSPowerNetwork/vscode-new-eos-contract) repository, and pushed it to github.
# How to use
1. Clone this repo **into a new directory with the name of your project** (Directory naming restrictions: ```[a-zA-Z0-9][a-zA-Z0-9_.-]```)
2. Open in VSCode
3. Modify the .devcontainer file according to the instructions at the top of the file (Insert the target github account and repository name)
4. Run the ```Remote-Containers: Rebuild and Reopen in Container``` command in VSCode

VSCode will relaunch, connecting to a new docker container that has already cloned the targeted smart contract from github.

# Misc notes
When VSCode closes, the container stops. The data within the container is not accessible, as it's stored in an unnamed volume mounted on your PC, only accessible through the docker container launched by VSCode.
All changes made within the container will persist on that PC (as long as you don't delete the docker volume), and must be pushed to a git repository if you want to work on it on another PC.
