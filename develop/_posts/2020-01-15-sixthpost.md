---
layout: post
title: WINDOW에서 GITHUB 블로그 만들기 STEP 6 [ 탭 이미지 변경, favicon ]
description: GITHUB 블로그 만들기 STEP 6
excerpt_separator: <!--more-->
---

오늘은 사이트 상단의 favicon을 수정해보려 합니다.  
조금 꼼꼼한 편이어서 그런지 별게 다 신경쓰여서 수정하게 되었습니다.. :)  

현재 블로그 탭은 아래와 같이 보여지고 있습니다.  
저는 빨간 부분을 수정해보려 합니다.  
![favicon]({{ site.baseurl }}/assets/img/docs/blog_sisthpost/sixthpost_1.jpg){:style="display:block; width: 420px; border:solid 1px #00000052;"}

우선 **\_includes\head\links.html 파일을 열어 내용을 확인해주세요.**
그 중 '/assets/icons/favicon.ico'와 '/assets/icons/icon.png'로 인해 위와 같은 아이콘이 뜨는 것 입니다.  
![favicon]({{ site.baseurl }}/assets/img/docs/blog_sisthpost/sixthpost_2.jpg){:style="display:block; width: 420px; border:solid 1px #00000052;"}

그럼 사용할 favicon이미지를 고른 후, format에 맞게 사이즈와 확장자를 수정해 봅시다.  
저는 프로필 이미지로 수정할 예정입니다.  
>/assets/icons/profile/profile.jpg를 그냥 사용해도 favicon이 정상적으로 수정되긴합니다. 귀찮으신 분들은 확장자나 크키 상관없이 그냥 경로만 수정해주세요.

<br><br>


<br><br>
'/assets/icons/favicon.ico'는 32X32(px) 사이즈에 확장자가 ico입니다.  
[ICO 변환 사이트](https://icoconvert.com) 에 접속해 이미지를 새로 저장해주세요.  
저는 원형 아이콘을 사용하고 싶어서, **Step 3. Apply styles( optional )** 옵션을 선택했습니다.  
![favicon]({{ site.baseurl }}/assets/img/docs/blog_sisthpost/sixthpost_3.jpg){:style="display:block; width: 420px; border:solid 1px #00000052;"}

사이즈 [Custom Size-(32x32)] 지정 후 [Convert ICO] 버튼을 클릭해 이미지를 저장해주세요.  
다운로드는 **Download your icon(s)** 을 누르면 됩니다.  

'/assets/icons/icon.png'는 192X192(px) 사이즈에 확장자가 png입니다.  
[https://fotoram.io/editor/#round](https://fotoram.io/editor/#round) 이 사이트에서 이미지 radius와 확장자, 사이즈를 수정해 저장할 수 있습니다.  
[https://gbworld.tistory.com/1336] (https://gbworld.tistory.com/1336) 해당 블로그에 설명이 잘 나와있으니 참조하셔도 좋을 것 같습니다.  

여기까지 이미지를 새로 만들었다면, 이제 /assets/icons/ 경로에 파일을 옮기고, 수정한 경로대로  **\_includes\head\links.html 내용을 편집해주세요.**
![favicon]({{ site.baseurl }}/assets/img/docs/blog_sisthpost/sixthpost_4.jpg){:style="display:block; width: 420px; border:solid 1px #00000052;"}

그런 다음 반영을 완료하면 아래처럼 favicon 이미지가 변경되었음을 확인할 수 있습니다.
