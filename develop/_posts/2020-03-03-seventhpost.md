---
layout: post
title: JEKYLL 블로그 구글 검색엔진 등록하기
description: GITHUB 블로그 만들기 STEP 7
excerpt_separator: <!--more-->
---

열심히 만든 블로그 혼자만 알고 있긴 아쉽겠죠!  
오늘은 블로그를 구글검색엔진에 등록시켜보겠습니다 :)

우선은 구글 계정이 있어야해요!
혹시 없는 분들은 계정을 만들고 시작해주세요.


## 1. Google Search Console 등록하기

[`Google Search Console`](https://search.google.com/search-console/about).를 클릭해
Google Search Console에 접속해주세요.

자신의 깃허브 블로그 주소를 복사해 아래처럼 붙여넣기 해줍니다.
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_eighthpost/img_2.JPG){:style="display:block; border:solid 1px #00000052;"}

<br>

계속 버튼을 누르면 아래처럼 팝업이 뜹니다.<br>
팝업의 인증서 파일을 다운받아, 루트경로에 붙여넣어주세요!
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_eighthpost/img_3.JPG){:style="display:block; border:solid 1px #00000052;width:500px;"}

<br>
붙여넣고 조금 기다리면, 소유권을 인증받을 수 있습니다.
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_eighthpost/img_4.JPG){:style="display:block; border:solid 1px #00000052;width:600px;"}


<br><br>
인증이 완료되면, 아래같은 화면에 접속할 수 있습니다.  
URL 등록을 조금 빨리 하고 싶다면, URL검사 창을 눌러보세요.  
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_eighthpost/img_5.JPG){:style="display:block; border:solid 1px #00000052;width:800px;"}

구글에서 본인의 블로그가 나오려면 '크롤링'이라는 작업이 필요합니다.<br>
'크롤링'은, 검색엔진이 깃허브 블로그에 들어있는 내용을 읽어가는 작업정도로 이해하시면 됩니다.  
저처럼 구글이 조금이라도 빨리 크롤링 작업을 완료했으면 하는 분들은 <br>
 'URL검사 창'의 '색인 생성 요청'버튼을 눌러주세요!
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_eighthpost/img_6.JPG){:style="display:block; border:solid 1px #00000052;width:800px;"}

이제 크롤링이 완료될 떄까지, 몇일 여유를 두고 기다려주면 됩니다!

## 2. SiteMap.xml 과 Robots.txt 작성하기
SiteMap 작성전에 우선 SiteMap이 뭔지 이해하고 갑시다.  

Sitemap이란  
웹 크롤링을 위해 필요한, 웹사이트 내에 접속 가능한 페이지 목록을 말합니다.  
쉽게 어느 링크들이 유효한지 검색 엔진이 쉽게 알아 들을 수 있도록 제출하는 파일입니다.  
<br>
작성은 2가지 방법이 있습니다.
**1. jekyll-sitemap 플러그인 사용**  
**2. 직접 SiteMap 작성하기**  
<br>
1.번 방법은 **'_config.yml'** 에 jekyll-sitemap 플러그인을 추가하는 소스를 적어주면 됩니다.  
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_eighthpost/img_10.JPG){:style="display:block; border:solid 1px #00000052;"}
<br>
2.번 방법은 가장 상위 경로에 'sitemap.xml' 파일을 만들고 아래 소스를 복붙해 넣어주세요.  
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_eighthpost/img_10.JPG){:style="display:block; border:solid 1px #00000052;"}
~~~
---
layout: null
---
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.sitemaps.org/schemas/sitemap/0.9 http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd" xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  {% for post in site.posts %}
    <url>
      <loc>{{ site.url }}{{ post.url }}</loc>
      {% if post.lastmod == null %}
        <lastmod>{{ post.date | date_to_xmlschema }}</lastmod>
      {% else %}
        <lastmod>{{ post.lastmod | date_to_xmlschema }}</lastmod>
      {% endif %}

      {% if post.sitemap.changefreq == null %}
        <changefreq>weekly</changefreq>
      {% else %}
        <changefreq>{{ post.sitemap.changefreq }}</changefreq>
      {% endif %}

      {% if post.sitemap.priority == null %}
          <priority>0.5</priority>
      {% else %}
        <priority>{{ post.sitemap.priority }}</priority>
      {% endif %}

    </url>
  {% endfor %}
</urlset>
~~~

<br><br>

이 때 반드시 **'_config.yml'** 파일의 url 부분에 자신의 깃허브 주소가 쓰여져 있어야 sitemap에서 접근이 가능합니다!!  
위 코드를 보면 {{sitemap.url}} 이라는 부분들이 있는데, 이 부분이 정상적으로 작동하려면 **'_config.yml'** 파일에 url이 명시되어 있어야 합니다.  

<br><br>

이제 Robots.txt 파일을 작성해볼께요.  

Robots.txt 파일은 웹 크롤러가, 깃허브 블로그 중 어느 링크에 방문 가능한지에 대한 정책을 담고 있습니다.  
<br>
가장 상위 경로에 **'Robots.txt'** 파일을 만들고, 아래 내용을 복붙해주세요.  
~~~

User-agent: *
Allow: /
Sitemap: {{ '/sitemap.xml' | relative_url | prepend: site.url }}

~~~

여기까지 끝났으면, GIT BASH를 통해 commit, push 해주면 됩니다.  


## 3. Google Search Console에 Sitemap 등록하기
방금 생성한 2파일을 모두 github에 등록했다면, 이제 Google Search Console에도 Sitemap을 등록해 주어야 합니다.  
[`Google Search Console SiteMap`](https://search.google.com/u/2/search-console/sitemaps)을 클릭해 Sitemaps 탭에 접속해주세요.  
아니면 좌측의 **Sitemaps** 라는 탭을 클릭해도 접속할 수 있습니다.  
<br>
그런 다음 **[사이트맵 URL 입력]** 부분에 'Sitemap.xml'을 작성하고 [제출]버튼을 클릭해주세요.  
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_eighthpost/img_11.JPG){:style="display:block; border:solid 1px #00000052;"}

제출이 성공적으로 완료되면, 아래처럼 제출된 사이트맵에서 결과를 확인할 수 있습니다.  
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_eighthpost/img_12.JPG){:style="display:block; border:solid 1px #00000052;"}  

<br><br><br>

구글 검색엔진이 정상적으로 크롤링은 마치려면 몇일 정도 기다려줘 합니다. :)  
느긋한 마음으로 기다리며 다음 포스팅으로 돌아올께요!
