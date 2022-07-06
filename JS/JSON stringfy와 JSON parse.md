# JSON stringfy와 JSON parse

- JSON이란 JavaScript Object Notation의 약자로서 데이터를 문자열의 형태로 나타내기 위해서 사용된다.
  이름이 암시하듯 JSON은 본래 자바스크립트에서 파생되었지만, 현재는 거의 표준으로 자리잡아 대부분의 다른 프로그래밍 언어에서도 지원하는
  데이터 포맷이다. JSON을 데이터 교환 목적으로 사용하는 경우가 많다.
  </br>
  </br>
  자바스크립트가 제공하는 JSON관련 메소드는 JSON.stringfy ,JSON.parse가 존재한다.
  </br>

### JSON.stringify() : Javascript 객체나 값을 JSON 문자열로 변환한다.

ex)

```JS
  const obj ={
    name: 'kim',
    weight: 60,
    height: 175,
    age: 20
  }

  const info = JSON.stringfy(obj)
  console.log(info)

  //'{'name':'kim','weight':'60', 'height':'175','age':'20'}' 이렇게 출력된다.
```

### JSON.parse() : JSON문자열을 Javascript 객체로 변환한다.

ex)

```JS
  const info = {
    'name': 'kim',
    'weight': 60,
    'height': 175,
    'age': 20
  }

  const obj = JSON.parse(info)
  console.log(obj)
  /* JSON 문자열 형태의 데이터가 JavaScript 객체의 형태로 변환되어 출력된다.

    const obj ={
      name: 'kim',
      weight: 60,
      height: 175,
      age: 20
    }
    이렇게 출력된다.
  */
```
