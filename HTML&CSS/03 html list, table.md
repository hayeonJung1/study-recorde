# list, table

### list

---

`&lt;ol&gt;` : 순서가 있는 목록을 표현할 때 사용한다.

`&lt;ul&gt;` : 순서가 없는 목록을 표현할 때 사용한다.(주로 현업에서 사용)

`&lt;li&gt;` : 목록하위 항목으로 사용되며, &lt;ul&gt; 태그 또는 &lt;ol&gt; 태그 하위에 위치한다.

`&lt;dl&gt;` : Definition List의 약자로, 사전처럼 용어를 설명하는 목록을 만든다.

     ex) A는 B다. 와 같은 Key = Value로 사용할 때 유용하다.

`&lt;dt&gt;` : Definition Term의 약자로, 정의되는 용어의 제목을 넣을 때 사용한다.

`&lt;dd&gt;` : Definition Description의 약자로, 용어를 설명하는 데 사용한다.

❗**주의 사항**

&lt;dl&gt; 태그는 하나 이상의 &lt;dt&gt;, &lt;dd&gt; 쌍의 태그를 갖고 있어야 한다.

(단, &lt;dt&gt; - &lt;dd&gt; 태그가 반드시 하나의 짝으로 지어져야 하는 것을 아니다.

&lt;li&gt;, &lt;dt&gt;, &lt;dd&gt; 태그는 밖에서 독립적으로 사용할 수 없다.

&lt;ul&gt; 태그 하위요소로는 &lt;li&gt; 태그가 위치해야 한다.

### table

---

**기본 구성**

`&lt;table&gt;` : 표

`&lt;tr&gt;` : 행(row, 가로)

`&lt;td&gt;` : 열(col, 세로)

**태그**

`&lt;table&gt;` : 표를 만드는 태그로써, 표 전체를 감싸는 데 사용한다.

`&lt;caption&gt;` : 표 제목

`&lt;tr&gt;` : 표의 행(가로)을 의미하는 태그이다.

`&lt;th&gt;` : 표의 제목 열을 의미하는 태그이다. css 기본값으로 글자가 굵게 처리되고 가운데 정렬된다.

`&lt;td&gt;` : 행의 내용

`&lt;col&gt;` / `&lt;colgroup&gt;` : 스타일 지정을 위한 열(그룹)

`&lt;thead&gt;` : 머리글

`&lt;tfoot&gt;` : 꼬리말

`&lt;tbody&gt;` : 본문

### 속성

| 속성                      | 설명                 |
| ------------------------- | -------------------- |
| scope="col" / scope="row" | 열 또는 행의 제목    |
| colspan="2"               | 2칸 열 병합          |
| rowspan="3"               | 3칸 행 병합          |
| span="3"                  | colgroup의 열의 갯수 |
