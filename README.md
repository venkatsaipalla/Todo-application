# Todo-application
# Todos Application | **Part 1** | Cheat Sheet

**1. HTML Input Element**

*1.1 Checkbox*

    The HTML input element can be used to create a Checkbox. To define a Checkbox, you need to specify the HTML type attribute with the value checkbox for an HTML input element.

``` 
<input type="checkbox" />
```
*1.2 The HTML Label Element*

    The HTML label element defines a Label.

```
<label for="myCheckbox">Graduated</label>
```

*1.2.1 The HTML for Attribute*

    The HTML for attribute associates the HTML label element with an HTML input element.

```
<input type="checkbox" id="myCheckbox" />
<label for="myCheckbox">Graduated</label>
```

**2. DOM Manipulations**

*2.1 The htmlFor Property*

    We can use htmlFor property to add HTML for attribute to the HTML label element.
```
let labelElement = document.createElement("label");
labelElement.htmlFor = "myCheckbox";
```

*2.2 The setAttribute() Method*
    We can use setAttribute() method to set any HTML attribute name and its corresponding value. If the attribute already exists, the value is updated. Otherwise, a new attribute is added with the specified name and value.

Syntax: Element.setAttribute(name, value);
```
let labelElement = document.createElement("label");
labelElement.setAttribute("for", "myCheckbox");
```
#
# Todos Application | **Part 2** | Cheat Sheet

**1. HTML Input Element**

*1.1 Placeholder*

    Placeholder is the text that appears in the HTML input element when no value is set. We can specify it using the HTML attribute  placeholder.
```
<input type="text" placeholder="Enter your name" />
```
**2. JavaScript Built-in Functions**

*2.1 alert()*

    The alert() function displays an alert box with a specified message and an OK button.

```
alert("Enter Valid Text");
```
**3. DOM Properties**

*3.1 Checked*

    The checked property sets or returns the checked status of an HTML checkbox input element as a boolean value.

```
let checkboxElement = document.getElementById(checkboxId);
checkboxElement.checked = true;
```

**4. DOM Manipulations**

*4.1 The removeChild() Method*

    The removeChild() method removes an HTML child element of the specified HTML parent element from the DOM and returns the removed HTML child element.

```
function onDeleteTodo(todoId) {
  let todoElement = document.getElementById(todoId);

  todoItemsContainer.removeChild(todoElement);
}
```
*4.2 The classList.toggle() Method*

    The classList.toggle() method is used to toggle between adding and removing a class name from an HTML element.

```
function onTodoStatusChange(checkboxId, labelId) {
  let checkboxElement = document.getElementById(checkboxId);
  let labelElement = document.getElementById(labelId);

  labelElement.classList.toggle('checked');
}
```
We can replace classList.add() and classList.remove() methods with classList.toggle() method.

#
# Todos Application | Part 3 | Cheat Sheet

**1. Execution Context**

The environment in which JavaScript Code runs is called Execution Context.

Execution context contains all the variables, objects, and functions.

Execution Context is destroyed and recreated whenever we reload an Application.

**2. Storage Mechanisms**

