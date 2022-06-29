# toggle

클릭시 글자색이 2개로 바뀌기

</br>

```JS
const h1 = document.querySelector(".hello h1");

function handleTitleClick(){
    const currentColor = h1.style.color;
    let newColor;
    if(currentColor ==="blue") {
        newColor = "tomato";
    } else {
        newColor = "blue";
    }
    h1.style.color = newColor; //맘에 안드는 코드 css 코드이기 때문
}

h1.addEventListener("click", handleTitleClick)
```

</br>

- 더 나은 코드로 바꾸기

```JS
const h1 = document.querySelector(".hello h1");


function handleTitleClick(){
    const clickedClass = "clicked"; //string을 변수에 저장하면 오류가 떠도 에러를 잡아준다.
    if (h1.className === clickedClass) {
      h1.className = "";
    } else {
      h1.className = clickedClass;
    }
}


// title에 click 이벤트가 발생하면 handleTitleClick 함수가 동작되길 원한다.
h1.addEventListener("click", handleTitleClick);


```

```JS
//스타일을 css에만 넣어주어서 더 깔끔한 코드가 되었다.

body {
    background-color: rgb(255, 233, 199);
}

h1 {
    color : cornflowerblue;
    transition: color .5s ease-in-out;
}

.clicked {
    color: tomato;
}
```

</br>

 - toggle

지금 현 상황: 폰트를 추가한 h1에 폰트를 유지한 채 click이벤트도 진행될 수 있도록 만들기.

</br>
classList란 우리가 class들의 목록으로 작업할 수 있게 해주는데
className은 이전 class를 상관하지 않고 모든걸 교체해 버린다.

classList는 HTML element의 class내용물을 조작하는 것을 허용한다.

contains은 우리가 명시한 class가 HTML element의 class에 포함되어 있는지 말해준다.
</br>
</br>
- toggle 함수는

toggle 함수는 토큰이 존재하면 토큰제거
토큰존재 하지 않으면 토큰을 추가한다.

스마트폰 오른쪽 버튼과 같다 생각하면 된다.(화면 켜기 끄기 기능)

ex)
toggle은 h1의 classList에 clicked가 이미 있는지 확인하여
만약있다면 toggle 이 clicked를 제거해준다
만약 class name이 존재하지 않는다면 toggle은 class name을 추가한다.
</br>

```JS
//remove와 add를 사용하여 변경 가능

const clickedClass = "clicked";
if(h1.classList.contains(clickedClass)){
    h1.classList.remove(clickedClass);
} else {
    h1.classList.add(clickedClass);
}
```

위의 코드와 아래의 토글코드 하나가 같다.
</br>

```JS
function handTitleClick() {
h1.classList.toggle("clicked")
}
```
