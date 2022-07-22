# Property, Method, 객체

## Method 메소드(멤버 함수)

- 클래스나 객체에 속해 있는 함수
- 객체 내에서 정의된 함수를 의미
- Javascript에서 함수가 객체의 프로퍼티로 저장된다면 이것은 메소드
- 함수로 된 property
- 클래스에 만드는 함수
- 메소드는 주로 객체의 프로퍼티 값을 변경하거나 알아내는 기능과 클래스를 대표하는 기능
- property 는 속성이라면 method 는 행동
- javascript 에서는 괄호로 함수를 호출하므로 대부분 괄호로 끝나면 method, 없으면 property
- ex) listA.length = 프로퍼티 / listA.push(1) = 메소드

```JS
var obj = {
  foo: function() {},
  bar: function() {}
};
obj.foo();
// foo: function() {} 이게 메소드
```

</br>
</br>
## Property

- 키(key)와 값(value)이 연관된 객체(object)의 부분
- 객체 내에서 선언된 변수()를 의미
- 배열 내부에 있는 값들을 요소(), </br>
  Javascript에서는 배열 또한 객체로 표현되기 때문에 요소와 Property는 Javascript에서 사실상 동일
- property는 객체에 포함, 변수는 컨텍스트에 포함

```JS
let person = {
	name: 'sean',
    age: 24
    };
```

객체는 프로퍼티의 집합이라고 할 수 있다.

- 프로퍼티: name: 'sean', age: 24
- 프로퍼티 키: name,age
- 프로퍼티 값: sean, 24

</br>
</br>

## 객체

- Jacascript의 method에서 this는 method가 속한 객체
- 인스턴스 생성 후 클래스에서 제공하는 프로퍼티와 메서드를 사용할 때 주로 사용

```JS
var obj = {
  x: 'local',
  y: 'global'
};
//  obj가 객체
```
