---
layout: post
title: WINDOW에서 GITHUB 블로그 만들기 STEP 3 [ GIT BASH 연결, 블로그 첫글 쓰기 ]
description: GITHUB 블로그 만들기 STEP 3
excerpt_separator: <!--more-->
---

오늘은 로컬PC에 GIT 프로젝트를 다운받은 후, 블로그에 첫번째 post를 작성해보겠습니다.

## 1. GIT CLONE
git 프로젝트를 다운받기에 앞서, 앞으로 프로젝트를 작업할 workspace 경로를 하나 지정해주세요.  
**저는 C:/GIT 폴더에서 작업할 예정입니다.**

파일 탐색기에서 GIT 폴더를 만들어도 되고, BASH 에서 mkdir명령어를 사용해 폴더를 생성해도 됩니다.  

아래는 C 드라이브로 이동 후 GIT 폴더를 만드는 명령어입니다.  
~~~
cd C:/
mkdir GIT(작업할 폴더 이름)
~~~

<br><br>

여기까지 따라해 본인의 워크스페이스 경로를 만들었다면 이제 github에서 프로젝트 소스를 다운받아 볼께요.  

그러려면  
1. 작업할 폴더 경로로 이동한 후,  
2. git clone 명령어를 사용해 프로젝트를 다운로드  
하면 됩니다.  

<br>

Bash 창에 아래와 같은 명령어를 입력해주세요.
~~~
cd GIT(작업할 폴더 이름)
git clone "GITHUB 프로젝트 URL"
~~~

위 "GITHUB 프로젝트 URL"은 전 포스팅에서 fork한 Repository URL을 작성해주시면 됩니다.
보통 "https://github.com/[GITHUB아이디]/[GITHUB아이디].github.io"일거라고 생각 되네요.  
저의 경우는 **https://github.com/easydevd/easydevd.github.io** 였습니다.  
그래도 이해가 안가시는 분들은  
![GITHUB BASH]({{ site.baseurl }}/assets/img/docs/blog_thirdpost/thirdpost_1.jpg)
을 복붙해주세요.  

명령어를 모두 실행하면, 아래와 같이 파일이 모두 다운로드 되었음을 확인할 수 있습니다.
![GITHUB BASH]({{ site.baseurl }}/assets/img/docs/blog_thirdpost/thirdpost_2.jpg)
