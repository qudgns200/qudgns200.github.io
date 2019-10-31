---
layout: post
title:  TIL(20191030)_Spring_board
category: TIL 
description: 
---

TIL(20191030) <span class="red">Spring_board</span>
<br>

Spring으로 게사판 작성 중...!!
  1. 진행 중 에러<br>
  <span class="blue">com.mysql.cj.exceptions.InvalidConnectionAttributeException</span> 발생<br>
  ※ 해결방안 : DB url 수정<br>
      ex) jdbc:mysql://localhost/company -> <br>
          jdbc:mysql://localhost/company?<span class="red">characterEncoding=UTF-8&amp;serverTimezone=UTC</span><br>
      <br>
  <span class="blue">Parameter Maps collection does not contain value for ~</span> 발생<br>
  ※ 나의 경우... parameterType을 parameterMap으로 잘못 작성하여 에러 발생
    
<br>

