---
layout: post
title: WINDOW에서 GITHUB 블로그 만들기 STEP 4 [ _config.yml 수정하기 ]
description: GITHUB 블로그 만들기 STEP 4
excerpt_separator: <!--more-->
---

오늘은 **_config.yml** 을 일부 수정해보려고 합니다 :)

hydejack 테마의 **_config.yml** 은 주석이 잘 달려있어, 수정하시는데 큰 어려움 없을것이라고  
생각되지만 정리를 위해 포스트 작성합니다.

## 1. _ config.yml   

*_config.yml* 은 디렉토리의 가장 상위 단계에 존재합니다.  
아래처럼 파일을 찾아 열어주세요.
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_1.jpg){:style="display:block; border:solid 1px #00000052;"}

<br><br>

파일이 정상적으로 열렸다면, 아래 노란색으로 표시된 부분들을 수정해줍니다.
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_2.jpg){:style="display:block; width: 700px; border:solid 1px #00000052;"}

~~~
url : 본인의 GITHUB 블로그 주소  
baseurl : 본인의 GITHUB블로그 주소 뒤에 붙는 / 경로가 있다면 적어주세요.  
title : 블로그 제목  
description : 블로그 설명 ( 150 char )  
tagline : sidebar에 들어갈 짧은 설명 글  
~~~

저는 description은 딱히 수정하지 않았습니다. 본인의 블로그니 수정하시는 분들은 모두 본인에게 맞게 수정하시면 됩니다.  
위처럼 수정한 후 서버에 반영해보겠습니다.  


GIT BASH를 실행시킨 후, 전 포스트에서 사용했던 명령어를 사용해주세요.  
~~~
cd C:/GIT/easydevd.github.io (본인 작업 경로로 이동)  
git add '_config.yml'  
git commit -m 'edit url, title, tagline'  
git push  
~~~

위 명령어까지 수행하고, 조금 기다린 후 블로그에 접속하면 아래와 같이 수정된 것을 확인할 수 있습니다.  
다른 포스트에 *_config.yml* 은 수정 후, 서버에 재반영하는 명령어를 추가로 수행해줘야 한다고 작성했었는데
굳이 실행시키지 않아도 반영되네요..  
하지만 혹시라도 저 위 명령어 만으로 반영 안되시는 분이 계시다면, 전 포스트에 작성한 명령어 추가로 수행해 보시길 바랍니다.  
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_4_1.jpg){:style="display:block; width:250px; margin:auto; border:solid 1px #00000052;"}

<br><br>

스크롤을 내려 아래부분을 더 수정해볼께요.
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_5.jpg){:style="display:block; width: 600px; border:solid 1px #00000052;"}
~~~
logo : sidebar에 있는 로고 이미지  
author : 본인 기준으로 이름, 이메일 등을 수정  
menu : 블로그 메뉴 정보  
~~~

로고에 프로필 이미지를 사용할 수도 있지만, 당장은 생각이 없어서 저는 #을 사용해 주석을 걸었습니다.  
**_author에 대한 더 자세한 내용은, data/authors.yml 을 수정해야 합니다.**  
해당 부분은 아래에서 다뤄볼께요.  
menu는 말 그대로 좌측에 보이는 메뉴에 대한 정보를 말합니다.  
본인이 작성하고 싶은 글 위주로 카테고리를 만들어 수정하시면 됩니다.  

<br><br>
여기까지 수정한 뒤 반영하면, 아래처럼 로고 이미지가 없어진 모습을 확인할 수 있습니다.  
메뉴 정보를 바꾸셨다면, 아래 메뉴 목록도 같이 수정됬을거라 생각되네요.  
<br>
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_6.jpg){:style="display:block;width:250px; margin:auto; border:solid 1px #00000052;"}


<br><br>
이제는 sidebar에 있는 이미지를 지우고, 메인 컬러를 변경해보려 합니다.  
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_9.jpg){:style="display:block; width: 700px;  border:solid 1px #00000052;"}

