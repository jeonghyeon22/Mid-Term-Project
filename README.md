# Mid-Term-Project
opensource SW활용 중간고사대체과제
<!DOCTYPE html>
<html>
    <head>
        <title>김정현의 블로그</title>
        <!-- 초기화 -->
        <style>
            * { 
                margin: 0; padding: 0;
                font-family: '맑은 고딕', 'Malgun Gothic', Gothic, sans-serif;
            }
            a { text-decoration: none; }
            li { list-style: none; }
        </style>
        <!-- 기본 클래스 -->
        <style>
            .pull-left { float: left; }
            .pull-right { float:right; }
        </style>
        <!-- 페이지 -->
        <style>
            body {
                width: 960px; margin: 0 auto;
                background: #edffe6;
            }
            p1{
                font-style: italic;
            }
            p2{
                font-weight: 1000;
                color:#000000;
            }


            #page-wrapper {
                background: rgb(255, 255, 255);
                margin: 40px 0; padding: 10px 20px;
                border-radius: 5px;
                box-shadow: 0 2px 6px rgba(100, 100, 100, 0.3);
            }
        </style>
        <!-- 헤더 -->
        <style>
            #main-header { 
                padding: 60px 70px; 
                background-image: url('title_img.jpg');
                background-size: 100%;
                background-repeat: no-repeat;
            }
            .master-title { 
                font-size: 30px; 
                color: #ffffff;
            }
            .master-description {
                font-size: 15px; font-weight: 400;
                color: #000000;
            }
        </style>
        <!--4.내비게이션 및 풀다운 메뉴 구성하기-->
        <style>
            #main-navigation {
                /* 안쪽 블로그 틀 border*/
                border-top: 1px solid #C8C8C8;
                border-bottom: 1px solid #C8C8C8;
                margin-bottom: 20px;
                height: 40px;
            }
            
            .outer-menu-item {
                float: left;
                position: relative;
            }
            .outer-menu-item:hover {
                /*왼쪽 메뉴 눌렀을때 디자인*/
                background: rgb(143, 202, 137);
                color: rgb(255, 255, 255);
            }

            .menu-title {
                /* 메뉴 디자인*/
                display: block;
                height: 30px; line-height: 30px;
                text-align: center;
                padding: 5px 20px;
            }

            .inner-menu {
                /*기본정보~ 학교생활 블럭*/
                display: none;
                position: absolute;
                top: 40px; left: 0;
                width: 100%;

                background: rgb(78, 83, 249);
                box-shadow: 0 2px 6px rgba(5, 5, 5, 0.9);
                z-index: 1000;

                text-align: center



            }

            .inner-menu-item > a {
                display: block;
                padding: 5px 10px;
                color: rgb(41, 234, 234)
            }

            .inner-menu-item > a:hover {
                /*안쪽 메뉴에 마우스 가져다댔을때에 대한 스타일*/
                background: black;
                color: rgb(255, 0, 238);
            }
        </style>
        <!--5. 검색 양식 추가하기(내부게이션 내부 검색)-->
        <style>
            .search-bar {
                height: 26px;
                padding: 7px;
            }
            .input-search {
                display: block;
                float: left;

                background-color: #FFFFFF;
                border: 1px solid #CCCCCC;
                border-radius: 15px 0 0 15px;
                box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);

                width: 120px; height: 24px;
                padding: 0 0 0 10px;
                font-size: 12px;
                color: #555555;
            }

            .input-search:focus {
                border-color: rgba(82, 168, 236, 0.8);
                outline: 0;
                box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
            }

            .input-search-submit {
                display: block;
                float: left;

                width: 50px; height: 26px;
                border-radius: 0 15px 15px 0;
                border: 1px solid #CCCCCC;

                margin-left: -1px;

                vertical-align: top;
                display: inline-block;
            }
        </style>
        <!--6. 본문 추가하기(중앙내용)-->
        <style>
            /* body 태그의 너비: 960픽셀 */
            /* #page-wrapper 태그의 padding 속성으로 내용물 너비는 920픽셀 */
            #content { overflow: hidden; }
            #main-section {
                float: left;
                width: 710px;
            }
            #main-aside {
                float: right;
                width: 200px;
            }
        </style>
        <!-- 좌측 내용물 / 6. 본문 추가하기(본문 포스트 위쪽) -->
        <style> /*갤러리 슬라이드!!*/
            /* 브라우저 마진과 패딩 리셋 */
            * {margin:0;padding:0;}
        
            /* INPUT 가리기 */
            .section [id*="slide"] {display:none;}
            
            /* 슬라이드 영역 - max-width 크기를 조절해주기*/
            .section .slidewrap {max-width:600px;max-height:800px; margin:0 auto;overflow:hidden;position:relative;}
            .section .slidelist {white-space:nowrap;font-size:0;}
            .section .slidelist > li {display:inline-block;vertical-align:middle;width:100%;transition:all .5s;}
            .section .slidelist > li > a {display:block;position:relative;}
        
            /* 좌우로 넘기는 LABEL버튼에 대한 스타일 */
            .section .slide-control {position:absolute;top:0;left:0;z-index:10;width:100%;height:100%;}
            .section .slide-control label {position:absolute;z-index:1;top:50%;transform:translateY(-50%);padding:50px;cursor:pointer;}
            .section .slide-control .left {left:30px;background:url('./img/left.png') center center / 100% no-repeat;}
            .section .slide-control .right {right:30px;background:url('./img/right.png') center center / 100% no-repeat;}
            .section .slide-control [class*="control"] {display:none;}
        
    
            /* INPUT이 체크되면 변화값이 li까지 전달되는 스타일 */
            .section [id="slide01"]:checked ~ .slidewrap .slidelist > li {transform:translateX(0%);}
            .section [id="slide02"]:checked ~ .slidewrap .slidelist > li {transform:translateX(-100%);}
            .section [id="slide03"]:checked ~ .slidewrap .slidelist > li {transform:translateX(-200%);}
            .section [id="slide04"]:checked ~ .slidewrap .slidelist > li {transform:translateX(-300%);}
            
            /*  INPUT이 체크되면 변화값이 좌우 슬라이드 버튼을 담고 있는 div 까지 전달되는 스타일 */
            .section [id="slide01"]:checked ~ .slidewrap .control01 {display:block;}
            .section [id="slide02"]:checked ~ .slidewrap .control02 {display:block;}
            .section [id="slide03"]:checked ~ .slidewrap .control03 {display:block;}
            .section [id="slide04"]:checked ~ .slidewrap .control04 {display:block;}
        </style>
        <style>/*움직이는 자기소개글*/
            article { 
                padding: 0 10px 20px 10px;
                border-bottom: 1px solid #C8C8C8;
            }

            .article-header { padding: 20px 0; }
            .article-title { 
                font-size: 25px;
                font-weight: 700; 
                padding-bottom: 10px;
                background-color: rgb(255, 238, 238);
            }
            .article-date { font-size: 15px; font-weight: 600;
                display: inline-block;
                background-color:rgb(244, 162, 162);} 
            .article-body {font-size: 13px; text-align: center;}
            #container{
                font-size: 0px;
            }
            .A{
                display: inline-block;
                font-size: 10px;

                width: 200px;
                height: 200px;
                vertical-align: middle;
                position:relative;
                z-index: 1;
            }
            .B{
                display: inline-block;
                font-size: 15px;

                width: 0px;
                height: 200px;

                color:rgb(255, 255, 255);
                background-color: #fc8787;
                border-top-right-radius: 10px;
                border-bottom-right-radius: 10px;

                overflow: hidden;

                vertical-align: middle;

                transition-duration: .5s;

                margin-left: -52px;
                z-index: 0;
            }
            .B h1,
            .B p{
                width: 300px;
                padding-left: 30px;
                padding-right: 5px;
            }
            .A:hover + .B{
                width: 500px;
            }    
        </style>
    
        <!-- 우측 구성 -->
        <style>
            .aside-list { padding: 10px 0 30px 0; }
            .aside-list > h3 {
                font-size: 15px;
                font-weight: 600;
            }
            .aside-list li a {
                margin-left: 8px;
                font-size: 13px;
                color: #ff00f2;
            }
        </style>
        <script src="http://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
        <script>
            $(document).ready(function () {
                $('.outer-menu-item').hover(function () {
                    $(this).find('.inner-menu').show();
                }, function () {
                    $(this).find('.inner-menu').hide();
                });
            });
            $(function() {
                $(".editor_img").each(function() {
                var title = $(this).attr('title');
                var alt = $(this).attr('alt');
                });
            });
        </script>
    </head>
    <body>
        <!--전체 감싸는 태그-->
        <div id="page-wrapper">
            <!--헤더-->
            <header id = "main-header">
                <hgroup>
                    <h1 class ="main-title"> 김정현의 블로그</h1>
                    <h2 class = "master-description"><br>김정현에 대한 모든 것 </h2>
                </hgroup>
            </header>
            <nav id ="main-navigation">
                <div class="pull-left">
                    <ul class ="outer-menu"> 
                        <li class="outer-menu-item">
                            <span class ="menu-title"> 기본정보</span>
                            <ul class="inner-menu">
                                <li class="inner-menu-item"><a href="#">인사</a></li>
                                <li class="inner-menu-item"><a href="#">정보</a></li>
                                <li class="inner-menu-item"><a href="#">성격</a></li>
                                <li class="inner-menu-item"><a href="#">인생타임라인</a></li>
                                <li class="inner-menu-item"><a href="#">인생목표</a></li>
                            </ul>
                        </li>
                        <li class="outer-menu-item">
                            <span class ="menu-title"> 취미생활 </span>
                            <ul class="inner-menu">
                                <li class="inner-menu-item"><a href="#">사진찍기</a></li>
                                <li class="inner-menu-item"><a href="#">SNS활동</a></li>
                                <li class="inner-menu-item"><a href="#">유튜브시청</a></li>
                                <li class="inner-menu-item"><a href="#">헬스</a></li>
                            </ul>
                        </li>
                        <li class="outer-menu-item">
                            <span class ="menu-title"> 학교생활</span>
                            <ul class="inner-menu">
                                <li class="inner-menu-item"><a href="#">학교 및 학과소개</a></li>
                                <li class="inner-menu-item"><a href="#">시간표</a></li>
                                <li class="inner-menu-item"><a href="#">친구소개</a></li>
                            </ul>
                        </li>
                    </ul>
                </div>
                <div class ="pull-right">
                    <div class="search-bar">
                        <form>
                            <input type="text" class = "input-search">
                            <input type="submit" class = "input-search-submit" value="검색">
                        </form>
                    </div>
                </div>
            </nav>
                


            <div id="content">
                <section id = "main-section">
                    <article>
                        <div class ="article-header">
                            <h1 class="article-title"> 기본정보 </h1>
                            <h2 class ="article-date"> 인사</h2>
                        </div>
                        <div class="article-body">
                            <p>
                                안녕하세요. 
                                어쩌고저쩌고할라랄항ㅁㄴ러ㅣㅣㅇ남러ㅏㄴㅇㅁ<br><br><br><br><br><br><br><br>

                            </p>
                        </div>
                        <div class ="article-header">
                            <h2 class ="article-date"> 정보</h2>
                        </div> 
                        <div id="container">
                            <div class="A">
                                <img src="증명사진.jpg" class='editor_img' alt="사진" title='김정현_사진'width="150px" >
                            <br>
                            </div>
                            <div class="B">
                                <h1>
                                    김정현(KIM JEONGHYEON , 金正賢)
                                </h1>
                                <p>
                                    바를 정 어질 현<br>
                                    바르고 너그럽고 착하게 살아가라는 의미<br><br>
                                    나이 : 만 20세 <br>
                                    생일 : 2월 22일<br>
                                    학과 : 컴퓨터공학과 <br>
                                    학번 : 32201010 (20학번) <br>
                                    사는 곳 : 경기도 의왕시 인덕원삼호아파트
                                </p>
                            </div>
                        </div>   
                        <div class="article-body">
                            <p> <br><br> 집 위치는 아래 지도에서 확인할 수 있습니다. <br><br></p>
                            
                                <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3169.6996794383244!2d126.97872921513554!3d37.39693397982992!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x357b5e442ad36c25%3A0xdc44c2122fd84b0f!2z7J24642V7JuQ7IK87Zi47JWE7YyM7Yq4!5e0!3m2!1sko!2skr!4v1651766397421!5m2!1sko!2skr" 
                                width="350" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade" aria-hidden="false">
                                </iframe>
                                <br><br><br>
                            </p>
                        </div>
                        <div class ="article-header">
                            <h2 class ="article-date"> 성격</h2>
                        </div> 
                        <div class="article-body">
                             내 성격은 어쩌고 ~ 내용추가<br><br><br>
                                MBTI에 대해서 내용추가~ <br><br><br>
                            <p2 style ="color: red;">[ESTP 특징]<br><br></p2>  
                            <p1>   
                                 ESTP 유형은 다른 사람에게 관대하고 느긋하다. 어떤 사람이나 사건에 대해 별로 선입견을 갖지 않으며 개방적이다. 특별히
                                갈등이나 긴장 상황을 잘 조절하고, 현실적으로 발생하는 문제를 해결하는데 뛰어난 능력을 발휘하기도 한다. 일을 진행할 때
                                기존의 방식에 따라 일을 진행하기보다는 실용적인 방법의 새로운 시스템을 만들어 내고자 한다. 이들은 남녀모두 행동파이고,
                                외부로 에너지를 발산하는 것을 좋아한다. <br>무엇인가 행동을 해야 하는 상황을 좋아하며, 눈 앞에 벌어지는 상황에 즉각적으로
                                참여한다. 평소에 생동감이 넘치고 주변 사람을 즐겁게 하는 재미있는 사람들이며, 삶을 재미있게 생각하기 때문에 사람들이
                                이들과 사귀는 것을 좋아한다.
                                ESTP 유형은 현실적인 문제를 다루며 행동지향적이고 적응력이 필요한 일을 선호한다. 또한 자신의 현실 감각을 발휘할 수
                                있는 분야에서 일하고자 한다. 이들은 자신의 활동에 대해 구속받는 것을 싫어하며, 업무에 분명한 목표는 있지만 일을 해나가
                                는 과정에서 융통성을 발휘할 수 있는 환경을 좋아한다. 업무와 재미가 공존할 수 있는 일을 선호하고, 활기차고 생동감 넘치
                                며 결과지향적인 동료와 함께 일하는 것을 선호한다. <br><br><br>
                            </p1>   
                            <p2 style ="color: rgb(111, 0, 255);">자세한 내용은 아래 PDF 참고
                                <br><br><br>
                                <object width="800" height="700" data ="MBTi 검사.pdf"></object>
                                <br><br><br><br>
                            </p2>
                        </div>
                    </article>    
                    <article>
                         <div class ="article-header">
                            <h1 class="article-title"> 취미생활 </h1>
                        </div>
                        <div class="article-body">
                            <p2>으아악 나에겐 많은 취미생활이 있지 어쩌고 저쩌고 내용추가<br><br><br><br><br><br></p2>
                        </div>
                        <div class ="article-header">
                            <p class ="article-date"> 사진찍기</p>
                        </div>
                        <div class="article-body">
                            <p> 사진찍기는 제 취미 중 하나입니다. 
                                <br> 일상생활에서 보이는 예쁜 것들을 찍는 것을 좋아합니다. <br>
                                귀여운 소품이 있는 소품샵에서, 분위기있는 카페에서, 야외에서 사진을 많이 찍습니다.<br>
                                특히 야외의 풍경을 찍는 것을 좋아합니다. 너무 쨍한 햇살이 아닌 해가 떨어지기 2시간 전의 햇살을 좋아합니다. 
                                <br>그 시간에 햇빛에 비치는 꽃과 식물 그리고 바다의 잔잔함을 사진에 많이 담곤합니다.
                                <br><br><br><br><br><br></p>
                        </div>
                        <div class="section">
                            <input type="radio" name="slide" id="slide01" checked="">
                            <input type="radio" name="slide" id="slide02">
                            <input type="radio" name="slide" id="slide03">
                            <input type="radio" name="slide" id="slide04">
                            <div class="slidewrap">
                                <ul class="slidelist">
                                    <li>
                                        <a>
                                            <img src="./img/img1.jpg">
                                        </a>
                                    </li>
                                    <li>
                                        <a>
                                            <img src="./img/img2.jpg">
                                        </a>
                                    </li>
                                    <li>
                                        <a>
                                            <img src="./img/img3.jpg">
                                        </a>
                                    </li>
                                    <li>
                                        <a>
                                            <img src="./img/img4.jpg">
                                        </a>
                                    </li>
                                </ul>
                        
                                <div class="slide-control">
                                    <div class="control01">
                                        <label for="slide04" class="left"></label>
                                        <label for="slide02" class="right"></label>
                                    </div>
                                    <div class="control02">
                                        <label for="slide01" class="left"></label>
                                        <label for="slide03" class="right"></label>
                                    </div>
                                    <div class="control03">
                                        <label for="slide02" class="left"></label>
                                        <label for="slide04" class="right"></label>
                                    </div>
                                    <div class="control04">
                                        <label for="slide03" class="left"></label>
                                        <label for="slide01" class="right"></label>
                                    </div>
                                </div>
                            </div>
                        </div><br><br>
                        <div class ="article-header">
                            <p class ="article-date"> SNS활동</p>
                        </div>
                        <div class="article-body">
                            어어어~ 링크 추가,,,, 내용추가
                        </div><br> 
                        <div class ="article-header">
                            <p class ="article-date"> 유튜브시청</p>
                        </div>
                        <div class="article-body">
                            어어어~ 유튜브 링크 추가하기 !!!내용추가
                        </div><br> 
                        <div class ="article-header">
                            <p class ="article-date"> 헬스</p>
                        </div>
                        <div class="article-body">
                            어어어~ 내용추가
                        </div><br> 
                     </article>






                    <article>
                        <div class ="article-header">
                            <h1 class="article-title"> 학교생활 </h1>
                        </div>
                        <div class="article-body">
                            <p2>
                                저의 학교와 관련된 것에 대해서 소개하겠습니당다ㅏㅇ당리 내용추가
                                <br>
                            </p2>
                        </div>
                        <div class ="article-header">
                            <p class ="article-date"> 학교 및 학과 소개</p>
                        </div>
                        <div class="article-body">
                            <p> <br><br> 저는 경기도 용인에 위치한 단국대학교에 재학 중인 컴퓨터공학과 3학년입니다.내용추가  <br><br></p>
                            
                            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d203064.48656319897!2d126.98667526245113!3d37.321608438076815!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x357b5755cbac9e51%3A0xda0d379a7fe9c5f3!2z64uo6rWt64yA7ZWZ6rWQ!5e0!3m2!1sko!2skr!4v1651781874705!5m2!1sko!2skr"
                                width="350" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade" aria-hidden="false">
                                </iframe>
                                <br><br><br>
                            </p>

                            컴퓨터공학과 어쩌고저쩌고내용추가<br><br>
                            <p2>
                            <a href="https://www.dankook.ac.kr/web/kor/-184?p_p_id=DeptInfo_WAR_empInfoportlet&p_p_lifecycle=0&p_p_state=normal&p_p_mode=view&p_p_col_id=column-2&p_p_col_count=1&_DeptInfo_WAR_empInfoportlet_action=view" 
                            target="_blank">컴퓨터공학과 자세한 정보보기</a>
                            <br><br>
                            </p2>


                        </div>
                        <div class ="article-header">
                            <p class ="article-date"> 시간표</p>
                        </div>
                        <div class="article-body">
                            <p>
                                제 시간표에 대해서 소개하겠습니다.<br><br>
                                3학년 1학기인 이번 학기에 저는 6전공 1자유로 총 19학점을 듣습니다. 원래 22학점을 들으려고했으나 수강신청실패로 3학점을 신청하지 못했습니다.
                                수강 정정으로 다른 수업에 들어갈 수 있었지만 아르바이트 및 연구실과제 등으로 시간이 부족할 것 같아 현실과 타협하여 전공16학점과 자유3학점을 듣기로 결정했습니다.<br><br>
                                아르바이트가 월요일에 있어 월요일에는 비대면으로 수업을 하는 과목 제외하고 다른 과목을 넣지 않았고, 통학이기 때문에 되도록이면 학교에 오지 않는 방법으로 수강계획을 세워 월요일, 수요일 공강을 만들었습니다!
                                <br><br>아래 시간표가 저의 이번학기 시간표입니다. <br><br><br>
                            </p>
                            <table border="1">
                                <caption > 3학년 1학기 강의시간표</caption>
                                <colgroup>
                                    <col style="background-color: rgb(255, 226, 226);">
                                    <col>
                                    <col>
                                    <col style="width:30px;">
                                </colgroup>
                                <thead>
                                    <tr>
                                        <th> 교시/요일</th>
                                        <th> 월</th>
                                        <th> 화</th>
                                        <th> 수</th>
                                        <th> 목</th>
                                        <th> 금</th>
                                    </tr>
                                    </thead>
                                <tbody>
                                    <tr>
                                        <th> 1</th>
                                        <td> </td>
                                        <td rowspan ="2"> 데이터베이스</td>
                                        <td rowspan ="10"> 공<br><br><br>강 </td>
                                        <td rowspan ="2"> 오토마타</td>
                                        <td rowspan ="2"> 인터넷프로토콜 </td>
                                    </tr>
                                    <tr>
                                        <th> 2</th>
                                        <td> </td>
                                        
                                    </tr>
                                    <tr>
                                        <th> 3</th>
                                        <td> 데이터베이스</td>
                                        <td> </td>
                                        <td> 인공지능 </td>
                                        <td> 오토마타 </td>
                                    </tr>
                                    <tr>
                                        <th> 4</th>
                                        <td> </td>
                                        <td> </td>
                                        <td> </td>
                                        <td> </td>
                                    </tr>
                                    <tr>
                                        <th> 5</th>
                                        <td> </td>
                                        <td rowspan ="2"> 자바프로그래밍 </td>
                                        <td> 인터넷프로토콜 </td>
                                        <td rowspan ="2"> 인공지능 </td>
                                    </tr>
                                    <tr>
                                        <th> 6</th>
                                        <td> </td>
                                        <td> </td>
                                        
                                    </tr>
                                    <tr>
                                        <th> 7</th>
                                        <td> </td>
                                        <td> </td>
                                        <td> 자바프로그래밍 </td>
                                        <td rowspan ="2"> 기초 FPGA </td>
                                    </tr>
                                    <tr>
                                        <th> 8</th>
                                        <td> </td>
                                        <td rowspan ="3"> 오픈소스 </td>
                                        <td> </td>
                                        
                                    </tr>
                                    <tr>
                                        <th> 9</th>
                                        <td> </td>
                                        <td> </td>
                                        <td> </td>
                                        
                                    </tr>
                                        <tr>
                                            <th> 10</th>
                                            <td> </td>
                                            <td> </td>
                                            <td> </td>
                                            
                                        </tr>
                                </tbody>
                             </table><br>
                        </div>
                    </article>
                </section>
                <aside id="main-aside">
                    <div class="aside-list">
                        <h3> 카테고리</h3>
                        <ul>
                            <li> <a href="#"> 데이터 </a></li>
                            <li> <a href="#"> 데이터 </a></li>
                            <li> <a href="#"> 데이터 </a></li>
                            <li> <a href="#"> 데이터 </a></li>
                            <li> <a href="#"> 데이터 </a></li>
                            <li> <a href="#"> 데이터 </a></li>

                        </ul>
                    </div>
                    <div class="aside-list">
                        <h3> 최근글</h3>
                        <ul>
                            <li> <a href="#"> 기본정보 </a></li>
                            <li> <a href="#"> 데이터 </a></li>
                            <li> <a href="#"> 데이터 </a></li>
                            <li> <a href="#"> 데이터 </a></li>
                      </ul>
                    </div>
                </aside>
            </div>
            <footer id=""main-footer>
                <a href = "#">김정현의 자기소개 BLOG </a>
                <address>
                   <a href = "mailto:wjdgusdl3532@naver.com">이메일 전송</a>
                   <a href = "tel:+821029983766">전화걸기</a>
                </address>
             </footer>  
        </div>
    </body>
</html>
