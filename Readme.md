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

## Make app remember username

To make the app remember the username, we have used preventDefault() method to remove the default behavior of input box. Then give required actions following the method. By the way, we use localStorage to store that info.

```
function handleSubmit(event) {
  event.preventDefault();
  const currentValue = input.value;
  paintGreeting(currentValue);
  saveName(currentValue);
}
```

## Add To-Do functions

To add to-dos to the list, we use a method called "createElement()". Using the input text, we append elements and then append them to <ul> in html.

```
function paintToDo(text) {
  const li = document.createElement("li");
  const delBtn = document.createElement("button");
  delBtn.innerText = "❌";
  const span = document.createElement("span");
  span.innerText = text;
  li.appendChild(delBtn);
  li.appendChild(span);
  toDoList.appendChild(li);
}
```
