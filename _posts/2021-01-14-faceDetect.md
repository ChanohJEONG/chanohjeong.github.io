---
layout: post
title:  "얼굴인식기반 전자출결 시스템"
date:   2021-01-14
excerpt: "OpenCV를 활용한 얼굴인식 프로젝트"
project: true
tag:
- jekyll 
- moon
- blog
- about
- theme
#feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---


## 위치 및 얼굴인식기반 전자출결시스템

<figure class="half">
	<a href="{{ site.url }}/assets/img/portfolio/facedetect1.png"><img src="{{ site.url }}/assets/img/portfolio/facedetect1.png"></a>
	<a href="{{ site.url }}/assets/img/portfolio/facedetect2.png"><img src="{{ site.url }}/assets/img/portfolio/facedetect1.png"></a>
</figure>


* skill : C, C++, OpenCV, Arduino, Andorid Studio, PHP
* url : <a href=""> Demo </a>

```html
핸드폰 앱을 통한 전자출결 시스템입니다.
BLE 모듈 근처에서 출결이 가능하며 출석 요청 시 얼굴인식을 통해 인증합니다.
얼굴 검출은 OpenCV를 활용했으며, GrayScaling, Oval처리 등 
데이터 전처리 과정은 C와 C++를 통해 직접 Image processing을 했습니다.
이후 PCA 기법을 활용한 차원축소를 통해 Modeling을 구현하였으며
최종적으로 약 95% 인식률을 달성하였습니다.
관리자 페이지 및 데이터 처리는 PHP를 통해 구현하였으며, 모바일 앱은 Android studio를 활용했습니다.
```

