# DOM

- DOM이란 웹페이지의 HTML을 계층화 시켜 트리구조로 만든 object 모델이다.

문서 객체란

- HTML 태그들, 즉 element 요소들을 JS가 이용할 수 있는 객로 만들면 그것을 문서 객체라고 부른다.

JS는 이 model로 웹 페이지에 접근하고, 페이지를 수정한다.
DOM은 HTML인 웹페이지와 스크립팅언어(JS)를 서로 이어주는 역할을 한다.

문서의 모든 요소를 정의하고 각각의 요소에 접근하는 방법을 제공한다.

### DOM을 통해 접근하는 이유

- API를 통해 서버에서 필요한 데이터를 가져와 웹페이지에 접목할 수 있다.
- Event를 추가하여 동적인 웹페이지를 구현할 수 있다.

### DOM에 접근하는 방법

1.  id 선택자로 접근하는 getElementByld() 메서드
2.  class값으로 접근하는 getElementsByClassName() 메서드
3.  태그 이름으로 접근하는 getElementsByTagName() 메서드
4.  다양한 방법으로 접근하는 querySelector(), querySelectorAll() 메서드

    - DOM트리의 텍스트, 속성 노드까지 자유롭게 제어 가능하다.

5.  웹 요소의 내용을 수정하는 innerText, innerHTML 프로퍼티
6.  속성을 가져오거나 수정하는 getAttribute(), setAttribute() 메서드
