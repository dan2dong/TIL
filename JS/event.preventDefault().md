#event.preventDefault()

- 브라우저의 기본 behavior을 막는다.

ex) ```<form>```의 기본동작 - submit and refresh.
event.preventDefault()라고 입력하면 브라우저에서 기본 동작인
submit과 새로고침 진행을 하지 않는다.
</br>
</br>
```<a>``` 태그는 href로 지정된 url로 이동을 하는 기능이 있지만
event.preventDefault()를 입력하면 링크를 눌러도 해당 페이지로 이동을 하지 않는다.

```JS
<body>
	<a href="http://www.naver.com" target="_blank">네이버</a>
</body>
```

```JS
const link = document.querySelector('a');

function handleLink (event){
  event.preventDefault();
}

link.addEventListener('click',handleLink)

```

참고로 함수의 parameter에는 꼭 event라고 표기하지 않아도 된다.
