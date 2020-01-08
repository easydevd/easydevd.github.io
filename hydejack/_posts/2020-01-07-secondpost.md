---
layout: post
title: WINDOW에서 GITHUB 블로그 만들기 STEP 2 [ GIT설치, JEKYLL THEME ]
description: GITHUB 블로그 만들기 STEP 2
excerpt_separator: <!--more-->
---

오늘은 저번 시간에 이어, GIT 을 설치하고 JEKYLL 테마를 적용해볼거에요.  
우선 GIT BASH를 설치합니다.  

## 1. GIT BASH 설치 [ For Window ]
GIT BASH는 윈도우에서 GIT을 사용하기 위해 필요합니다.  
아래 주소에서 GIT을 다운로드 해주세요.  

저는 윈도우용을 다운로드 했습니다.   
[GIT BASH 다운로드](https://git-scm.com/downloads)  
![GIT BASH]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_2.JPG)

위 Winodows를 클릭하면 알아서 설치파일이 다운로드 됩니다.  
혹시 다운로드가 안되면, 아래 파일들 중 본인 PC에 맞는 파일을 눌러 다시 다운로드 해주세요.  

<br><br>

![GIT BASH DOWNLOAD]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_14.JPG){:style="width:400px;"}


보통 **64-bit Git for Windows Setup.** 을 다운로드 받으실 것 같은데, 이 파일은 실행파일이고,  
아래 **64-bit Git for Windows Portable.** 은 무설치 버전 파일입니다.  

<br>

쉽게, 아래 Portable을 다운로드 받으면 흔히 아는 exe파일이 아닌 7z 압축파일이 다운로드 됩니다.

저는 exe파일로 설치 진행했습니다.  

<br><br><br>

다운로드가 완료되면, 설치파일을 실행시켜 주세요.
![GIT BASH_STEP1]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_3.jpg){:style="display:block; height:408px;"}
NEXT 버튼을 누릅니다.

<br><br>
![GIT BASH_STEP2]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_4.jpg){:style="display:block; height:408px;"}

|OPTION|EXPLAIN|  
|---|---|  
| Additional Icons - On the Desktop | 바탕화면에 바로가기 아이콘 추가 |  
| Windows Explorer Integration | 마우스 오른쪽 버튼 클릭 시, GIT 연결 옵션 추가  

* 참조 ![마우스 우클릭시]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_15.jpg){:style="width:200px;"}

|  
| Git LFS (Large File Support) | 용량이 큰 파일 지원  |  
| Associate .git* configuration files with the default text editor | .gif* 구성파일을 기본 텍스트 편집기와 연결  |  
| Associate .sh files to be run with Bash | .sh 파일 Bash에서 실행 가능하게 하기  |  
| Use a TrueType font in all console windows | 윈도우 콘솔에서 트루타입 폰트를 사용  |  
| Check daily for Git for Windows updates | 매일 업데이트 유무 확인하기 |  

저는 그냥 기본 체크되어 있는대로 설치 진행했습니다.

<br><br>

![GIT BASH_STEP3]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_5.jpg){:style="display:block; height:408px;"}
GIT 명령어를 실행할 편집기를 골라주세요.  
Git에서는 VIM을 권장 하고 있습니다.  

<br><br>

![GIT BASH_STEP4]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_6.jpg){:style="display:block; height:408px;"}

|OPTION|EXPLAIN|  
|---|---|  
| Use Git from Git Bash only | Git Bash에서만 Git 사용가능  |  
| Use Git from the Windows Command Prompt | CMD에서도 Git사용 가능  |  
| Use Git and optional Unix tools from the Windows Command Prompt | 윈도우 CMD 에서 GIT과 일부 유닉스 툴 사용가능 |  

<br>

마지막 옵션은 유닉스와 윈도우 명령이 충돌 나는 등의 문제가 발생할 수 있습니다. 잘 아시는 분만 선택해주세요.  
저는 추천되어 있는 옵션을 선택했습니다.  

<br><br>

![GIT BASH_STEP5]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_7.jpg){:style="display:block; height:408px;"}
Next 클릭  

<br><br>

![GIT BASH_STEP6]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_8.jpg){:style="display:block; height:408px;"}
Next 클릭  

<br><br>

![GIT BASH_STEP7]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_9.jpg){:style="display:block; height:408px;"}

|OPTION|EXPLAIN|  
|---|---|
| Checkout Windows-style, commit Unix-style line endings | Checkout시 윈도우 스타일, Commit시 유닉스 스타일 적용  |  
| Checkout as-is, commit Unix-style line endings | Checkout시 스타일 변환 없음, Commit시 유닉스 스타일 적용  |  
| Checkout as-is, commit as-is |  Checkout, Commit 둘다 스타일 변환 없음  |  

<br><br>

![GIT BASH_STEP8]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_10.jpg){:style="display:block; height:408px;"}
어떤 터미널 에뮬레이터를 사용할건지 선택해주세요.  

|OPTION|EXPLAIN|  
|---|---|
| Use MinTTY(the default terminal of MSYS2) | MinTTY terminal emulator 사용  |  
| Use Windows' default console window | Windows 기본 콘솔 사용  |  

<br><br>

![GIT BASH_STEP10]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_11.jpg){:style="display:block; height:408px;"}
추가 옵션 확인 후, Next버튼을 눌러주세요.  
[ Enable file system caching, Enable Git Credential Manager ] 은 기본 선택되어 있습니다.  

<br><br>

![GIT BASH_STEP11]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_12.jpg){:style="display:block; height:408px;"}
저는 특별히 추가하지 않았습니다.  
Next 클릭  

<br><br>

![GIT BASH_STEP12]({{ site.baseurl }}/assets/img/docs/blog_secondpost/secondpost_13.jpg){:style="display:block; height:408px;"}
Install을 시작해주세요.  

그냥 Next만 계속 눌러도 설치는 정상적으로 되지만, 이해를 돕기 위해 조금 더 자세히 적어뒀습니다.
