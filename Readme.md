# To Do List Web Application

## This project is to practice javascript creating to-do-list.

## Date Object and setInterval()

We will get time from Date object and will refresh it every second.  
Since the Date object returns single digit when it is < 10, we have to take care about it.

```
clockTitle.innerText = `${hours < 10 ? `0${hours}` : hours}:${
    minutes < 10 ? `0${minutes}` : minutes
  }:${seconds < 10 ? `0${seconds}` : seconds}`;
```

---

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

---

## Add To-Do functions

To add to-dos to the list, we use a method called "createElement()". Using the input text, we append elements and then append them to ul tag in html.

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

---

## Save to-dos in localStorage

Create a object to store text and id and then push that object to array.

```
const toDoObj = {
    text: text,
    id: newId,
  };
```

### Use JSON.stringify() to conver a object to string so that we can store it in localStorage.

```
function saveToDos() {
  localStorage.setItem(TODOS_LS, JSON.stringify(toDos));
}
```

### Used JSON.parse() to parse string to object

```
const parsedToDos = JSON.parse(loadedToDos);
    parsedToDos.forEach(function (toDo) {
      paintToDo(toDo.text);
    });
```

---

## Update deleted list

When a user click delete button, we have to update "toDos" array. So, put event target in "btn" and get its parendNode which is going to give us id of clicked list. Then, using filter() function, we will create new array and assign it to "toDos".

```
function deleteToDo(event) {
  const btn = event.target;
  const li = btn.parentNode;
  toDoList.removeChild(li);
  const cleanToDos = toDos.filter(function (toDo) {
    return toDo.id !== parseInt(li.id);
  });
  toDos = cleanToDos;
  saveToDos();
}
```
