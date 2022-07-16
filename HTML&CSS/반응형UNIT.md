# 반응형UNIT

### rem = relative to root element

### em = relative to parent element

rem은 root의 font-size에 대한 상대적인 크기이다. rem은 최상위 element인 html의 사이즈를 기준으로 삼는다.</br>
기본적으로 html의 default font-size는 16px이다.따라서 변경하지 않았을 시에는 1rem : 16px이 된다.
</br></br>
em은 rem이 root의 font-size에 대한 상대적인 크기였다면,em은 부모 element의 font-size에 대한 상대적인 크기이다.
</br>
예를 들어 부모 요소의 font-size가 10px이라고 가정 했을 때, 2em = 20px가 된다.
</br>
em 같은 경우, 부모의 사이즈를 기준으로 하기 때문에 중첩된 자식 element에 계속 쓰이면 한눈에 파악하기 어려울 수 있다.
</br>

--- 

### %(퍼센트)

% 또한 상대적인 단위로 부모의 사이즈에 대한 퍼센트로 계산된다. </br>
예를 들어, 부모의 width가 300px일때, </br>
child의 height 속성을 50%로 주면 최종적으로 150px로 계산된다.
</br>
em과 마찬가지로 % 역시 부모의 크기에 영향을 받는 단위이다.
</br></br>
font-size : 100%는,</br>
font-size : 1em과 동일하다.
</br>

---

### vh = viewport height

### vw = viewport width

</br>
1vw = 뷰포트 너비의 1%'로 계산됩니다.
그렇다면 500px 너비인 뷰포트에서 1vw의 값은 5px이 되는 것이다.
</br></br>

즉, 현재 실행중인 스크린 크기에 맞춰 상대적 크기를 반환하겠다는 뜻이다.</br></br>
ex) 현재 스크린크기가 height = 1000px, width = 800px이라면, </br>
1vh= 10px / 1vw =8px</br>
height: 50vh, width:25vw로 설정한다면 height = 500px ,width = 200px이 적용된다.

---

1vw : viewport 너비의 1/100
</br>
1vh : viewport 높이의 1/100
</br>
vmin : viewport 너비 또는 높이 중 작은 쪽의 1/100
</br>
vmax : viewport 너비 또는 높이 중 큰 쪽의 1/100
</br>
</br>
부모 vs browser

- 부모요소에 대해서 반응해야 되는 경우 : %, em 사용
- browser에 대해 반응해야 되는 경우 : v\*, rem 사용
  </br>
  %와 em은 부모의 크기에 상대적인 영향을 받는 단위이다. </br></br>
  표현하려고 하는 요소가 부모의 크기에 따라 변하길 원하고,</br>
  예를 들어 부모의 크기에 따라 크기를 상대적으로 정하고 싶은 button component라면 </br>
  % 혹은 em을 사용하는 것이 좋을 것 같다.
