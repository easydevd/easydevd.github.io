---
layout: post
title: WINDOW에서 GITHUB 블로그 만들기 STEP 1 [ RUBY, JEKYLL 설치 ]
description: GITHUB 블로그 만들기 STEP 1
excerpt_separator: <!--more-->
---

오늘은 Github를 사용한 블로그를 만들어 보려고 합니다.  
저는 윈도우에서 개발 진행중이어서, 작성 되는 모든 글은 윈도우를 기반으로 하고 있습니다.  
## 1. GITHUB 회원가입  
깃허브 블로그를 만들려면 제일 먼저 회원가입을 해야합니다.  
아래 주소에 들어가서 회원가입과 이메일 인증을 먼저 해주세요!  
[GITHUB, 깃허브](https://github.com/)  
![GITHUB 회원가입]({{ site.baseurl }}/assets/img/docs/blog_firstpost/firstpost_3.JPG){:data-width="1920" data-height="1200"}


## 2. RUBY 설치
윈도우는 루비가 기본으로 설치되어 있지 않기 때문에, 우선 루비를 다운받아야 합니다.  
아래 링크에서 다운로드 해주세요.  
[루비 다운로드](https://rubyinstaller.org/downloads/)  
![Ruby+Devkit 2.6.5-1 (x64) 클릭]({{ site.baseurl }}/assets/img/docs/blog_firstpost/firstpost_1.JPG){:data-width="1920" data-height="1200"}

다음버튼을 누르다보면 알아서 설치된답니다.  

설치가 완료되면, 아래 prompt를 실행시켜주세요.  
![Start Command Prompt With Ruby 클릭]({{ site.baseurl }}/assets/img/docs/blog_firstpost/firstpost_2.JPG){:data-width="1920" data-height="1200"}

## 3. JEKYLL 설치
PROMPT가 실행되면, 아래 명령어들을 순서로 입력해주세요.  

gem install jekyll  
gem install minima  
gem install bundler  
gem install jekyll-feed  
gem install tzinfo-data  

위 패키지 들이 모두 정상적으로 설치되면, 로컬에서 서버를 구동해 볼 수 있습니다.

샘플 블로그를 하나 만들어볼께요.  

jekyll new HelloBlog  
위 명령어 실행 후, 아래 그림처럼 정상적으로 생성 완료된것을 확인해줍니다.  
![Jekyll Site Installed]({{ site.baseurl }}/assets/img/docs/blog_firstpost/firstpost_4.JPG){:data-width="1920" data-height="1200"}

위 샘플 블로그를 실행시켜보겠습니다.  

cd HelloBlog  
bundle exec jekyll serve  

명령어 실행 후, http://127.0.0.1:4000/ 로 접속해 보세요.  
![]({{ site.baseurl }}/assets/img/docs/blog_firstpost/firstpost_5.JPG){:data-width="1920" data-height="1200"}
위 처럼, 사이트가 구동 된다면 성공적으로 JEKYLL 설치가 완료된 것입니다.  

그리고 아까 HelloBlog를 Install했던 경로로 들어가면  
![]({{ site.baseurl }}/assets/img/docs/blog_firstpost/firstpost_6.JPG){:data-width="1920" data-height="1200"}
위 파일들을 확인할 수 있습니다.  

보통 GITHUB 블로그 만들 때, JEKYLL 템플릿을 가져다 많이 사용하는데,  
그러지 않고 직접 만들려면 여기서 본인만의 사이트 개발 준비 하시면 됩니다.  

저는 템플릿을 가져다 사용할 예정이어서, 다음 포스트에서는 GIT 설치 후, 지킬 테마 적용하고, GITHUB와 연결시켜볼께요.  
