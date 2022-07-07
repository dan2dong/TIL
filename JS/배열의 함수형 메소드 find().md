# 배열의 함수형 메소드 find()

## .find

- 배열 내에서 항목을 찾는데 도움을 준다.

```JS
  function findAvocado(currentFruit){
    return currentFruit === "avocado"
  }
  const fruits = ['apple','banana', 'watermelon', 'avocado']
  const getAvocado = fruits.find(findAvocado)

  console.log(getAvocado)
```

- 모든 메소드들과 마찬가지로 필요한 parameter가 하나뿐이고,
  그것은 콜백함수(callback function)이다.
  콜백함수는 우리가 호출하는 것이 아니라, 우리는 함수의 이름만 적으면 된다.
  JS가 함수를 호출할 것이고, 또한 유용한 인수(arguments)와 함께 호출할 것이다.

- .find의 경우 JS는 findAvocado 함수를 호출하고
  과일 배열의 각 과일 첫번째 인수와 함께 호출한다.
  조건에 맞는 값 중 첫번째 값을 리턴한다.
  만약 배열에 조건을 만족하는 값이 없으면 undefined를 리턴한다.
  콜백함수에 있는 파라미터 이름은 중요하지 않다.
  currentFruit같이 마음대로 지어도 된다.
  중요한 것은 position이다.

- 각 메소드에는 콜백함수가 수행하는 직업에 대한 규칙이 있다.
  .find 규칙은 콜백함수가 'true'를 반환하는 경우에 우리가 찾고 있던 항목을 찾았음을 의미.
  'findAvocado' 함수에서 'true'가 되는 조건은 'currentFruit'이 'avocado'랑 같으면 된다.
  그렇지 않으면 false이다.
  'findAvocado'함수가 'true'를 리턴한 후, 처리 중인 현재 항목은 .find 함수의 결과 값이 될 것이다.
  이것이 변수 getAvocado가 보유하게 될 값이다.
