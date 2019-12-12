# [ES6] Enhanced Object Literals - 향상된 객체 리터럴
## Enhanced Object Literals

<br>
### :four_leaf_clover:  속성 메서드 축약
- 객체의 속성을 메서드로 사용할 때 `function` 예약어를 생략하고 생성 가능하다.


###### 예제
```javascript
var dictionary1 = {
    words: 100,

    // ES5
    lookup: function(){
        console.log("find words");
    }

}
```


```javascript
var dictionary2 = {
    words: 100,

    // ES6
    lookup() {
        console.log("find words");
    }

}
```

###### 결과
- `dictionary1.lookup();`과 `dictionary2.lookup();`의 결과가 동일하다.

<br>
### :four_leaf_clover:  속성명 축약
- 객체의 속성명과 값 명이 동일할 때 축약 가능

###### 예제
```javascript
var figures = 10;
var dictionary = {
    // figures: figures,
    figures
}
```
