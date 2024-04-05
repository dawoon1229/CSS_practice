## 박스 모델(box model)

---

브라우저 화면은 가로와 세로를 축으로 하는 2차원 공간이다. 따라서 브라우저를 통해 랜더링 되는 웹 요소들 또한 그 안에서 개별적으로 너비와 높이를 가진다. 박스 모델은 너비와 높이를 가지는 개별 요소를 가리켜 ‘박스’라 표현하고, 박스를 네 가지 세부영역으로 나누어 구분한 일종의 디자인 모델이다. CSS로 스타일을 정의할 수 있는 모든 요소에는 박스 모델 관련 속성 중 일부 또는 전부를 적용할 수 있으며, CSS는 영역 별로 크기를 따로 설정할 수 있도록 다양한 속성들을 제공한다.

- 콘텐츠 영역: 요소 내에 포함된 콘텐츠를 표시하는 영역으로, 관련 속성은 width과 height이다.
- 안쪽 여백: 콘텐츠 주변을 감싸는 여백으로, 관련 속성은 padding이다.
- 경계선(테두리): 콘텐츠와 안쪽 여백을 둘러싸는 경계선으로, 관련 속성은 border이다.
- 바깥쪽 여백: 경계선 바깥을 감싸는 여백으로, 관련 속성은 margin이다.

## 콘텐츠 영역의 크기를 결정하는 width와 height

---

박스 모델 중 가장 안쪽에 위치한 콘텐츠 영역은 가로축에 해당하는 너비와 세로축에 해당하는 높이를 각각 조절하여 콘텐츠의 크기를 결정할 수 있는 영역이다. 너비를 결정할 때는 width 속성을, 높이를 결정할 때는 height 속성을 사용한다. 두 속성은 모두 크기를 결정하기 위해 사용하는 속성이므로, 속성값을 결정할 때는 수치와 단위를 함께 입력해주어야 한다. 아래는 width나 height의 값을 정할 때 사용하는 대표적인 단위이다.

- px: 화면을 구성하는 단위인 화소(pixel)를 뜻하는 절대 단위이다.
- %: 부모 요소의 너비 또는 높이를 백분율로 계산해 적용하는 사대 단위이다.

절대 단위란 기기마다 정해져 있는 크기의 고정 값을 말하는 것으로, 1px(픽셀)은 화소 하나 만큼의 크기를 의미한다. 절대 단위를 이용하면 요소의 크기는 고정되어 변하지 않는다. 반면 상대 단위는 부모 요소(상위 요소)의 너비나 높이를 기준으로 계산되는 크기를 말하는 것으로 부모 요소의 영역 크기가 변경되면 함께 변경된다는 특징이 있다.

## 경계선 스타일 지정하기

---

박스 모델의 구성 요소 중 하나인 경계선(테두리)은 화면 상에서 요소가 차지하고 있는 공간을 뚜렷하게 표시하고, 다른 요소와의 구분을 명확하게 할 수 있도록 하는 유용한 영역이다. 경계선은 박스 전체를 감싸는 형태로 표시되는데, 여기에 스타일을 추가할때는 단축 속성인 border를 지정하거나 border의 다양한 하위 속성을 개별적으로 지정하는 방법을 사용한다.

- border-width: 경계선의 두께를 지정한다.
- border-style: 경계선의 모양을 지정한다. 점선, 실선, 겹선 등 다양한 모양을 선택할 수 있다.
- border-color: 경계선의 색상을 지정한다.
- border: 단축 속성이다. 경계선의 두께, 모양, 색상을 한꺼번에 지정할 수 있다.

## 박스 모델의 배경

---

박스 모델에 배경을 추가할 때는 단축 속성 background를 이용해 배경 색상, 이미지, 위치나 크기 등 다양한 사항들을 정의할 수 있다. 또한 backgroun의 여러 가지 하위 속성들을 개별적으로 정의할 수도 있다.

