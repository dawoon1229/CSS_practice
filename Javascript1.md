## 자바스크립트(JavaScript)

### 특징

1. 자바스크립트는 객체 기반의 스크립트 언어이다.
2. 자바스크립트는 동적이며, 타입을 명시할 필요가 없는 인터프리터 언어.
3. 자바스크립트는 객체 지향형 프로그래밍과 함수형 프로그래밍을 모두 표현할 수 있다.
4. 자바(Java)언어와는 관련이 없다.

---

### 자바스크립트로 할 수 있는 것

1. HTML의 ‘내용’을 동적으로 변경할 수 있다.
2. HTML의 ‘속성’을 변경할 수 있다.
3. HTML의 스타일을 변경할 수 있다.
4. 브라우저 제어(팝업, 쿠키, 인쇄, 전체화면 등)

---

### 기본 문법

- 자바스크립트의 실행문은 세미콜론(;)으로 구분한다.
- 대소문자를 구분하며, 변수나 함수의 이름, 예약어 등을 작성하거나 사용할 때에는 대소문자를 정확히 구분해서 사용해야 한다.

```jsx
var javascript = 10; // 변수 javascript와 JavaScript는 서로 다른 두 개의 변수로 인식됨.
var JavaScript = 20;
Var Script = 30; // 변수의 선언은 var 키워드로만 할 수 있으면 Var는 동작하지 않음.
```

---

### 식별자(identifier)

- 식별자는 변수나 함수의 이름을 작성할 때 사용하는 이름.
- 영문자(대소문자), 숫자, 언더스코어(_) 또는 달러($)만을 사용할 수 있다.
- Camel Case 방식 또는 Underscore Case 방식으로 이름을 지을 수 있다.
- 자바스크립트에서는 주로 Camel Case 컨벤션을 사용.
    
    firstCoding vs first_coding
    

---

### 키워드(keyword)

- 자바스크립트에서는 몇몇 단어들을 특별한 용도로 사용하기 위해 미리 예약되어 있다.
- 미리 예약된 단어들을 키워드(keyword) 또는 예약어(reserved word)라고 하며, 프로그램 내에서 식별자로 사용할 수 없다. (오류 발생)

```jsx
var firstVar = 10; //var는 변수의 정의를 위해 예약된 키워드.
function myFirstFunc { //function은 함수의 정의를 위해 예약된 키워드.
	var seconVar = 20; //var는 변수의 정의를 위해 예약된 키워드.
}
```

---

### 입출력 방법

- 자바스크립트에서 사용자가 입력한 값을 받기 위해 다음과 같은 방법들이 있다.
    - window.prompt() 함수
    - input 태그의 value속성 읽기
    - 개발자 도구 console

```jsx
<script>
	var a = prompt("a변수에 입력할 값을 넣어주세요. ");
</script>
```

---

### 자바스크립트 코드의 실행 결과를 출력해보는 방법

- window.alert() 메소드(함수)
- HTML DOM 요소를 이용한 innerHTML 프로퍼티
- document.write() 메소드
- console.log() 메소드

---

### 웹 페이지에 적용하는 방법

- HTML 문서에 자바스크립트 코드를 적용하는 방법
    - 내부 자바스크립트 코드로 적용
    - 외부 자바스크립트 파일로 적용

```jsx
<head>
	<meta charset="UTF-8">
	<title>JavaScript Apply</title>
	<script src="/examples/media/example.js"></script><!--외부 스크립트-->
	<script>
		document.getElementById("text").innerHTML="여러분을 환영합니다!";
	</script>
</head>
```

---

### JS 제어문

반복문(iteration statements)

반복문이란 프로그램 내에서 똑같은 명령을 일정 횟수만큼 반복하여 수해하도록 제어하는 실행문이다. 프로그램이 처리하는 대부분의 코드는 반복적인 형태가 많으므로, 가장 많이 사용되는 실행문 중 하나이다.

1. while 문
2. do / while 문
3. for 문
4. for / in 문
---

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        h1{
            color: blue;
        }
    </style>
</head>
<body>
    <h1 onclick="changeText()" id="title">안녕 제목이야</h1>
    <button onclick="changeText()">눌러보세요</button>

    <button onclick="print()">인쇄</button>

    <button onclick="openNewTab()">새 창</button>
    <button onclick="closeTab()">새창닫기</button>

    <button onclick="fullscreen()">전체화면 보기</button>

    <img id="img" width="500" src="https://ssl.pstatic.net/melona/libs/1491/1491834/fdf4c7bd85960551ae4c_20230731151310224_5.jpg" alt="">

    <script>
        let tab = null;

        function fullscreen() {
            document.body.requestFullscreen();
        }

        function openNewTab() {
            tab = window.open('https://www.naver.com');
        }

        function closeTab() {
            tab.close();
        }

        function changeText() {
            // html요소의 내용 변경
            document.getElementById('title').innerText='제목을 바꿔보자';

            // html 요소의 속성 변경
            document.getElementById('img').src='https://ssl.pstatic.net/melona/libs/1491/1491834/7c98fa6c6137f0778439_20240422135426022_1.jpg';
            document.getElementById('img').width='1000';

            // html 요소의 스타일 변경
            document.getElementById('title').style.color = 'red';
        }
        
    </script>
</body>
</html>
```
<img width="713" alt="스크린샷 2024-04-26 164214" src="https://github.com/dawoon1229/CSS_practice/assets/164113758/7c3c741c-86b6-418c-918c-ccb4d9335bd5">

<img width="808" alt="스크린샷 2024-04-26 164236" src="https://github.com/dawoon1229/CSS_practice/assets/164113758/150321d4-27a1-4278-accd-07492caffb3b">

---
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        h1{
            color: blue;
        }
    </style>
</head>
<body>
    <h1 onclick="changeText()" id="title">안녕 제목이야</h1>
    
    <input id="input" type="text">
    <button onclick="getInputText()">input값 읽기</button>
    <button onclick="getPrompt()">prompt 읽기</button>
    <button onclick="alert(text)">text 변수</button>
    <button onclick="checkLen()">제출</button>

    <script>

        var text = '어떤 값'

        function checkLen() {
            var text = document.getElementById('input').value;
            if (text.length < 5) {
                alert('5글자 이상으로 작성하세요.');
                return false
            }
            return true;
        }

        function getInputText() {
            var text = document.getElementById('input').value;
            alert(text);
        }
        function getPrompt() {
            var text = window.prompt('아무거나 써보세요');
            alert(text);
        }
    </script>
</body>
</html>
```

<img width="392" alt="스크린샷 2024-04-26 164334" src="https://github.com/dawoon1229/CSS_practice/assets/164113758/db613175-e0ba-418f-b1fb-298eadceaf97">

<img width="644" alt="스크린샷 2024-04-26 164359" src="https://github.com/dawoon1229/CSS_practice/assets/164113758/94127b45-4f9e-4d5a-b6a2-65a7b9045e5e">

---


