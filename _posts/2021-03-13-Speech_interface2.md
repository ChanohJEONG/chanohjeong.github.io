---
layout: post
title:  "음성 인터페이스"
date:   2021-03-13
excerpt: "음성 인터페이스 수업(2)"
tag:
- jekyll 
- moon
- blog
- about
- theme
#feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---

# 음성 인터페이스(2)

#### Speech Signal Characteristics

- Speech Production Model

---

#### Speech Communication & Interface

- 음성 생성 및 마이크 입력 과정

  - Speech Production

  - Natural Speech

    1. Signal Analysis : **Analysis/Synthesis**
       * *Voice Transformation*
    2. Speech compression : **Voice storage** 
       * *Wired / Wireless Transmission*
    3. Human-Computer Interface : **Speech/Speaker recognition** 
       - *Text-to-speech*
       - *Emotion technology*

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-1.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-1.PNG" width="50" height="30"></a>
</figure>

- 음성 출력 및 듣는 과정

  - Speech Acquistion
    - Speech Signal Processing
  - Recognition / Discrimination

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-2.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-2.PNG" width="50" height="30"></a>
</figure>

  ----

  #### Voice Communication

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-3.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-3.PNG" width="50" height="30"></a>
</figure>

#### Human Computer Interface

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-4.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-4.PNG" width="50" height="30"></a>
</figure>

---

#### Speech Production Model

- Human speech production mechanism

##### (1) *Anatomy of Speech Production*

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-5.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-5.PNG" width="50" height="30"></a>
</figure>

- Larynx(후두)

  - Control vocal cords/folds(성대)
  - Consists of cartilage(연골),muscles,ligaments(인대)
  - 성대안의 있는 근육과 근처에 있는 연골에 의해서 Tension이 결정 된다.

- Stages of vocal folds

  - Breating, voiced, unvoiced

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-6.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-6.PNG" width="50" height="30"></a>
</figure>

##### (2) *Dynamics of Vocal Folds*

- 성대는 빠르게 열고 닫힘 : Open/Close/return phase

- Pitch period

  - Duration of one glottal Cycle  ( 1개의 성문주기 지속성)
  - Fundamental frequency = 1/pitch
    - 60 ~ 400 Hz

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-7.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-7.PNG" width="50" height="30"></a>
</figure>

- Harmonics

  - Fourier transfrorm of the periodic glottal waveform 

    : 주기적인 성문 진동형태의 푸리에 변환

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-8.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-8.PNG" width="50" height="30"></a>
</figure>

##### (3) *Vocal Tract*

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-9.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-9.PNG" width="50" height="30"></a>
</figure>

- Definition of Vocal Tract : Oral cavity from the larynx to the lips & the nasal passage

  후두에서 입술과 비강까지의 구간

- Role : Spectrally color the souce

  음성 소스에 스펙트럼으로 색상 지정

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-10.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-10.PNG" width="50" height="30"></a>
</figure>

- Formant(형성)

  - Resonance frequencies of the vocal tract : 성대의 공명 주파수
  - Poles of all-pole inear system : 선형시스템 막대그래프 중 모든 항목들
  - Bandwidth and amplitude varies by phonemes and speaking style : 대역폭과 진폭은 현상과 말하는 스타일에 따라 다양하게 형성됨
  - Vocal Tract length up -> formant frequency down : 성대가 길어지는건 주파수가 낮아지는것

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-11.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-11.PNG" width="50" height="30"></a>
</figure>

---

### Magnitude Spectrum of Speech in dB Scale

<figure>
    <a href="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-12.PNG"><img src="{{ site.url }}/assets/img/AI_Class/Speech_Interface/2-12.PNG" width="50" height="30"></a>
</figure>

 카페 마감으로 다음 이시간에..