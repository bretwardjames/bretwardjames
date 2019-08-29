---
title: "Taskwarrior + Timewarrior = Freelancing Bliss!"
date: 2019-08-28T08:00:00
draft: false
featured_image: "timew.jpg"
url: /blog/taskwarrior-timewarrior-freelancing-bliss
categories:
- Business
- Mindset
- Life
- Taskwarrior
---

{{< youtube f_Be0CUVvA4 >}} \

Copy this command right into your terminal after navigating to the `~/.task/hooks` directory:

```wget https://raw.githubusercontent.com/GothenburgBitFactory/timewarrior/dev/ext/on-modify.timewarrior```


# Setting up Timewarrior with Taskwarrior

First, install Timewarrior:

```sudo apt-get install timewarrior```

Once it's installed, initialize Timwarrior:

```timew```

The next thing you want to do is install the hook to start time tracking when a task is started in Taskwarrior:

```cd ~/.task/hooks
wget https://raw.githubusercontent.com/GothenburgBitFactory/timewarrior/dev/ext/on-modify.timewarrior
sudo chmod +x on-modify.timewarrior```

Now, just start a task:

```task start 1```

and the time tracking will start automatically.

Dope. Tastic.
