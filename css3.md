## Footer

Footer Page는 일반적으로 저작권 정보, 연락처, 관련된 문서 등의 내용을 포함하는 페이지의 최하단의 영역을 말한다.

<footer>태그는 문서나 특정 섹션의 푸터를 정의할 때 사용한다.

푸터는 보통 <footer> 요소가 포함되어 있는 문서나 섹션에 대한 아래와 같은 정보를 포함한다.

- 저자(author) 정보
- 저작권 정보
- 연락처
- 사이트맵
- 페이지 맨 위로 되돌아갈 수 있는 Top 버튼
- 연관 페이지

```html
<!DOCTYPE html>
<html lang="ko">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>화면 아래에 붙는 푸터</title>
    <style>
        body {
            width: 100%;
            min-width: 1000px;
            margin: 0px;
            display: flex;
            flex-direction: column;
        }
        footer {
            background-color: #f5f6f7;
            margin: 0px;
            padding: 20px;
            width: 100%;
            margin-top: auto;
        }
        footer .list_corp {
            list-style-type: none;
            padding: 0px;
            margin: 0px;
            display: flex;
            justify-content: center;
        }

        .list_corp>li:last-child {
            border-right: none;
        }

        .corp_item {
            padding: 0px 10px;
            border-right: 1px solid #999;
            display: inline-flex;
            justify-content: center;
            align-items: center;
        }
        .corp_item a {
            text-decoration: none;
            color: #404040;
            font-size: 1rem;
            text-align: center;
        }
        #content {
            /* height: 500px; */
        }
    </style>
</head>

<body>

    <div id="content">
        <h1>어떤 사이트의 내용</h1>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
        <div>어떤 콘텐츠</div>
 
        
    </div>

    <footer>
        <ul class="list_corp">
            <li class="corp_item">
                <a target="_blank" href="https://www.navercorp.com/">회사소개</a>
            </li>
            <li class="corp_item">
                <a target="_blank" href="https://recruit.navercorp.com/">인재채용</a>
            </li>
            <li class="corp_item">
                <a target="_blank" href="https://www.navercorp.com/naver/proposalInquire">제휴제안</a>
            </li>
            <li class="corp_item">
                <a target="_blank" href="https://www.naver.com/policy/service.html">이용약관</a>
            </li>
            <li class="corp_item">
                <a target="_blank"
                    href="https://www.naver.com/policy/privacy.html">
                    <strong>개인정보처리방침</strong></a>
                </li>
            <li class="corp_item">
                <a target="_blank" href="https://www.naver.com/policy/youthpolicy.html">청소년보호정책</a>
            </li>
            <li class="corp_item">
                <a target="_blank" href="https://policy.naver.com/policy/service_group.html">네이버
                    정책</a>
                </li>
            <li class="corp_item">
                <a target="_blank" href="https://help.naver.com/">고객센터</a>
            </li>
        </ul>
    </footer>

</body>

</html>
```
<img width="689" alt="스크린샷 2024-04-12 171950" src="https://github.com/dawoon1229/CSS_practice/assets/164113758/d9def8b6-2a4e-40b3-ab2f-34ba8affcd31">

