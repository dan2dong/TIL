innerHTML과 innerText는 속성은 텍스트를 읽어오고 설정할 수 있다는 점에서 비슷해보이지만,조금씩 다른 차이가 있다.

<br>
innerHTML- innerHTML은 'Element'의 속성으로, element내에 포함 된 HTML 또는 XML 마크업을 가져오거나 태그와 함께 입력하여 내용을 
직접 설정 가능.

innerHTML을 사용하면 내부 HTML 코드를 JavaScript 코드에서 새 내용으로 쉽게 변경 가능.
단점은 보안에 취약하고 파싱이 느리다.

//사용 예시
h1.innerHTML = "<a href='https://daum.net'>daum</a>"
<br>

innerText- innerText는 'Element'의 속성으로, element내에서 사용자에게 보여지는 text값들을 가져오거나 설정할 수 있다.

//사용 예시
h1.innerText = "Text"
