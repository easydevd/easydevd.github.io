---
layout: post
title: blueimp fileupload 라이브러리 
description: blueimp fileupload 라이브러리 수정하기
excerpt_separator: <!--more-->
categories: [jqery, js, library, blueimp, fileupload]
tags:       [jqery, js, library, blueimp, fileupload]
---

오늘은 fileupload.js 라이브러리를 받으면 많이 수정하는 부분들에 대해 알아보려 합니다.  

우선 jQuery File Upload Plugin을 다운로드 해주세요!  
다운로드 경로 : https://github.com/blueimp/jQuery-File-Upload

  
업로드할 수 있는 파일의 확장자는 **acceptFileTypes**를 수정해주면 됩니다.
~~~js
acceptFileTypes : /(\.|\/)(gif|jpe?g|png|pdf|doc|docx)$/i
~~~
로 수정하면 gif, jpg, jpeg, png, pdf, doc, docx 확장자를 가진 파일만 업로드할 수 있습니다.
  
파일 크기 제한은 **maxFIleSize**, 멀티업로드의 경우 파일 갯수 제한은 **maxNumberOfFiles** 각각 우너하는 옵션으로 수정해주면 됩니다.  

그래서 blueimp 라이브러리를 받아 jsp 페이지에 import시키고 파일 업로드시 변경할 옵션을 추가하려면 아래 정도로 수정할 수 있겠네요 
~~~js
$('#fileupload').fileupload(
  'option', {
      url : '~~.do',
      formData : {
        newParam : 'A'
      },
       disableImageResize : false,
       previewMaxWidth : 28,
       previewMaxHeight : 28,
       accpetFileTypes : /(\.|\/)(gif|jpe?g|png|pdf|doc|docx)$/i,
       maxFileSize : '5000000',
       maxNumberOfFiles : 10,
       dropZone : $("#dropZone')
       }
      );
~~~
    
**url**에는 파일을 전송할 경로,  
**dropZone**은 파일을 드래그 앤 드롭으로 선택했을 때 어느영역에 한해서 업로드 목록에 추가시킬지를 말하는 것입니다!  
    
좀 더 구체적인 부분들은 다음 포스팅으로 찾아올께요!
