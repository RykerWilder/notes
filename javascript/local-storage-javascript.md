# JavaScript Local Storage

Local Storage is a browser API that allows us to create, read, modify, and delete data in the browser. However, these records are limited to the browser, which means, for example, that data stored in Chrome is not available in Firefox.

---

### Convert to JSON

The data in the local storage is in JSON format, so before inserting the data, we need to convert the JavaScript objects to JSON format.
To do this we will use the **stringify()** function, inserting as a parameter the object to be transformed into JSON.

```javascript
const person = {
    name: "Ryker",
}
const personToJSON = JSON.stringify(person);
```

---

### Insert JSON into Local Storage

To insert data inside we will use the **setItem()** function which accepts the record key as the first parameter and the value as the second parameter.

```javascript
localStorage.setItem("person", personToJSON);
```

---

### Retrieve data

To retrieve data we will use the **getItem()** function, in which we will insert the record key as a parameter.

```javascript
const personJSON = localStorage.getItem("person");
```

---

### Convert to JavaScript object

After fetching some data we will use the ***parse()*** function to transform the data into a JavaScript object.

```javascript
const JSONToPerson = JSON.parse(personJSON);
```

---

### Delete data

To delete data from Local Storage, simply use the **removeItem()** function, passing the record key as a parameter.

```javascript
localStorage.removeItem("person");
```