~~~
permalink : 접속 경로  
paginate : 한 페이지에 보여줄 게시글 수  
paginate_path : 페이징할 경로 (위 기준으로, 1p는 path를 붙일 필요 없고, '/page-2/'.. 등을 붙이면 pagination 된다.)
accent_image : sidebar 배경 이미지  
accent_color : hydejack 기본 테마 기준, 청색  
theme_color : sidebar의 기본색  
~~~

저는 accent_image는 사용하고 싶지 않아, none 옵션을 주어 이미지가 더 이상 뜨지 않게 수정했습니다.  
이미지가 제거되면, 아래처럼 보이겠네요.  
theme_color는  rgb(25,55,71)로 수정 후, 개발자 도구에서 background-color를 잡으면  rgb(25,55,71)로 보입니다.  
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_8.jpg){:style="display:block; width:250px; margin:auto;border:solid 1px #00000052;"}
<br><br>
accent_color는 저처럼 수정하시면, 아래처럼 css가 잡히게 됩니다.  
왼쪽이 수정 전, 오른쪽이 수정 후 입니다.  
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_7.jpg){:style="display:block; border:solid 1px #00000052;"}

<br><br>

여기까지 수정하면, 정말 기본적인 *_config.yml* 을 수정했다고 볼 수 있겠네요.  

## 2. authors.xml
마크다운을 사용해 포스트를 작성하고 들어가면, 글 하단 부분에 아래와 같은 부분을 찾을 수 있습니다.  
노란색으로 표시되어 있는 **"_data/authors.xml"** 을 수정해봅시다.  
![authors.xml]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_11.jpg){:style="display:block; width: 650px; border:solid 1px #00000052;"}


<br><br>

![authors.xml]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_12.jpg){:style="display:block; border:solid 1px #00000052;"}

그 다음 About과 이미지경로를 수정해줍니다.  
![authors.xml]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_13.jpg){:style="display:block; border:solid 1px #00000052;"}

저는 프로필 이미지는 삭제하고 싶어 주석을 걸어뒀어요.  
About에는 본인이 쓰고 싶은 말을 적으시면 됩니다.  
~~~
You Can Send me Email <본인 이메일>  
Thank U for Inviting
~~~

![authors.xml]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_14.jpg){:style="display:block; border:solid 1px #00000052;"}
social 부분도 수정해주세요. 자신이 추가하고 싶은 SNS게정을 등록하시면 됩니다.  

<br><br>
여기까지 한 후 반영하면 아래처럼 변경됩니다.  
![authors.xml]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_15.jpg){:style="display:block; border:solid 1px #00000052;"}

이미지를 주석걸었을 뿐인데, 위에서 설정한 제 author name이 뜨는 이유는, **_includes/author.html을 참조하시면 알 수 있습니다.**  

**author.html의 일부 중**
~~~
{% if author.picture %}
  {% include components/hy-img.html class="avatar" img=author.picture alt=author.name %}
{% elsif plugins contains 'jekyll-avatar' %}
  {% assign avatar = author.social.github | default:author.github.username | default:author.github  %}
  {% include components/avatar-tag.html user=avatar %}
{% endif %}
~~~
위와 같은 부분이 있습니다.  
**저는 author.picture 구문을 타서 author.picture은 경로가 없지만 alt에 author.name이 찍히면서 제 이름이 출력되는 것입니다.**


author.name이 뜨는걸 원치 않기 때문에, author.html에 주석을 걸어 파일을 수정하겠습니다.
![authors.html]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_17.jpg){:style="display:block; border:solid 1px #00000052;"}
위처럼 7번 line에 주석을 건 후 커밋해주세요.  
그런 다음 다시 블로그에 접속하면 아래처럼 바뀐 화면을 보실 수 있습니다.
![authors.xml]({{ site.baseurl }}/assets/img/docs/blog_fourthpost/fourthpost_16.jpg){:style="display:block; border:solid 1px #00000052;"}
