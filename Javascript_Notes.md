
* ### get members, functions, properties, prototype things, etc of an object

```javascript
let obj = new myClass()

const allProperties = [];
for (const key in obj) {
    allProperties.push(key);
}
console.log("all properties: ", allProperties);
```