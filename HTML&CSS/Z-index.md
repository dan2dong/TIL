# Z-index

## z-index 속성

- 어느 요소를 앞에 배치할지 뒤에 배치할지 결정하는 속성</br>
- position 속성이 relative, absolute, fixed 값을 갖는 요소에 대해서만 적용
  </br>
  </br>

  ```CSS
  z-index: auto | <숫자값>
  ```

  </br>

### auto

자동지정</br>
<숫자값> : 값이 작을 수록 (음수 포함) 뒤에 배치하고 높을 수록(양수 포함) 앞에 배치

![다운로드 (7)](https://user-images.githubusercontent.com/91517680/180652280-e09b13a4-1ed5-41a0-9069-7861c6bc6881.png)
</br>

### Stacking Order

HTML의 모든 요소는 다른 요소의 앞으로 나오거나 뒤로 들어갈 수 있다는 개념
</br>
순서를 결정하는 규칙
</br>

- HTML에 작성된 순서
- position 속성이 사용된 요소는 position 속성을 사용하지 않는 요소(static) 앞에 나타남
- z-index 속성에 지정된 순서
  </br>
  </br>

### Stacking Contexts

- 같은 부모 밑에 있어서 Stacking Order에 따라 함께 앞뒤로 움직일 수 있는 요소들의 그룹이 생성하는 쌓임 규칙
- 어떤 요소에서 Stacking Contexts가 생성될 때 자식 요소들이 StackingContexts에서 특정 범위를 벗어나지 못하도록 한계를 결정
- 이 경우 자식 요소들은 z-index 속성이 적용되지 않음
  </br>
  생성 규칙

- 요소가 문서의 최상위 요소 (html 요소)
- 요소의 position 값이 static이 아니면서 z-index도 auto가 아닐때
- 요소의 opacity 값이 1보다 작을 때
  </br>
  </br>
  ### 같은 단계의 Stacking Contents의 Stacking Order </br>
- 루트 요소(html) </br>
- position 값이 있고 z-index 값이 음수인 요소(와 자식들) </br>
- position 값이 없는 요소 (HTML 순서에 따라서) </br>
- position 값이 있고 z-index 값이 auto인 요소(와 자식들) </br>
- position 값이 있고 z-index 값이 양수인 요소(와 자식들)
