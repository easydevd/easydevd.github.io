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

## 2. Sitemap.xml 과 Robots.txt 작성하기
Sitemap 작성전에 우선 Sitemap이 뭔지 간단히 설명하고 시작할꼐요.  

Sitemap이란  
웹 크롤링을 위해 필요한, 웹사이트 내에 접속 가능한 페이지 목록을 말합니다.  
쉽게 어느 링크들이 유효한지 검색 엔진이 쉽게 알아 들을 수 있도록 제출하는 파일입니다.  
<br>
작성은 2가지 방법이 있습니다.
**1. jekyll-sitemap 플러그인 사용**<br>
**2. 직접 Sitemap 작성하기**  
<br>
1.번 방법은 **'_config.yml'** 에 jekyll-sitemap 플러그인을 추가하는 소스를 적어주면 됩니다.  
plugins에 'jekyll-sitemap'을 추가해주세요.  
![_config.yml OPEN]({{ site.baseurl }}/assets/img/docs/blog_eighthpost/img_10.jpg){:style="display:block; border:solid 1px #00000052;"}
<br>
2.번 방법은 가장 상위 경로에 'sitemap.xml' 파일을 만들고 아래 소스를 통째로 복붙해 넣어주세요.  
~~~sitemap.xml

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
