# Margin-collapsing (마진상쇄)

## 마진 상쇄란?

흔히 마지 겹침 현상이라고도 불린다.하지만 인과관계로 볼 때 , 마진이 겹치게 되면 상쇄가 일어나기 때문에
영미권에서는 '마진 상쇄(Margin collaspsing)'로 부르고 있다.

이미지에 마진 값을 부여하면 맞닿아있는 면의 마진은 겹치게 된다는 이야기이다.
예를 들어서 왼쪽 이미지 마진 4px값와 오른쪽 이미지 마진 4px의 면이 맞닿아 있다면 8px가 아니라 4px만큼만 마진을 적용한다는 이야기이다.

## 마진 상쇄가 일어나는 3가지 상황

### - 1. 인접 형제 박스 간 상하 마진이 겹칠 때

     겹쳐진 두 마진 값을 비교해, 더 큰 마진 값으로 상쇄해 렌더링 한다.
     만약 겹쳐진 두 값이 동일할 경우, 중복을 상쇄해 렌더링한다.

```JS
<div class="first">first div</div>
<div class="second">second div</div>
```

```CSS
.first {
	width: 200px;
    height: 200px;
    background-color: lightpink;
    margin-bottom: 30px;
}
.second {
	width: 200px;
    height: 200px;
    background-color: lightgray;
    margin-top: 30px;
}
```

![마진상쇄1](https://user-images.githubusercontent.com/91517680/178175039-8dda84de-5cb2-4439-9e10-229d6ec3527b.jpeg)

원래 생각하는 대로라면 first div의 하단에 마진 30px을, second div의 상단에 30px을 적용해서 두개의 div 사이엔 (30px + 30px) 총 60px의 마진이 생겨야 한다.
하지만 마진 상쇄가 이루어지면서 적용된 두 개의 마진 중 하나인 30px이 적용되었다.
(두 개의 마진 크기가 같은 경우는 둘중 하나가 적용되고, 크기가 다른 경우는 둘 중 큰 마진이 적용된다.)

</br>

### - 2. 부모 요소와 첫번째 자식 요소의 마진이 겹칠 때

```JS
<div class="parent">
	<div class="child1"></div>
</div>
```

```CSS
.parent {
	width: 400px;
    height: 400px;
    background-color: lightpink;
    margin-top: 30px;
}
.child1 {
	width: 200px;
  	height: 200px;
    background-color: lightgray;
    margin-top: 60px;
}
```

위와 같은 부모 - 자식 블럭의 html에 마진을 적용했을 때, 1번과 같이 생각하는 대로라면 (30px + 60px)로 총 90px의 상단 마진이 생겨야 한다.

![마진상쇄2](https://user-images.githubusercontent.com/91517680/178175196-aa626168-a811-4791-8c00-f01cbde3944d.jpeg)

하지만 마진 상쇄 현상이 일어나 두개의 마진 중 크기가 큰 마진이 적용되는 것을 볼 수 있다.
+) 상쇄될 때, 자손의 마진의 크기가 더 크던 작던 상관없이 무조건 부모 블럭 밖으로 나오게 된다.

이때 부모-자식 관계의 블럭이기 때문에, 부모-자식 간의 경계는 border, padding, content의 유무로 구분된다.
따라서 부모-(첫번째)자식 사이에 inline content가 없거나, padding, border 값을 주지 않았다면 마진 상쇄 현상이 일어난다.

![마진상쇄 3](https://user-images.githubusercontent.com/91517680/178175246-a7df7673-af72-4d85-b571-20edaf2dee80.jpeg)

부모 블럭의 상단에 2px짜리 border속성을 주었는데, border가 생기자 마진 상쇄가 일어나지 않고 부모 블럭과 자식 블럭의 마진이 분리되어 적용되는 것을 볼 수 있다.

</br>

### - 3. 빈 요소의 상하 마진이 겹칠 때

이때 빈 요소란 높이(height)가 0인 블럭 요소를 말한다.

```HTML
<div class="first">first div</div>
<div class="empty"></div>
<div class="second">second div</div>
```

```CSS
.first {
	width: 300px;
  	height: 300px;
    background-color: lightpink;
   	margin-bottom: 30px;
}
.empty {
	width: 300px;
    margin-top: 60px;
    margin-bottom: 30px;
}
.second {
	width: 300px;
    height: 300px;
    background-color: lightgray;
    margin-top: 40px;
}
```

위와 같은 3개의 블럭이 있다. 이때 두번째 블럭은 content, height이 없다. 즉, 빈 요소이다.
위 3개 블럭에 다음과 같이 마진을 적용시켰을 때 발생하는 마진 상쇄를 보도록 하자.

![마진상쇄 4](https://user-images.githubusercontent.com/91517680/178175508-1311402d-a41d-46b3-b6f0-22471a9d29de.jpeg)

빈 요소의 상단에는 60px의 마진이, 하단에는 30px의 마진이 적용되어 있다.
하지만 first div의 하단에 30px의 마진이 적용되어 있으므로, 빈 요소의 상단 마진과 겹치면서 60px로 마진 상쇄가 일어난다.
이후 60px의 마진은 second div의 상단 마진인 40px과 다시 한 번 겹치게 되면서 60px로 또 다시 상쇄된다.
따라서 다중으로 상쇄가 일어나고, 60px의 마진만 남게 된다.

## 마진 상쇄 규칙

마진 값이 0이더라도 상쇄가 적용된다.
위의 규칙에 따라 부모-자식 관계에서 상쇄가 적용되는 경우 무조건 부모 블럭 밖으로 나오게 된다.
음수 값을 가진 마진을 포함할 경우, 상쇄된 마진의 크기는 제일 큰 양수 마진과 제일 작은(음의 방향으로, 절댓값이 제일 큼) 마진의 합이 된다.
모든 마진이 음수 값을 가질 경우, 상쇄된 마진의 크기는 제일 작은(음의 방향으로, 절댓값이 제일 큼) 마진의 크기가 된다.
좌우 마진은 상쇄가 적용되지 않는다.

### 마진 상쇄 규칙 예외

다음과 같은 상황에서는 인접 요소 간 마진 상쇄가 일어나지 않는다.

박스가 position: absolute 된 상태
박스가 float: left/right 된 상태 (단, clear 되지 않은 상태)
박스가 display: flex 일 때 내부 flexbox item
박스가 display:grid 일 때 내부 grid item