*2.1 Client-Side Data Storage*

    Client-Side Data Storage is storing the data on the client (user's machine).

Local Storage
Session Storage
Cookies
IndexedDB and many more.

*2.2 Server-Side Data Storage*

    Server-Side Data Storage is storing the data on the server.

**3. Local Storage**

It allows web applications to store data locally within the user's browser.
It is a Storage Object. Data can be stored in the form of key-value pairs.
Please note that both key and value must be strings. If their type is other than a string, they get converted to strings automatically.

|  Key	| Value |
|-------|-------|
| fullName | Rahul Attuluri |
| gender |	Male|
| city	| Delhi|

To access and work with Local Storage we have below methods:

**setItem()**

**getItem()**

clear()

removeItem()


*3.1 The setItem() Method*
    The setItem() method can be used for storing data in the Local Storage.

*Syntax: localStorage.setItem("Key", "Value");*

*3.2 The getItem() Method*
    The getItem() method can be used for getting data from the Local Storage.

**Syntax**: localStorage.getItem("Key");

#
# Todos Application | Part 4 | Cheat Sheet

**1. JavaScript Object Notation (JSON)**

JSON is a data representation format used for:

Storing data (Client/Server)

Exchanging data between Client and Server

**1.1 Supported Types**
Number

*String

*Boolean

*Array

*Object

*Null

**1.2 JS Object vs JSON Object**

In JSON, all keys in an object must be enclosed with double-quotes. While in JS, this is not necessary.

**JS:**
```
let profile = {
  name: "Rahul",
  age: 29,
  designation: "Web Developer"
};
```

**JSON:**
```
let profile = {
  "name": "Rahul",
  "age": 29,
  "designation": "Web Developer"
};
```

**1.3 JSON Methods**

**1.3.1 JSON.stringify()**

It converts the given value into JSON string.

*Syntax*: JSON.stringify( value )

**1.3.2 JSON.parse()**

It parses a JSON string and returns a JS object.

*Syntax*: JSON.parse( string )

#
# Todos Application | Part 5 | Cheat Sheet

**1. Array Methods**
| Method	|Functionality|
|----|----|
|includes, indexOf, lastIndexOf, find, findIndex()	|Finding Elements|
|push, unshift, splice	|Adding Elements|
|pop, shift, splice	|Removing Elements|
|concat, slice	|Combining & Slicing Arrays|
|join	|Joining Array Elements|
|sort	|Sorting Array Elements|

**1.1 splice()**

The splice() method changes the contents of an array.

Using splice() method, we can

Remove existing items,
Replace existing items,
Add new items

**1.1.1 Removing existing items**

**Syntax**: arr.splice(Start, Delete Count)

Start: Starting Index
Delete Count: Number of items to be removed, starting from the given index

```
let myArray = [5, "six", 2, 8.2];
myArray.splice(2, 2);

console.log(myArray);  // [5, "six"]

let deletedItems = myArray.splice(2, 2);

console.log(deletedItems);  // [2, 8.2]
```

The splice() method returns an array containing the deleted items.

**1.1.2 Adding new items**

**Syntax**: arr.splice(Start, Delete Count, Item1, Item2 ... )

Here the Item1, Item2 ... are the items to be added, starting from the given index.

```
let myArray = [5, "six", 2, 8.2];
myArray.splice(2, 0, "one", false);

console.log(myArray);  // [5, "six", "one", false, 2, 8.2]
```

**1.1.3 Replacing existing items**

*Syntax*: arr.splice(Start, Delete Count, Item1, Item2 ... )
```
let myArray = [5, "six", 2, 8.2];
myArray.splice(2, 1, true);

console.log(myArray);  // [5, "six", true, 8.2]
```
**1.2 findIndex()**
The findIndex() method returns the first item's index that satisfies the provided testing function. If no item is found, it returns -1.

*Syntax*: arr.findIndex(Testing Function)

Here Testing Function is a function to execute on each value in the array.

```
let myArray = [5, 12, 8, 130, 44];
let itemIndex = myArray.findIndex(function(eachItem) {
  console.log(eachItem);
});
```

In the above code snippet, the below function is a Testing Function.
```
function(eachItem) {
  console.log(eachItem);
}
```

#
# Todos Application | Part 6 | Cheat Sheet

**1. Local Storage**

*1.1 The removeItem() Method*

The removeItem() method removes the specified storage object item based on the key.

*Syntax*: localStorage.removeItem(key)

Key - Name of the key to be removed

```
localStorage.removeItem("todoList");
```

![Screen shot ](https://res.cloudinary.com/dxejhgtqt/image/upload/v1664648576/samples/Screenshot_31_wgkfce.png)
