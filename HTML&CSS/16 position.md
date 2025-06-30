# position

| 속성 | 설명 |
| --- | --- |
| static(정적) | html문서 상에서 원래 있어야하는 위치에 배치 |
| relative(상대적) | 요소를 원래 위치를 기준으로 상대적으로 배치 |
| absolute(절대적) | 요소를 부모 요소를 기준으로 배치 |
| fixed(고정) | 브라우저화면을 기준으로 요소를 항상 고정된 위치에 배치 |

### position: static (디폴트)

🔹 HTML에 작성된 순서 그대로 브라우저 화면에 표시된다.

🔹 top, right, bottom, left, z-index의 속성에 영향을 받지 않음

### position: relative

🔹 static이었을 때의 위치를 기준으로 상대적으로 이동시켜 배치시킨다.

🔹 top, bottom, left, right 속성을 이용해서 지정할 수 있다.

### position: absolute

🔹 가장 가까운 부모에 대해 상대적으로 위치 지정

🔹 부모 중에 static이 아닌 요소가 없다면 최상위 태그 body에 기준으로 배치된다.

🔹 보통 absolute를 사용할 때는 부모 요소를 relative로 지정한다.

🔹 position: absolute인 요소는 HTML 문서 상에서 독립되어 앞뒤에 나온 요소와 상호작용을 하지 않게 된다.

### position: fixed

🔹 스크롤을 하더라도 요소를 항상 고정된 위치에 배치한다.

🔹 top, bottom, left, right 속성을 이용해서 지정할 수 있다.

🔹 배치 기준이 브라우저 전체 화면(뷰포트)이다.

🔹 position:absolute와 마찬가지로 **HTML 문서 상에서 독립되어** 앞뒤에 나온 요소와 상호작용을 하지 않게 된다.

### position: sticky

🔹 스크롤이 특정 위치에 왔을 때 요소를 지나치지 않고 고정해주는 역할

🔹 top, bottom, left, right 속성을 이용해서 지정할 수 있다.

🔹 static하게 문서에 위치해 있다가 스크롤에 따라 fixed처럼 동작하게 함

🔹 부모 요소에 높이 속성이 지정되어 있어야 한다.

🔹 상단에 공간을 두고 위치에 있던 네이게이션 바가 스크롤 시에 상단에 붙게 되는 경우 주로 사용

🔹 보통 nav에 sticky속성을 주는데, 직속부모 높이 속성에 영향을 받기에 nav는 body태그 아래에 위치