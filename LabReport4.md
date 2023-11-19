# Lab Report 4: Vim
## Log in to ieng6
![Log in Image](log-in-ieng6.png)

Keys Pressed: `Ctrl R` `s` `<enter>`

To save time from writing out the whole command for logging in to ieng6, I used `Ctrl R` to search through my command history and typed the beginning letter to the command `s` which autocompleted to `ssh cs15fa23fd@ieng6.ucsd.edu`. I then pressed `<enter>` to execute the command and log in to ieng6.

## Clone Fork to Repository
![Clone Fork Rep Image](clone-fork.png)

Keys Pressed: `Ctrl R` `cl` `<enter>`
I once again used `Ctrl R` to search through my command history and first typed out `c` but when the autocomplete command did not match the desired command that clones my fork of the lab 7 repository, I continued by typing `cl` which autocompleted to the correct command `git clone git@github.com: KacyUmana/lab7.git`. I then pressed `<enter>` to execute the command.

## Run Failing Tests
![Fail Tests Image](fail-tests.png)

Keys Pressed: `cd l` `<tab>` `<enter>` `Ctrl R` `ba` `<enter>`

In order to be able to run the failing tests I first need to `cd` into the directory that the `test.sh` file resides in. I typed out the command `cd` and then typed out the first letter of the directory `l` and pressed `<tab>` which autocompletes to the name of the directory `lab7`. I then pressed `<enter>` to execute to command and change into the directory `lab7`. I pressed `Ctrl R` to search for the desired command that runs the tests `bash test.sh`, I typed the letters of `bash` until it autocompleted to the correct command which was `ba` and finally pressed `<enter>` to execute the command to ensure that the tests run successfully. 

## Fix Failing Test
![Edit Fix Image](edit-fix.png)

Keys Pressed: `vim L` `<tab>` `.java` `<enter>` `j` x43 `l` x11 `x` `<enter>` `<esc>` `i` `2` `<enter>` `<esc>` `<esc>` `:wq` `<enter>`

To edit the `ListExamples.java` file and fix the mistake causing the tests to fail, I typed the command `vim` followed by the first letter of the desired file `L` then pressed `<tab>` so that it autocompletes to `ListExamples`. I manually typed the rest of the file name `.java` and pressed `<enter>` to execute the command. Once the file loaded on vim, I pressed `j` 43 times for the cursor to land on the line that needs to be fixed. I then pressed `l` 11 times to move the cursor to the left until it lands on the character I wish to delete which is the `1` in `index1`. I pressed `x` to delete the character `1` and pressed `<enter>` to execute the command. I pressed `esc` to exit .. mode and return back to normal mode. I pressed `i` and pressed `2` to insert the 2 at the end of `index` so that it becomes `index2` and pressed `<esc>` to exit insert mode and return to normal mode. 

## Run Succeeding Tests
![Succeeding Tests Image](succeed-tests.png)

Keys Pressed: `<up>` `<up>` `<enter>`

The `bash test.sh` command was 2 up the search history, thus `<up>` was pressed twice to access it and `<enter>` was pressed to execute the command in order to run the tests again to ensure they are successful.

## Commit and Push Changes
![Commit Push Image](commit-push.png)

Keys Pressed: `Ctrl R` `ad` `<enter>` `Ctrl R` `com` `<enter>` `Ctrl R` `pu` `<enter>`

In order to be able to commit the changes that were made to the `ListExamples.java` file 