- background-color: 요소의 배경 색상을 지정한다.
- background-clip: 배경 색상의 요소 내 적용 범위를 지정한다.
- background-image: 요소의 배경 이미지를 지정한다.
- background-origin: 배경 잉미지의 요소 내 적용 범위를 지정한다.
- background-size: 배경 이미지의 크기(너비와 높이)를 지정한다.
- background-position: 배경 이미지의 위치를 지정한다.
- background-repeat: 배경 이미지의 반복 여부 및 방식을 지정한다.
```Html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .org {
            color: orange;
        }

        #sTitle {
            color: red;
        }

        #title {
            border-bottom: 3px solid purple;
            padding: 20px;
            margin: 50px;
            text-align: center;
        }
        #content *{
            box-sizing: border-box;
        }
        #content>div{
            margin: auto;
            width: 400px;
            margin-bottom: 20px;
        }
        #content {
            width: 500px;
            height: 450px;
            border: 5px groove gray;
            border-radius: 30px;
            margin: auto;
            margin-top: 50vh;
            transform: translateY(-300px);
        }
        #content input{
            width: 100%;
            font-size: 16pt;
        }
        .login-btn{
            width: 100%;
            height: 50px;
            font-size: 20pt;
        }
    </style>
</head>

<body>
    <div id="content">
        <h1 id="title" class="org">로그인</h1>
        <div>
            <input type="text" placeholder="ID">
        </div>
        <div>
            <input type="password" placeholder="PW">
        </div>
        <div>
            <button class="login-btn">Login</button>
        </div>
    </div>
</body>

</html>
```

### background-color 와 background-clip

background-color를 이용해 배경색을 지정하면, 해당 색상은 기본적으로 콘텐츠 영역과 안쪽 여백, 그리고 경계선까지 색상을 표시하게 된다. 만일 배경색의 적용 범위를 변경하고자 한다면 사용자는 background-clip 속성의 네 가지 속성 중 하나를 선택해 색상이 표시되는 영역을 지정할 수 있다.

- border-box: 기본 값으로, 배경색이 박스 모델의 경계선까지 표시된다.
- padding-box: 배경색이 박스 모델의 안쪽 여백까지 표시된다.
- content-box: 배경색이 박스 모델의 콘텐츠 영역에만 표시된다.
- text: 배경색이 텍스트 위에만 표시된다.

### background-image 와 background-repeat

background-image 속성을 이용하면 박스 모델 영역의 배경으로 이미지를 표시할 수 있다. 이때 배경으로 사용할 이미지를 지정하기 위해서는 <img>태그의 src속성에 이미지를 지정할 때와 마찬가지로 이미지의 URL을 입력해야 한다. background-image 속성에 이미지의 URL을 입력하기 위해서는 CSS의 url() 함수를 사용한다.

- repeat: 기본 값이다. 배경 영역을 채울 때까지 이미지를 반복한다. 마지막 반복 이미지가 영역을 벗어날 시 잘라낸다.
- repeat-x: 배경 영역의 너비를 모두 채울 때까지 이미지를 반복한다. 반복은 가로 방향으로만 진행된다.
- repeat-y: 배경 영역의 높이를 모두 채울 때까지 이미지를 반복한다. 반복은 세로 방향으로만 진행된다.
- no-repeat: 이미지가 반복되지 않고 한 번만 표시된다.
- space: 이미지가 잘리지 않는 선에서 최대 개수를 반복한다. 이미지는 양끝 정렬되고 이미지와 이미지 사이에 자동으로 여백이 추가된다.

### background-origin

background-image를 이용해 배경 이미지를 추가하면 이미지는 경계선 안쪽 영역을 채우는 방식으로 표시된다. 그러나 이는 고정된 특성이 아닌 기본 특성일 뿐이며, 원한다면 변경할 수 있는 특성이다. background-origin 속성을 정의하면 배경 이미지가 채워지는 방식을 지정할 수 있는데, 이때는 세 가지 방식 중 한 가지를 선택할 수 있다.

