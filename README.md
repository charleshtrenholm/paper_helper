# Big Bad File Sorter

A project designed to help my friend sort his files and display them in an excel format. It's highly not recommended you use this for anything other than exactly the file format described.

## Getting Started
---
These instructions are designed specifically for you, anonymous user. There will hopefully idiot-proof instructions on how to use this tool in the terminal. You can copy paste any of the commands `that look like this` into the terminal and press enter and it should work.

### First things first, Install Python 3

By default, your computer will already have python2.7, but it wont work for this script. In order to install python3, you'll have to install this other thing called homebrew, which is a tool that installs things. You can paste the following into the terminal:

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`

Wait for it to finish installing. When the dollar sign is back on the line that you type in, that's when whatever you just did is finished. you can type `which brew` to ensure that it installed correctly. it should output something like `usr/local/bin/brew` if it worked and `brew not found` if it didnt.

now that you have this thing that can install things, it will be way less of a scary looking command to install python 3. just do:

`brew install python3`

Again, when you see the dollar sign, you can type `which python3` and as long as it doesnt say `python3 not found` you should be good.

### Setting up the script

First you want to copy the code down to your computer, and put it in a file on your desktop. Do these exact instructions (dont type in the lines with the hashtags):

```bash
    # take your terminal to the desktop
    cd ~/Desktop
    # pull down the code from github, this will create a new folder on your desktop
    git clone https://github.com/charleshtrenholm/paper_helper.git
    # move the terminal into the newly created folder
    cd paper_helper
    # make the necessary folders
    mkdir new_files sorted_files results
```

With python3, we also have this other thing called pip3, which installs speficially python packages. we need to do that to get the thing that turns your output into an excel sheet. In the same folder do:

```bash
    pip3 install openpyxl
```

### Actually doin' it
Now you should be all good to go to run this bad boi. Before you run it, **just to be on the safe side, make sure you have a backup copy of the files somewhere**. Here are the simple steps (code stuff is done):

1. Edit the `interns.txt` file to contain the list of all the names you want the script to check for. You can just do this with TextEdit. Just make sure that each name is capitalized and on a different line. (also don't make it a rich text file)

2. Using finder, you can drag all of your files you want to sort into the `new_files` directory (you'll see it now at Desktop/paper_helper/new_files). Don't worry if they're not formatted correctly, they will just stay in `new_files` if they're not.

3. In the terminal, run `python3 main.py` and it should run. It will move all the files into different appropriate directories in `sorted_files`, and when it's done will open an excel sheet showing who needs what. It will also display in the terminal any files that didn't get sorted and messages about why. You can find older files in the `results` directory.

### Bonus notes

- whenever you want to run it again, you need to make sure you're always in the directory where the code lives. If you get the terminal complaining about "no such file or directory", you're not in the place where it can be run. These 2 commands will get you what you need:

```bash
    cd ~/Desktop/paper_helper
    python3 main.py
```
- Running it again with new files that have the same name as already existing, already sorted files will overwrite the old ones.

- you can move the entire `new_files` directory around if you want (like to Documents or whatever), but just don't move files around individually or the script won't work.