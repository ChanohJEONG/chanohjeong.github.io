---
layout: post
title:  "음성 인터페이스"
date:   2021-03-02
excerpt: "음성 인터페이스 수업(1)"
tag:
- jekyll 
- moon
- blog
- about
- theme
#feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---

# 음성 인터페이스

##### 1. 과목 개요

- 디지털 신호 처리, 음성 신호 처리
- 딥러닝 기반 음성신호 처리
- 음성 인터페이스 관련
  - 화자 인식
  - 음성 인식
  - Text to speech (TTS) 문자의 음성화
- 선수과목 : Python 언어 
- 과제 20%, Project 50%, 중간고사(Paper) 30%

------

##### 2. 첫 수업 (Digital Signal Processing [DSP])

- DSP 과정
<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/DSP.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/DSP.PNG" width="50" height="30"></a>
</figure>

- A/D conversion
  - Analog 신호를 Digital 신호로 변환 

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/AD_conversion.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/AD_conversion.PNG" width="50" height="30"></a>
</figure>

- D/A conversion

  - Interpolation(보간법) : 새로운 점을 만들기 위해 수많은 점들을 평균화 시키는것. A/D Conversion을 통과하여 생성된 샘플점들을 직선으로 연결하지 않고 고선으로 연결함으로써 본래 신호파형에 대한 변형을 최소화 시키준다.

  - ###### Zero-order hold, Linear, Quadratic, Idel/optimal interpolation

     ##### --> Sampling theorem

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Interpolation.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Interpolation.PNG" width="50" height="30"></a>
</figure>

----

#### Sampling

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Sampling.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Sampling.PNG" width="50" height="30"></a>
</figure>

- sampling interval : 음성 신호값을 추출하는 간격(주기)
- 1/T = Fs : Sampling frequency (주파수)

---

#### Sampling Theorem (표본화 정리)

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Theorem_fucn.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Theorem_fucn.PNG" width="50" height="30"></a>
</figure>

- 표본화 주파수(Sampling frequency)가 신호 대역의 2배이상이면 표본(Sample)로부터 본래 표본을 완전히 재구성 할 수 있다.

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Theorem_fucn2_1.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Theorem_fucn2_1.PNG" width="50" height="30"></a>

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Theorem_fucn2.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Theorem_fucn2.PNG" width="50" height="30"></a>
</figure>

- Aliasing : 표본화 주파수(Sampling frequency)가 신호대역2배보다 작을 경우, 부족한 만큼 고주파 성분끼리의 간섭이 일어나는 현상

---

##### Quantization ( 양자화 )

- 균일/선형 양자화 ( Uniform/Linear Quantization)
  - 양자화 스텝 크기가 균일하며 대표값이 같은 양수,음수의 대칭적 구조
  - PCM(Pulse-code modulation) : 펄스 부호 변조
    : Analog 신호의 Digital 표현으로 신호(Siganl)을 균일한 주기로 표본화(Sampling)한 뒤 디지털 코드로 양자화(Quantization) 처리한다.
  - 3-bit 양자화 예시

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Quantization1.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Quantization1.PNG" width="50" height="30"></a>
</figure>

#####신호가 한곳에 집중되었을 경우 주기적 Sampling은 의미가 없어지는것이 단점 

- 비균일/비선형 양자화 (Non-Uniform)
  - 양자화 스텝 크기가 비균일함
  - 입력 신호 레벨이 작을때는 양자화 계단 간격을 작게!
  - 입력 신호 레벨이 클때는 양자화 계단 간격을 크게하는 방식

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Quantization2.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/Quantization2.PNG" width="50" height="30"></a>
</figure>

추가 내용은 내일....