# Introduction to Git
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
