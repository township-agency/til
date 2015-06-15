# Is that bit empty?

We often have to check if something's empty. Be it a string, an array, or a dictionary, we care a lot about whether or
not something is empty. Swift provides a really damn simple way to test it.

### The old way - silly Objective-C

```objective-c
// NSString
if (myString == nil){
  // it's empty
}

if (myArray == nil || myArray.length == 0){
 // it's empty
}
```

### The Swift way

```swift
if (myObject.isEmpty){
  // it's empty! 
}
```
