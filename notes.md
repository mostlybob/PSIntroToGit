# Introduction to Git
## 2016-01-03
### Branches (cont'd)
- created file on master & committed
  - now shows the divergence in ```gitk```
- demonstrate ```rebase```
  - my local stuff is sufficiently different from what he's doing in the video, I'm not entirely sure how it's going to go
  - ```rebase``` is one of those things I've never quite got the hang of
  - just to be safe, I'm committing here
- that was fun (not, but educational)
  - not surprisingly, my work on ```notes.md``` on different branches caused trouble with the rebase, with multiple conflicts needing to be resolved
  - here's something learned about conflicts, esp. during rebase:
    - the last line, with the ```>>>>>>>>``` (something like anyway), shows the commit message, not something from the file itself
    - once the file is how you want it, issue ```git add <filespec>``` before ```git rebase --continue```
      - may have to resolve successive conflicts until the whole file is fixed
  - all is (apparently) well; time to commit and resolve (heh) not to fiddle with ```notes.md``` on different branches again

## 2016-01-02
### Basic Commands (cont'd)
- ```git commit -v```
  - adds a diff in the commit message
    - I found I had to do ```-va``` since ```-v``` on its own caused git to complain about unstaged changes
- ```git log```
  - shows a log of commits with excerpts of commit messages
  - ```--stat``` adds some more detail to what happened in each commit
  - ```-p``` adds actual content of change
    - this one's a lot more verbose

### Branches
- using ```gitk```
  - my install doesn't include it (Korora 23)
    - ```sudo dnf install gitk``` fixed that
  - ```~/.gitk``` to edit settings
    - esp font face & size
    - I don't appear to have one, by default, but I can create it
      - another dotfile to think about tightening up my management of :P
    - doesn't appear to have any effect, but the app does have a way to change settings through the UI, so I'm not going to fuss with this
- why branch?
- to ease following along, I'll use the branch names he does on this repo
  - I guess I'll use this notes file do that
- ```git branch human```
  - creates the branch without switching to it
- ```git checkout human```
  - checks it out
- ok, turns out I do want a file that is specific to this branch
  - creating a new file ```human.rb``` to follow along with his example
- ```git commit -va``` to see contents with commit message
- interesting to watch ```gitk``` as I switch between branches
- his example of continuing to work on the master branch would need a file on ```master``` (not this file - trying to avoid merge conflicts) that was also on ```human``` to illustrate the "branching" observed in ```gitk``` when different files on the respective branches are being edited
- (this is a side note on my own fiddling around) as expected, I made a change to this file on ```master``` (fixed the markdown starting on this Branches section) and when I tried to merge it to ```human``` it had conflicts that had to be resolved. Lesson learned. 

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
