# css 효과

### z-index

🔹 요소의 쌓임 순서(스택 순서)를 지정하는 데 사용

🔹 z-index 속성은 정수 값을 가지며, 음수 값도 허용된다. 값이 높을 수록 요소가 더 위에 표시되며, 동일 값일 경우에는 HTML 구조에서 먼저 선언된 요소가 위에 표신된다.

🔹 position 속성이 static이 아닌 요소에 적용된다. 즉 position: relative;, position: absolute;, position: fixed; 등과 함께 사용된다.

### transition

| 속성 | 설명 |
| --- | --- |
| transition | property, duration, function, delay |
| transition-property | 요소에 추가할 전환 효과를 설정 |
| transition-duration | 전환 효과가 지속될 시간을 설정 |
| transition-timing-function | 전환 효과의 시간 당 속도를 설정 |
| transition-delay | 전환 효과가 나타나기 전까지의 지연 시간을 설정 |

```css
div {
   width: 100px;
   height: 50px;
   background-color: red;
   margin-bottom: 10px;

   transition-property: width, background-color; /* 어떤 css 프로퍼티를 transition할지 지정 */
   transition-duration: 2s, 2s; /* width와 bg-color가 2초동안 변화 */
}

div:hover { /* 마우스를 올리면 transition발동해서 적용될 상태 */
   width: 300px;
   background-color: blue;
}
```

```css
transition-timing-function: ease; /*기본값, 느리게 시작하여 점점 빨라졌다가 느려지면서 종료*/
transition-timing-function: linear;  /*시작부터 종료까지 등속*/
transition-timing-function: ease-in;  /*느리게 시작한 후 일정한 속도에 다다르면 그 상태로 등속*/
transition-timing-function: ease-out;  /*일정한 속도의 등록으로 시작해서 점점 느려지면서 종료*/
transition-timing-function: ease-in-out;  /*느리게 시작하여 느려지면서 종*/
```

### transtorm

🔹 요소에 이동, 회전, 확대/축소, 비틀기 효과를 부여

| 속성 | 설명 | 단위 |
| --- | --- | --- |
| translate(x, y) | 요소의 위치를 X축으로 x만큼, Y축으로 y만큼 이동 | px, %, em등 |
| translateX(n) | 요소의 위치를 X축으로 x만큼 이동 | px, %, em등 |
| translateY(n) | 요소의 위치를 Y축으로 y만큼 이동 | px, %, em등 |
| scale(x, y) | 요소의 크기를 X축으로 x배, Y축으로 y배 확대 또는 축소 시킨다. | 0과 양수 |
| scaleX(n) | 요소의 크기를 X축으로 x배 확대 또는 축소 시킨다. | 0과 양수 |
| scaleY(n) | 요소의 크기를 Y축으로 y배 확대 또는 축소 시킨다. | 0과 양수 |
| skew(x-angle, y-angle) | 요소를 X축으로 x 각도만큼, Y축으로 y각도만큼 기울인다 | +/- 각도(deg) |
| skewX(x-angle) | 요소를 X축으로 x 각도만큼 기울인다 | +/- 각도(deg) |
| skewY(y-angle) | 요소를 Y축으로 y 각도만큼 기울인다 | +/- 각도(deg) |
| rotate(angle) | 요소를 angle만큼 회전시킨다. | +/- 각도(deg) |

### animation

🔹 HTML요소에 애니메이션 효과를 적용시켜준다.

🔹 @keyframes 를 사용해 적용한다.

| 속성 | 설명 | 기본값 |
| --- | --- | --- |
| animation-name | @keyframes 애니메이션 이름을 지정 |  |
| animation-duration | 한 싸이클의 애니메이션에 소요되는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정 | 0s |
| animation-timing-function | 애니메이션 효과를 위한 타이밍 함수를 지정 | ease |
| animation-delay | 요소가 로드된 시점과 애니메이션이 실제로 시작하는 사이에 대기하는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정 | 0s |
| animation-iteration-count | 애니메이션 재생 횟수를 지정 | normal |
| animation-fill-mode | 애니메이션 미실행 시 요소의 스타일을 지정 |  |
| animation-play-state | 애니메이션 재생 상태를 지정 | running |
| animation | 모든 애니메이션을 한번에 지정 |  |

```css
@keyframes move { /* @keyframes 뒤에 애니메이션을 대표하는 임의의 이름 move를 부여 */
   from { /* 애니메이션 시작 시점 */
       left: 0;
   }
   to { /* 애니메이션 종료 시점 */
       left: 300px;
   }
}
/*
from, to 키워드 대신 상세한 조작
@keyframes move {
  0%   { left: 0; }
  50%  { left: 100px; }
  100% { left: 300px; }
}
*/

div {
      position: absolute;
      width: 100px;
      height: 100px;
      background-color: red;
      
      animation-name: move; /* @keyframes에 지정한 이름 */
      animation-duration: 5s; /* 애니메이션 동작 시간 */
      animation-iteration-count: infinite; /* 애니메이션 재생 횟수 무한 */
}
```