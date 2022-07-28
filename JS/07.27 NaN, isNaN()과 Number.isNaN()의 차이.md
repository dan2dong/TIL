# NaN, isNaN()과 Number.isNaN()의 차이

## Not-A-Number

### NaN

NaN은 Not-A-Number(숫자가 아님)을 나타내는 전역 객체의 속성이다. Number.NaN의 값과 같다.</br>
최신 브라우저에서 NaN은 설정 불가, 쓰기 불가한 속성이다.
</br>

### NaN을 반환하는 경우는 다음과 같다.

- 숫자로서 읽을 수 없는 경우 ex) parseInt('text'), Number(undefined)
  // Math.sqrt(): 제곱근(루트)을 구하는 메서드
- 결과가 허수인 수학 계산식 ex) Math.sqrt(-1)
  // **: 거듭 제곱 연산자 ex) 2 ** 3의 연산결과는 8이다.
- 피연산잔가 NaN인 경우 ex) (7 \*\* NaN)
- 정의할 수 없는 계산식 ex) (0 \* Infinity)
- 문자열을 포함하면서 덧셈이 아닌 계산식 ex) ('안녕'/ 3)
  </br>

### NaN 판별

NaN은 다른 모든 값과 비교(==,!=, === ,!==)했을 때에도 같지 않고, 다른 NaN과도 같지 않다. </br>
그래서 NaN을 판별할 때는 isNaN() 또는 Number.isNaN()을 사용하면 가장 분명하게 NaN을 판별할 수 있다.

```JS
NaN === NaN // false
Number.NaN === NaN // false
isNaN(NaN) // true
isNaN(Number.NaN) // true

```

## Number.NaN

Number.NaN은 Not-A-Number(숫자가 아님)을 나타내며, NaN과 같다. </br>

### NaN과 Number.NaN은 Not-A-Number 나타낸다는 점에서 같다.다만 NaN은 비교연산을 했을 때 어떤 다른 NaN과도 같지 않다는 점을 기억하자

 </br>

## isNaN() vs Number.isNaN()

isNaN(value)과 Number.isNaN(value)은 value가 NaN인지 판별할 때 쓰인다. 그러나 둘은 분명히 다르다. </br>

```JS
isNaN('hello world'); // true
Number.isNaN('hello world'); // false
```

'hello world'는 숫자가 아닌 문자열이다. 일단 숫자가 아니므로(Not-A-Number) isNaN()에선 true를 리턴한다.</br>
그러나 isNaN()과 같은 기능을 할 것 같은 Number.isNaN()에선 왜 false를 리턴하는지 알아보자.</br>
이는 두 메서드가 NaN인지 판별하는 방식이 서로 다르기 때문이다.</br>

### isNaN()

- 인자로 들어온 값이 NaN이거나, 값을 숫자로 변환했을 때 NaN이면 참(true)을 리턴한다.
  이렇듯 isNaN()은 인자를 숫자로 변환하는 과정을 거쳐 판별한다.

### Number.isNaN

- 인자로 들어온 값이 NaN이어야만 참(true)을 리턴한다.
  isNaN()에서는 인자를 Number로 변환한 뒤, NaN이면 true를 리턴하기 때문에 isNaN('hello world')의 경우 true이다.
  Number.isNaN()에서는 false를 리턴한한다. 그 이유는 문자열은 숫자가 아닌것은 맞지만, 그 자체가 NaN이 아니기 때문이다.
  문자열인 'hello world'은 그 자체로 NaN이 아니다.

</br>
</br>

```JS
isNaN(null); // false
Number.isNaN(null); // false

isNaN('25'); // false // "25"는 숫자 25로 변환된다.
isNaN('25.25'); // false // "25.25"는 숫자 25.25로 변환된다.

Number.isNaN(NaN); // true
Number.isNaN(Number.NaN); // true

Number.isNaN({}); // false, {} is not NaN
Number.isNaN('hello'); // false, 'hello' is not NaN
Number.isNaN(NaN); // true, NaN is NaN
Number.isNaN('happy' / 'coding'); //true, 'happy'/'coding' is NaN -> NaN is NaN

isNaN({}); // true, {}는 숫자로 변환하면 NaN이다.
isNaN('hello'); // true, 'ponyfoo' is not a number
isNaN(NaN); // true, NaN is not a number
isNaN('happy' / 'coding'); // true, 'happy'/'coding' is NaN -> NaN is not a number

```

</br>
</br>

### 여러가지 값을 숫자로 변환했을 때 어떻게 되는지 알아보자

```JS
// 여러가지 값을 숫자로 변환해보자.
Number(null); // 0 // null은 숫자로 변환하면 0이다.
Number(''); // 0
Number('      '); // 0
Number(false); // 0
Number(''); // 0
Number([]); // 0
Number({}); // NaN
```

</br>
</br>

### NaN과 Infinity

```JS
isNaN(5 / 0); // false // (5/0) is Infinity -> Infinity is a number
isNaN(0 / 0); // true // (0/0) is NaN -> NaN is NaN
Number.isNaN(5 / 0); // false // Infinity is not NaN
Number.isNaN(0 / 0); // true // (0/0) is NaN -> NaN is NaN

0 / 0; // NaN
5 / 0; // Infinity
-5 / 0; // -Infinity

0 * Infinity; // NaN
1 * Infinity; // Infinity

Number(Infinity); // Infinity
Number(-Infinity); // -Infinity
```

</br>

### NaN 과 배열 메서드

배열 안에서 찾으려는 값(searchElement)과 정확하게 일치(===)하는  '첫번째' element의 index를 리턴.

```JS
arr.indexOf(searchElement,fromIndex)
```

</br>
일부 배열 메서드에서는 NaN을 찾을 수 없다.

```JS
let arr = [2, 4, NaN, 12];
arr.indexOf(NaN); // -1 (false)
arr.includes(NaN); // true
arr.findIndex((n) => Number.isNaN(n)); // 2
```
