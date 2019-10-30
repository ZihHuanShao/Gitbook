# Object

## function的不同意義

### 作為屬性

`person`為一`object(物件)`，`fullname`是函式也是`person`的屬性

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

```javascript
// 注意有加()的差異

// 回傳John Doe
person.fullName();

// 回傳function() { return this.firstName + " " + this.lastName; }
person.fullName;
```

{% embed url="https://www.w3schools.com/js/js\_object\_methods.asp" %}

### 作為建構函式

`person物件`的建構函式：

```javascript
// Constructor function for Person objects
function Person(firstName,lastName,age,eyeColor) {
  this.firstName = firstName;
  this.lastName = lastName;
  this.age = age;
  this.eyeColor = eyeColor;
  this.changeName = function (name) {
    this.lastName = name;
  }
}
```

{% hint style="info" %}
You cannot add a new method to an object constructor the same way you add a new method to an existing object.

Adding methods to an object constructor must be done inside the constructor function:

若要將函式加到物件建構函式，必須寫在物件建構函式裡面
{% endhint %}

如何呼叫物件建構函式裡的函式：

```javascript
// Create a Person object
var myMother = new Person("Sally","Rally",48,"green");

// Change last name
myMother.changeName("Doe");
```

{% embed url="https://www.w3schools.com/js/js\_object\_constructors.asp" %}



