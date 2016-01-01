# Introduction to Git
## 2016-01-01
### Basic Commands
- some overlap from before
- ```.gitignore```
- ```./.git/info/exclude```
- ```git add .```
- ```git status```
- ```git commit -m```
- ```git ls-files```
  - a new one for me
  - shows files currently being tracked in the git repo
  - shows possible files for addition to ```.gitignore```
  - remove those files with ```git rm <file>```
- ```git commit -a```
  - shows editor interface for adding messages to commit
  - I'm a bit out of practice, since I mostly use ```git commit -am <commit message>```

## 2015-12-30
Since this is an intro course, I expect most of it will be review, but that's ok. Since we're using it at work, I suspect there might be a few blank spots in my knowledge. As I find them, I want to mark them here. 

- the use of ```~/.gitconfig```
  - mine's pretty sparse, but using it to define some aliases might be handy, thinking ```pom``` for ```push origin master``` for example
  - I need to work on my syncing and back up of dot files; I had that going at one point for things like ```.bashrc``` and ```.conkyrc```

- content of the .git folder
  - as he said, most of it is below my 'need to know' but one place that looks interesting is the ```hooks``` folder that has defined events for putting actions to be done
  - simple shell scripts
  - defaults are appended with ```.sample``` 
  - I suppose removing the file extension would activate them

- ```.gitignore```
  - can put ```.gitignore``` files in any folder under source control, but his preference is to keep it at the root and consolidated there
    - mine too, fwiw
  - ```./.git/info/exclude```
    - is not checked in, unlike ```.gitignore```
    - can be used for local cases that will not apply to others using the repo

- ```git ls-files```
  - displays files currently being tracked in the repo

- ```git rm <filespec>```
  - does it delete the file from the director?
  - testing with the creation of a scratch file and committing
    - added scratch
    - added to tracking
    - committed it
    - pushed to master
    - issue ```git rm scratch```
      - ```git status``` shows message that scratch has been deleted
      - it is also removed from the file system
      - **might be good to find out how to just stop tracking the file without deleting it from the FS**


-----