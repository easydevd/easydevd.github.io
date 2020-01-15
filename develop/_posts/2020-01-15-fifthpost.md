---
layout: post
title: WINDOW에서 GITHUB 블로그 만들기 STEP 5 [ 게시글 경로 수정 ]
description: GITHUB 블로그 만들기 STEP 5
excerpt_separator: <!--more-->
---

지금까지 작성한 게시글은 모두, **[블로그주소]/hydejack** 경로에 작성되었습니다.  
오늘은 이 게시글의 경로를 바꿔보려 합니다.  

**/develop** 이라는 경로를 생성해, 개발 관련 포스트를 이곳에 작성할 예정입니다.  

우선 루트 경로의 **_featured_tags폴더로 이동해 develop.md 파일을 생성해주세요.**
~~~develop.md
---
layout: list
title: Develop
slug: develop
menu: true
order: 1
description: >
  개발일기
---
~~~

layout : 게시글 display 형태 [list, post]    
title : 경로 제목 [브라우저 탭에 표시할 타이틀]  
slug : url  
menu : true
order : 왼쪽 사이드 바에서 보여질 메뉴 순서입니다.  
description : 해당 경로에 포스팅 될 게시글에 대한 설명  

**새 md 파일을 작성하지 않고, hydejack.md 파일을 수정해 사용하셔도 무관합니다. 대신 파일 명까지 함께 변경해주세요.**  

<br>
다음은 *_config.yml* 파일의 menu 정보를 수정해야 합니다.  
**_config.yml 파일을 열어, 새로 사용할 메뉴 이름과 경로를 수정해주세요**
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_fifthpost/fifthpost_1.jpg){:style="display:block; width: 600px; border:solid 1px #00000052;"}

~~~
- title:             Develop
  url:               /develop/  
~~~

**이제 /develop 경로에 작성할 md 파일들이 있을 경로를 생성해주어야 합니다.**  
**기존 hydejack/_posts를 develop/_posts로 수정해주세요.**   
<br>
hydejack 경로를 추후 재사용할 예정이라면, 삭제하지 말고 hydejack폴더를 통째로 복사한 후  
develop이라는 이름으로 rename 시켜주면 됩니다.  
<br><br>
여기까지 수정했다면 이제 git bash를 통해 수정한 파일들을 모두 커밋해주세요.  
**하위 경로의 모든 파일과 폴더를 한번에 add 하려면, 해당 경로로 이동 한 후
아래 명령어를 사용하면 됩니다.**
~~~
git add .
~~~

저 같은 경우는 develop 폴더가 새로 추가 됬으니, develop경로로 이동한 후  
git add . 명령어를 사용하면 해당 경로의 파일이 모두 추가됩니다.  

<br><br>

반영이 완료된 후 다시 블로그에 접속하면, 아래 표시한 부분들이 모두 정상적으로 수정되었음을 확인 할 수 있습니다.
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_fifthpost/fifthpost_3.jpg){:style="display:block; border:solid 1px #00000052;"}
