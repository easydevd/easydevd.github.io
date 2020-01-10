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

<br>

아래는 C 드라이브로 이동 후 GIT 폴더를 만드는 명령어입니다.  
~~~
cd C:/
mkdir GIT(작업할 폴더 이름)
~~~

|명령어|내용|  
|---|---|   
| cd | Change Directory 경로 이동 |   
| mkdir | Make Directory 폴더 생성 |   

<br>

여기까지 따라해 본인의 워크스페이스 경로를 만들었다면, 이제 github에서 프로젝트 소스를 다운받아 볼께요.  

그러려면  
**순서 1. 작업할 폴더 경로로 이동한 후,**  
**순서 2. git clone 명령어를 사용해 프로젝트를 다운로드**  
하면 됩니다.  

<br>

Bash 창에 아래와 같은 명령어를 입력해주세요.
~~~
cd GIT(작업할 폴더 이름)
git clone "GITHUB 프로젝트 URL"
~~~

위 **"GITHUB 프로젝트 URL"** 은 전 포스팅에서 fork한 **Repository URL** 을 작성해주시면 됩니다.  
보통 **"https://github.com/[GITHUB아이디]/[GITHUB아이디].github.io"** 일거라고 생각 되네요.  
<br><br>
저의 경우는 **https://github.com/easydevd/easydevd.github.io** 였습니다.  
그래도 이해가 안가시는 분들은  
![GITHUB BASH]({{ site.baseurl }}/assets/img/docs/blog_thirdpost/thirdpost_1.jpg){:style="display:block; border:solid 1px #00000052;"}
위 URL을 복붙해주세요.  

<br>

명령어를 모두 실행하면, 아래와 같이 파일이 모두 다운로드 되었음을 확인할 수 있습니다.
![GITHUB BASH]({{ site.baseurl }}/assets/img/docs/blog_thirdpost/thirdpost_2.jpg)

|명령어|내용|  
|---|---|
| ls | LIST 현재 디렉토리 모든 파일, 폴더 조회 |     

## 2. ATOM 설치
이제 위에서 다운로드 받은 파일들을 수정할 편집기가 필요합니다.  
본인에게 편한 편집기라면 어느것이든 상관없어요. (Ex. Brackets...)  
저는 ATOM을 설치해 보겠습니다.  
<br>
[ATOM 사이트](https://atom.io/)에 접속해 [DOWNLOAD]버튼을 눌러 설치를 진행해주세요.  
<br>
![ATOM]({{ site.baseurl }}/assets/img/docs/blog_thirdpost/thirdpost_3.jpg)

ATOM을 다 설치헀다면 아톰 실행 후 **[ CTRL + SHIFT + O ]** 를 눌러 아까 다운받은 프로젝트를 열어주세요.  
또는 왼쪽 상단 **[ FILE - Open Folder... ]** 을 누르시면 됩니다.  

저의 경우는, "C:/GIT/easydevd.github.io"가 열리며 아래와 같은 창이 떴습니다.
![ATOM]({{ site.baseurl }}/assets/img/docs/blog_thirdpost/thirdpost_4.jpg)

## 3. 블로그 첫 글 쓰기
블로그에 글을 포스팅하기 전에 먼저 알아야 할 기본적인 개념들이 몇가지 있습니다.  

웹페이지는 보통 HTML, JS, CSS, NODEJS... 등과 같은 언어로 개발이 되는데, JEKYLL에서는 조금 생소한 확장자 파일을 보실 수 있습니다.  
바로 .md (MarkDown) 언어입니다.  
JEKYLL는 게시글 작성을 위해 MARKDOWN 언어를 사용해 .md 파일을 개발해야합니다.  
그리고, 그 밖의 환경설정 등과 같은 제어는 .yml파일에서 수정하시면 됩니다.  

그 중에서도 특히, **_config.yml** 파일은 JEKYLL 동작에 대한 설정 제어를 다루고 있습니다.

앞으로 글을 포스팅할 **_posts** 경로의 md 파일들은 수정이나 추가해도 서버에 자동으로 반영되지만,  
**_config.yml** 파일은 수정했다면 반드시 재빌드를 해줘야 합니다.  
**_config.yml** 은 여러 환경 설정과 변수들이 제어하고 있는데, 사이트가 빌드 될때 한번만 읽어들이기 때문입니다.

만약 개발 중 **_config.yml** 파일을 수정했다면, 현재 실행 중인 지킬 서비스를 중단하고, 아래 명령어를 입력해주세요!
~~~
bundle exec jekyll serve
~~~
 파일은
|확장자|내용|  
|---|---|
| .md | Markdown을 사용해 작성한 게시글 파일 |     
| _config.yml | Jekyll 블로그에 대한 설정값을 제어하는 파일 |     

여기까지 이해가 되셨다면, 이제 **_posts** 경로로 이동해 게시글을 써봅시다.  
제가 다운받은 hydejack 테마는 이미 게시글이 여러개 작성되어 있네요.  
우선 저는 **https://easydevd.github.io/hydejack/** 경로에 md파일을 작성해보겠습니다.  

<br>

ATOM을 실행시킨 후, 위에서 열어둔 프로젝트 안의 **hydejack/_posts** 폴더를 열어주세요.  
그러면 아래처럼 이미 작성되어 있는 .md 파일이 여러개 보일 것입니다.
<br>
![hydejack/_posts]({{ site.baseurl }}/assets/img/docs/blog_thirdpost/thirdpost_5.jpg)

해당 경로에서 **[ Ctrl + N ]** 또는 좌측 상단의 **[ File - New File ]** 을 눌러 새창을 열어주세요.  
아래처럼 새창이 뜨는지 확인해주세요.  

그런 다음 아래 내용을 복사해 붙여넣고, **오늘날자-test.md** 로 저장해줍니다.  
저는 '2020-01-10-test.md'로 저장했습니다.
~~~
---
layout: post
title: GITHUB 블로그 시작
description: GITHUB 블로그 시작했습니다 :)
excerpt_separator: <!--more-->
last_modified_at: 2020-01-10T14:49
---

