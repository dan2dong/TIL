# 콜백함수

전달될 당시에 콜백함수를 바로 호출해서 반환된 값을 전달하는 것이 아니라,</br>
콜백함수를 가리키고 있는 함수의 레퍼런스(참조값)가 전달된다.</br>
그래서 콜백함수는 고차함수안에서 필요한 순간에 호출이 나중에 됨

```JS
function double(num) {
  return num * 2;
}
// doubleNum 함수는 고차 함수이다. (다른 함수를 인자로 받음)
// doubleNum 함수의 인자 func에 함수가 들어올 경우
// func은 doubleNum의 콜백 함수이다.
function doubleNum(func, num) {
  return func(num);
}
// 아래의 경우 double은 doubleNum의 콜백 함수이다.
doubleNum(double, 5);
```

## 일급객체(first-class object)

일반 객체처럼 모든 연산이 가능한 것

- 함수의 매개변수로 전달
- 함수의 반환값
- 할당 명령문
- 동일 비교 대상
  </br>
  </br>

## 고차함수(Higher-order function)

- 인자로 함수를 받거나(콜백함수)
- 함수를 반환하는 함수