- border-box: 배경 이미지가 경계선에서부터 채워지는 방식으로 표시된다.
- padding-box: 기본 값으로, 배경 이미지가 안쪽 여백부터 채워지는 방식으로 표시된다.
- content-box: 배경 이미지가 콘텐츠 영역부터 채워지는 방식으로 표시된다.

### background-size

background-size 속성값 * 크기 지정: 크기를 나타내는 수치와 단위를 함께 입력해 크기를 조절한다. 너비와 높이에 해당하는 수치를 함께 입력할 수 있다. * cover: 이미지의 크기를 비율이 흐트러지지 않는 선에서 최대 크기로 조절한다. 가로 또는 세로 방향에서 잘리는 영역이 발생할 수 있다. * contain: 이미지의 크기를 비율이 흐트러지지 않고, 잘리지도 않는 선에서 최대 크기로 조절한다.

### background-position

background-position에 키워드를 입력해 위치를 지정하면 배경 이미지는 박스 안에서 키워드가 의미하는 위치에 맞게 이동한다.
```Html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Background</title>
    <style>
        #content {
            
            background: url("https://cdn.pixabay.com/photo/2017/08/01/22/10/people-2568247_1280.jpg") gray;
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            background-clip: content-box;
            /* display: none; */
            padding: 20px;
            border: 2px solid red;
            width: 1000px;
            height: 500px;
            box-shadow: 2px 2px 10px gray;
            text-align: center;

            display: table-cell;
            vertical-align: middle;
            
        }
        body{
            height: 100vh;
            background: url("https://cdn.pixabay.com/photo/2024/02/09/16/17/grey-whale-8563340_1280.png");
            background-repeat: repeat-x;
            background-size: contain;
        }
        #title {
            font-family: '궁서';
            font-size: 40pt;
            color: white;
            text-shadow: 1px 1px 10px purple;
            
        }
    </style>
</head>
<body>
    <div id="content">
        <div id="title">힘으로 안되는건 힘이 부족하기 때문이다</div>
    </div>
</body>
</html>
```

## 텍스트 꾸미기

---

### display

CSS의 display 속성은 요소의 유형을 변경할 수 있는 속성이다. 이를 이용하면 블록 레벨 요소와 인라인 요소를 바꿔가며 사용하는 것은 물론, 요소 내부의 레이아웃 유형까지도 다양하게 변경할 수 있다. 다음은 display 속성에 지정할 수 있는 대표적인 속성 값을 정리한 것이다.

- none: 요소를 화면에 표시하지 않는다.
- block: 요소를 블록 레벨 요소로 만든다.
- inline: 요소를 인라인 요소로 만든다.
- inline-block: 요소를 인라인 요소로 표시하되, 블록 레벨의 특성을 추가한다.
- flex: 요소를 블록 레벨 요소로 표시하되, 내부 레이아웃 방식을 flex로 변경한다.
- inline-flex: 요소를 인라인 요소로 표시하되, 내부 레이아웃 방식을 flex로 변경한다.

## 요소 내부의 레이아웃 변경하기

---

flex와 inline-flex는 display 속성에 지정할 수 있는 다른 속성값과 마찬가지로 요소가 화면에 표시될 때 어떤 형태로 공간을 차지할 것인지를 결정한다. flex는 요소를 블록 레벨로, inline-flex은 요소를 인라인으로 표시한다. 그런데 여기에서 그치지 않고, 두 속성은 지정된 요소의 내부 레이아웃 방식, 즉 자식 요소의 배치 방법에까지 영향을 끼친다. display에 flex 또는 inline-flex이 지정된 요소를 ‘플렉스 컨테이너’라 부르는데, 플렉스 컨테이너는 기본적으로 ‘플렉스 아이템’이라 불리는 자식 요소의 display 유형을 무시한 채 요소들을 일정한 방향으로 나란히 배치하는 특징을 가진다.

