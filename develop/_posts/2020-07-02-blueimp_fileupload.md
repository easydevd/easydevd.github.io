---
layout: post
title: blueimp fileupload, dropZone 수정하기
description: blueimp fileupload, dropZone 수정하기
excerpt_separator: <!--more-->
categories: [jqery, js, library, blueimp, fileupload, dropZone]
tags:       [jqery, js, library, blueimp, fileupload, dropZone]
---

dropZone은 사용자가 임의로 영역을 설정해 줄 수 있습니다.

~~~css
#dropZone{
  height: 180px;
  position : relative;
  opacity : 0.3;
  border : dashed 1px #000;
}

.fade{
  opacity : 0;
  -webkit-transition : opacity .15s linear;
  -o-transition : opacity .15s linear;
  transition : opacity .15s linear;
 }
  
 .fade.in{
    opacity : 1
 }
  
  #dropzone.in {
    background-color : #44b683;
    border-color : #fff;
    color : #fff;
    opacity : 1;
  }
~~~

~~~html
<div id="dropZone" class="fade well">
  <div class="txt">Drap &amp; Drop</div>
</div>
~~~

~~~js
$('#dropZone').bind('dragover', function(e){
  var dropZone = $('#dropzone'),
      timeout = window.dropZoneTimeout;
  e.preventDefault();
  
  if(timeout){
    clearTimeout(timeout);
  }else{
    dropZone.addClass('in');
  }
  var hoverDropZone = $(e.target).closest(dropZone);
  dropZone.toggleClass('hover',hoveredDropZone.length);
  window.dropZoneTimeout = setTimeout(function(){
    window.dropZoneTimeout = null;
    dropZone.removeClass('in hover');
  }, 100);
});

~~~

