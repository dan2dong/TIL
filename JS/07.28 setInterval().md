# setInterval()

setInterval() 함수는 주기적으로 인자를 실행한다.

### setInterval(콜백함수, 시간)는 "시간(ms)"을 간격으로 "콜백함수"를 반복 호출 하는 함수이다.

1.let 변수 = setInterval(콜백함수, 시간)
</br></br>
2.clearInterval(변수)로 반복중단
clearInterval(변수)
</br></br>
3.setInterval()함수의 반환값을 변수에 재할당하여 재시작</br>
변수 = setInterval(콜백함수, 시간);

- 사용예시

```JS
let interval = setInterval(callback, 1000);

function callback() {
	console.log('a');
}
```

이렇게 1000ms 마다 callback 함수를 호출할 수 있다.
이 반복을 중단하려면,

```JS
clearInterval(interval);
```

그 후 다시 호출하려면 ,

```JS
interval = setInterval(callback, 1000);
```

다시 변수에 담아주면 된다.
</br>
</br>
다른 예시

```JS
function test() {
  console.log("Hello!");
}
setInterval(test, 3000);
```

- 위 test 함수에 인자가 있다면?

```JS
function test(string) {
  console.log(string);
}
setInterval(function() {
  test("Hello!");
}, 3000);
```
