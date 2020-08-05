---
title: "클래스 선언 방법 (ES5)"
---

클래스 선언 방법 (ES5).

### 리터럴 방식
```js
var 인스턴스 = {
  프로퍼티1 : 초기값,
  프로퍼티2 : 초기값,
  메서드1 : function() {

  },
  메서드2 : function() {

  }
}
```

### 함수 방식
```js
function Person() {
    this.name = '';
    this.age = 초기값;

    this.메서드1 = function() {

    }

    this.메서드2 = function() {

    }
}

var 인스턴스 = new 클래스이름(); 
```


### 프로토타입(prototype) 방식
```js
function 클래스이름() {
  this.프로퍼티1 = 초기값;
  this.프로퍼티2 = 초기값;
}

클래스이름.prototype.메서드1 = function() {

}

클래스이름.prototype.메서드2 = function() {

}
```


### 생성자, 프로토타입
```js
var Person = (function () {
  // Constructor
  function Person(name) {
    this._name = name;
  }
 
  // method
  Person.prototype.sayHi = function () {
    console.log('Hi! ' + this._name);
  };
 
  // return constructor
  return Person;
}());
 
var me = new Person('Lee');
me.sayHi(); // Hi! Lee.
 
console.log(me instanceof Person); // true
```


### 리터럴 방식
```js
var Client = (function() {
  "use strict";

  var $this = {};

  $this.init = function(name, settings) {
    $this.name = name;
    $this.settings = settings || {};
    console.log("init()-" + $this.name, $this.settings);
  }

  $this.clear = function() {
    console.log("clear()");
  }

  return {
    init: $this.init,
    clear: $this.clear
  }
})();

Client.init("client", {'key1':'val1', 'key2':'val2'});
Client.clear();
```
