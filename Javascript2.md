## JS DOM

### 문서 객체 모델(DOM, Document Object Model)

DOM은 XML이나 HTML 문서에 접근하기 위한 일종의 인터페이스로, 문서 내의 모든 요소를 정의하고, 각각의 요소에 접근하는 방법을 제공한다.(HTML 요소를 JS로 접근할 수 있다.

<img width="395" alt="스크린샷 2024-05-03 151003" src="https://github.com/dawoon1229/CSS_practice/assets/164113758/b0fa3b14-5566-470b-8d93-5f7420076c51">


---

### Document 객체

Document 객체는 웹 페이지 그 자체를 의미한다.

웹 페이지에 존재하는 HTML 요소에 접근하고자 할 때는 반드시 Document 객체부터 시작한다. 아래 표는 요소를 선택하기 위한 document 메소드.

<img width="611" alt="스크린샷 2024-05-03 151121" src="https://github.com/dawoon1229/CSS_practice/assets/164113758/6d41f611-3d9a-4b79-a778-cfc058cf5a96">


HTML 요소의 생성 (자바스크립트로 요소를 동적으로 만들어줄 수 있다.)

<img width="632" alt="스크린샷 2024-05-03 151226" src="https://github.com/dawoon1229/CSS_practice/assets/164113758/5f55ba76-4d46-4e80-999e-47b397f2051c">


HTML 이벤트 핸들러 추가 (onclick, onXXX 와 같은 이벤트도 동적으로 설정)

<img width="635" alt="스크린샷 2024-05-03 151305" src="https://github.com/dawoon1229/CSS_practice/assets/164113758/36ac79e2-aeb8-4083-9687-6d6c4ceb461e">


---

### DOM 요소의 선택

HTML 요소를 다루기 위해서는 우선 해당 요소를 선택해야 한다.

1. HTML 태그 이름(tag name)을 이용한 선택
2. 아이디(id)를 이용한 선택
3. 클래스(class)를 이용한 선택
4. name 속성(attribute)을 이용한 선택
5. CSS 선택자(selector)를 이용한 선택
6. HTML 객체 집합(object collection)을 이용한 선택(eg: document.anchors)

---

### DOM 요소의 내용 변경

HTML DOM을 이용하면 HTML 요소의 내용(content)이나 속성값 등을 손쉽게 변경할 수 있다. HTML 요소의 내용을 변경하는 가장 쉬운 방법은 innerHTML 프로퍼티를 이용하는 것이다.

```html
var str document.get ElementById("text");
str.innerHTML="이 문장으로 바뀌었습니다!"; //요소의 내용을 변경

var link=document.getElementById("link"); //아이디가 "link"인 요소를 선택
link.href="/javascript/intro"; //해당 요소의 href 속성값을 변경
link.innerHTML="자바스크립트 수업 바로 가기!"; //해당 요소의 내용을 변경
```

---

### DOM 요소의 스타일 변경

HTML DOM을 이용하면 HTML 요소의 스타일(style)도 변경할 수 있다.

style 프로퍼티를 이용하여 HTML 요소에 CSS 스타일을 적용.

```html
var str=document.getElementById("text"); //아이디가 "str"인 요소를 선택함

//글자색 변경 함수
function changeRedColor(){str.style.color="red";} //글자색을 빨간색으로 변경
function changeBlackColor(){str.style.color="black";} //글자색을 검정색으로 변경
```

---

### 노드의 추가

다음 메소드를 사용하면 특정 위치에 새로운 노드(요소)를 추가할 수 있다.

1. appendChild()
2. insertBefore()
3. insertData()

```html
var parent=document.getElementById("list"); //id가 "list"인 요소를 선택
var newItem=document.getElementById("item"); //id가 "item"인 요소를 선택
parent.appendChild(newItem); //list 요소의 맨 마지막 자식 노드로 추가
parent.insertBefore(newItem, parent); //기준이 되는 자식 노드의 바로 앞에 추가함
parent.insertData(3, "나른한"); //텍스트 노드의 3번째 문자부터 "나른한" 텍스트 추가
```

---

### 노드의 생성

createElement() 메소드를 사용하여 요소 노드를 생성할 수 있다.

```html
function createNode() {
	var criteriaNode = document.getElementById("text"); //기준 노드
	var newNode = document.createElement("p"); //새로운 <p> 요소를 생서함
	newNode.innerHTML = "새로운 단락입니다.";
	
	//기준 노드 바로 앞에 새 요소 추가
	document.body.insertBefore(newNode, criteriaNode);
}
```

---

### 노드의 제거

removeChild() 메소드는 자식 노드 리스트에서 특정 자식 노드를 제거한다.

이 메소드는 성공적으로 노드가 제거되면 제거된 노드를 반환하며, 노드가 제거될 때에는 제거되는 노드의 모든 자식 노드들도 다 같이 제거된다.

```html
var parent = document.getElementById("list"); //id가 "list"인 요소를 선택
var removedItem = document.getElementById("item"); //id가 "item"인 요소를 선택
parent.removeChild(removedItem); //지정된 요소를 삭제
```

---

### HTML과 JavaScript를 사용항여 간단한 댓글 시스템을 만드는 예제

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS 간단 댓글</title>
</head>
<body>
    <div>
        <input type="text" name="" id="input" placeholder="댓글을 입력해보세요">
        <!-- 버튼의 onclick 이벤트에 writeComment 함수를 호출하는 부분을 추가 -->
        <button onclick="writeComment()">등록</button>
    </div>
    <div>
        <ul id="comments">
            <!-- 댓글 리스트는 초기에 비어있음 -->
        </ul>
    </div>
    <script>
        var comments = ['짬뽕', '국밥', '수육'];

        function writeComment() {
            // DOM
            const comment = document.getElementById('input').value;
            comments.push(comment);
            drawList();
        }

        function drawList() {
            let html = '';

            for (var i=0; i<comments.length; i++) {
                // 템플릿 리터럴을 올바르게 처리
                html += `<li>
                    ${comments[i]} 
                    <button onclick="modifyComment(${i})">E</button> 
                    <button onclick="deleteComment(${i})">X</button>
                </li>`;
            }

            const cmtListEl = document.getElementById('comments');
            cmtListEl.innerHTML = html;
        }

        function modifyComment(idx) {
            // prompt를 사용해 사용자로부터 댓글을 받음
            var text = prompt('수정할 내용', comments[idx]);
            if (!text) {
                return;
            }

            comments[idx] = text;
            drawList();
        }

        function deleteComment(idx) {
            if (!confirm('지울까요?')) {
                 return;
            }

            comments.splice(idx, 1);
            drawList();
        }

        // 초기에 리스트를 그리도록 수정
        drawList();
    </script>
</body>
</html>
```

<img width="191" alt="스크린샷 2024-05-03 172629" src="https://github.com/dawoon1229/CSS_practice/assets/164113758/6ffbb820-42a2-46e0-aac6-5cee6fd72318">


---

### 간단한 뮤직 플레이어를 만드는 예제

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>뮤직 플레이어</title>
    <style>
        @import url('https://fonts.googleapis.com/earlyaccess/notosanskr.css');

        #playerBox {
            width: 700px;
            height: 200px;
            border: 1px solid gray;
            display: flex;
            justify-content: space-around;
            align-items: center;
            box-shadow: 2px 2px 15px lightslategray;
        }
        #albumart {
            box-shadow: 2px 2px 15px lightslategray;
        }
        #albumart img {
            width: 150px;
        }
        #info {
            width: 450px;
            height: 180px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        #title {
            font-family: 'Noto Sans KR';
            font-size: 2em;
            font-weight: bold;
        }
        #lrc {
            font-family: 'Noto Sans KR';
            font-size: 1.3em;
            margin: 10px 0px;
        }
        #player {
            width: 100%;
        }
    </style>
</head>
<body>
    <div id="playerBox">
        <div id="albumart">
            <img src="https://search.pstatic.net/common?type=n&size=174x174&quality=95&direct=true&src=https%3A%2F%2Fmusicmeta-phinf.pstatic.net%2Falbum%2F006%2F197%2F6197877.jpg%3Ftype%3Dr204Fll%26v%3D20210913233037" alt="">
        </div>
        <div id="info">
            <div id="title">제목</div>
            <div id="lrc">가사</div>
            <audio id="player" src="music.m4a" controls></audio>
        </div>
    </div>
    <script>
        const title = '과제곡 (교수님 죄송합니다)';
        const lrcData = ['(교수님 죄송합니다',
            '죄송합니다 교수님 죄송합니다)',
            '예 교수님 과제는 5개군요 (네?)',
            '아뇨 불만 없어요 다 해올게요 (네)',
            '심지어 창작 과제가 2개라구요? (아)',
            '잠을 줄여서라도 해야죠 암요 (암요)',
            '어 궁금하진 않지만',
            '질문은 없냐 시기에 여쭤보자면',
            '학생들에게 다',];

        const lrcTimeData = [
            14,
            22.715233,
            34.735892,
            41.063261,
            49.608472,
            57.348211,
            64.789686,
            68.749263,
            73.95813
        ]

        document.getElementById('title').innerText = title;
        const player = document.getElementById('player');
        const lrc = document.getElementById('lrc');

        player.ontimeupdate = function(time) {
            var time = player.currentTime;
            var idx = 0;

            for (var i=0; i<lrcData.length; i++) {
                if (lrcTimeData[i] > time) {
                    idx = i == 0 ? 0 : i-1;
                    break;
                }
            }

            console.log(idx, lrcData[idx]);
            lrc.innerText = lrcData[idx];

        }
    </script>
</body>
</html>
```

<img width="550" alt="스크린샷 2024-05-03 172819" src="https://github.com/dawoon1229/CSS_practice/assets/164113758/8dda95d9-9690-4e12-8664-df915063fafb">



---
