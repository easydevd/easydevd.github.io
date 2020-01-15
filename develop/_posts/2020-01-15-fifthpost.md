---
layout: post
title: WINDOW에서 GITHUB 블로그 만들기 STEP 5 [ 게시글 경로 수정 ]
description: GITHUB 블로그 만들기 STEP 5
excerpt_separator: <!--more-->
---

지금까지 작성한 게시글은 모두, **[블로그주소]/hydejack** 경로에 작성되었습니다.  
오늘은 이 게시글의 경로를 바꿔보려 합니다.  

**/develop** 이라는 경로를 생성해, 개발 관련 포스트를 이곳에 작성할 예정입니다.  

우선 루트 경로의 **_featured_tags경로로 이동해 develop.md 파일을 생성해주세요.**
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

layout : 게시글 display 형태 (post...)  
title : 경로 제목 [브라우저 탭에 표시될 내용]  
slug : url  
menu : true [메뉴 display : true]  
order : 왼쪽 사이드 바에서 보여질 메뉴 순서입니다.  
description : 해당 경로에 포스팅 될 게시글에 대한 설명  