- flex-direction: 플렉스 컨테이너의 주축 및 플렉스 아이템의 진행 방향을 지정한다.
- flex-wrap: 플렉스 아이템 정렬 시 줄바꿈 여부를 지정한다.
- justify-content: 플렉스 컨테이너의 주축 위에서 플렉스 아이템의 배치 방법을 지정한다.
- align-items: 플렉스 컨테이너의 교차축 위에서 플렉스 아이템의 배치 방법을 지정한다.
- align-self: 플렉스 컨테이너의 교차축 위에서 플렉스 아이템의 배치 방법을 각 아이템에 개별적으로 지정한다.

### flex-direction

flex-direction의 기본값은 row로, 플렉스 컨테이너가 처음 만들어지면 주축을 가로축으로 설정해 왼쪽부터 오른쪽 방향으로 요소를 배치하는 것이 기본 특성이다. 그러나 flex-direction의 값을 column으로 변경하면 주축을 세로축으로 바꾸어 위에서부터 아래 방향으로 요소를 배치할 수 있다. 더불어 각 속성값에 접미사로 reverse를 추가할 경우에는 요소의 배치 방향을 반대로 변경할 수도 있다.

- row: 가로축을 주축으로 정하고 요소를 왼쪽부터 오른쪽 방향으로 배치한다.
- row-reverse: 가로축을 주축으로 정하고 요소를 오른쪽부터 왼쪽 방향으로 배치한다.
- column: 세로축을 주축으로 정하고 요소를 위에서부터 아래 방향으로 배치한다.
- column-reverse: 세로축을 주축으로 정하고 요소를 아래에서부터 위쪽 방향으로 배치한다.

### justify-content

justify-content는 플렉스 컨테이너의 주축 위에서 아이템을 어떤 방식으로 배치할 것인지 결정하는 속성이다. 이 속성은 컨테이너의 주축 길이보다 아이템의 길이 총합이 더 짧은 경우에, 아이템 사이의 남는 공간을 어떻게 배치할 것인지 결정하기 위해 주로 사용한다.

- flex-start: 아이템이 주축의 시작점에서 순서대로 배치된다.
- flex-end: 아이템이 주축의 끝점에서 순서대로 배치된다.
- center: 아이템이 주축의 중심부에서 순서대로 배치된다.
- space-between: 아이템이 일정한 간격을 둔 채 양끝 정렬 방식으로 배치된다.
- space-around: 아이템이 각자 동일한 여백을 갖도록 배치된다.
- space-evenly: 아이템 사이의 모든 간격이 동일하게 유지된 채 배치된다.
```Html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .item {
            display: inline-block;
            height: 100px;
            width: 100px;
            border: 2px solid red;
        }
        #head {
            display: flex;
            justify-content: flex-end;

        }
        #menu {
            list-style-type: none;
            padding: 0px;
            background-color: #0D4036;
            color: white;
        }
        #menu>li {
            display: inline-block;

        }
        #menu>li>a {
            color: white;
            text-decoration: overline underline;
            width: 100px;
            display: inline-block;
            text-align: center;
            font-weight: bold;
            padding: 10px;
            background-color: #0D4036
        }
        #menu>li>a:hover {
            background: #2A8C7A;
            color: aqua;
        }
        #container {
            display: flex;
            border: 2px solid blue;
            height: 300px;
            flex-direction: row;
            /* justify-content: space-around; */
            justify-content: space-between;
            /* justify-content: space-evenly; */
            /* justify-content: flex-end; */
            /* justify-content: center; */
            /* align-items: flex-end; */
            align-items: center;
            
        }
        #container>div:first-child {
            background-color: gray;
            align-self: flex-start;
        }
        #container>div:first-child {
            align-self: flex-end;
        }
    </style>
</head>
<body>
    <div>
        <ul id="menu">
            <li><a href="">홈</a></li>
            <li><a href="">네이버</a></li>
            <li><a href="">구글</a></li>
            <li><a href="">유튜브</a></li>
        </ul>
    </div>
    <div id="container">
        <div class="item">item1</div>
        <div class="item">item2</div>
        <div class="item">item3</div>
    </div>
</body>
</html>
```