{{page.description}}  
오늘은 {{page.last_modified_at}} 입니다.  

자주 들러주세요.
~~~

이제 저장해주세요.
![hydejack/_posts]({{ site.baseurl }}/assets/img/docs/blog_thirdpost/thirdpost_6.jpg)

위처럼 저장하고 나면, ATOM에 새로 추가된 파일이 녹색으로 표시됩니다.  
![hydejack/_posts]({{ site.baseurl }}/assets/img/docs/blog_thirdpost/thirdpost_7.jpg)

수정한 파일은 노랑, 새로 추가한 파일은 녹색으로 표시되니 개발하실 때 참고해주세요.  
<br><br>

이제 GIT BASH를 통해 github서버에 올려주면 글쓰기가 완료됩니다.  

GIT BASH에서 방금 생성한 md파일이 있는 경로로 이동해주세요.
~~~
cd hydejack/_posts
~~~

![hydejack/_posts]({{ site.baseurl }}/assets/img/docs/blog_thirdpost/thirdpost_8.jpg)
제대로 이동했는지, 위처럼 경로를 꼭 확인해주세요!  

경로를 확인했다면 이제 커밋만 하면 됩니다.  
아래 명령어를 복사해서 실행시켜 주세요.

~~~
git add '2020-01-10-test.md'
git commit -m 'test post'
git push
~~~

git add 뒤에는 방금 본인이 추가한 md파일명을 작성해주시면 됩니다.  
git commit -m 뒤의 **'test post'** 는 커밋시 작성할 메시지 입니다.  
나중에 뭔가를 수정하거나, 커밋할 파일에 특별한 내용이 있다면 그 내용으로 적어주세요.  

git push 명령어는 최초 실행시, 로그인 하라는 창이 뜰것입니다.  
github 계정대로 로그인 해주세요.  

<br>

여기까지 완료했다면, github 사이트에 들어갔을 때 방금 본인이 커밋한 파일을 확인할 수 있습니다.

![hydejack/_posts]({{ site.baseurl }}/assets/img/docs/blog_thirdpost/thirdpost_9.jpg)
위에 다른 md파일들도 많은데, 간략히 보기위해 이미지를 조금 편집했습니다.  
해당경로에 방금 작성한 파일이 정상적으로 보이는지 확인해주세요 :)  

1~2분후 본인 블로그에 들어가면 방금 추가한 페이지를 볼 수 있습니다.
접속 경로를 잘 모르겠다면,  

**[자신 블로그 주소]/[추가한 md 파일 경로와 이름]** 으로 접속하시면 됩니다.  
<br>
저의 경우는   **https://easydevd.github.io/hydejack/2020-01-10-test/**  로 접속하면 방금 등록한 포스트가 바로 보입니다.  

<br><br><br>

다음 포스트에서는 _config.yml 파일을 자신에게 맞도록 수정해볼게요 :)
