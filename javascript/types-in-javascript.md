# Types in Javascript 

If you're looking to see if something is an Array or an Object in Javascript, you actually can't use `typeof`, because an Array is technically an Object.

To check if something is in fact an array, you can try
  
```javascript
var data = ["one", "two", "three"];
// typeof data === Object

function isArray(data) {
  return Object.prototype.toString.call(data) == '[object Array]';
}

isArray(data);
// true!
```

Tada!
