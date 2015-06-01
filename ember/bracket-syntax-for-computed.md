#Bracket Syntax for Computed Properties

So you want to observe multiple properties on a single object in ember?

You would normally write it as:

```javascript
fullName: function() {
  return this.get('user.firstName') + ' ' + this.get('user.lastName');
}.property('user.firstName', 'user.lastName')
```


As of Ember 1.4, you can use property brace expansion for an abbreviated syntax:

```javascript
fullName: function() {
  return this.get('user.firstName') + ' ' + this.get('user.lastName');
}.property('user.{firstName,lastName}')
```
