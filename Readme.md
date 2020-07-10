# To Do List Web Application

This project is to practice javascript creating to-do-list.

## Date Object and setInterval()

We will get time from Date object and will refresh it every second.  
Since the Date object returns single digit when it is < 10, we have to take care about it.

```
clockTitle.innerText = `${hours < 10 ? `0${hours}` : hours}:${
    minutes < 10 ? `0${minutes}` : minutes
  }:${seconds < 10 ? `0${seconds}` : seconds}`;
```
