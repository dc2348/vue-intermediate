# [ES6] Modules - 자바스크립트 모듈화 방법

# Modules
- ES5에서는 모듈화 방법이 업었음(파일을 나누어도 스코프는 동일)
- 따라서  자바스크립트 모듈 로더 라이브러리(AMD, Commons JS)등을 이용하여 모듈화를 하였었음
- ES6에서는 모듈화 기능을 js언어 자체에서 지원
- 호출되기 전까지는 코드 실행과 동작을 하지 않는 특징이 있음

###### 예제
```javascript
// libs/math.js
export function sum(x, y) {
    return x + y;
}
export var pi = 3.131593;
```

```javascript
//main.js
import {sum} from 'lib/math.js';
sum(1, 2);
```

- import될 때 export가 실행됨.
- export 간에는 다른 스코프를 가짐.

<br>

### :four_leaf_clover: export default
```javascript
// util.js
export default function(x){
    return console.log(x);
}
```

```javascript
// main.js
import util from 'util.js';
console.log(util);
util("hi");
```

```javascript
// app.js
import log from 'util.js';
console.log(log);
log("hi");
```
- `export default`는 한 개의 파일에서 하나 밖에 `export`가 되지 않음
- 캡슐화(incapsulation)하는 것임.
