---
title: "Taskwarrior Project Templates? Yes Please!"
date: 2019-09-02T08:00:00
draft: false
cover: "/img/templates.jpg"
url: /blog/taskwarrior-project-templates-yes-please
tags:
- Business
- Mindset
- Life
- Taskwarrior
---

{{< youtube I_BGFK6XA4k >}} 

## Creating a project template from an executable file

First, open a new file using nano:

`sudo nano videofile`

Next, add your tasks, separated by a new line:

record video 
edit video 
upload video 

Then just add "task add" to the front of each line:

_task add_ record video 
_task add_ edit video 
_task add_ upload video 


Now exit the file and save:

`ctrl + x`\
`y`

And now we can make the file executable:

sudo chmod +x videofile`

Now we can create all those tasks simply by executing that file:

`./videofile`

NOW, in order to bake in the dependencies, we need to add some stuff to the line items in the file. So we go back into that file:

```sudo nano videofile```

And change the first line to

```recordstring=`task add record video```

Then enter a new line beneath that:

```recordid=`echo $recordstring | grep -o -E '[0-9]+'```

Then just repeat that process for each task.

The last thing we need to do is use the variable for the _id_ in the creation of the task. So the task for editing the video will look like this:

```
editstring=`task add edit video $recordid`
editid=`echo $recordstring | grep -o -E '[0-9]+'
```

Etc.

Drop a comment below if you have any questions. 

