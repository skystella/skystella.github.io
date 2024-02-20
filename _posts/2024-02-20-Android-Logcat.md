---
title: 이제 유니티에서 안드로이드 빌드하고 바로 로그 확인하세요
author: cotes
date: 2023-04-12 12:03:00 +9
categories: [Blogging]
tags: [blog, build, android]
pin: false
---

유니티 에디터에서는 잘 작동되지만 핸드폰에서 실행시에 튕기거나 게임이 멈추는 경우가 있다. <br/><br/>
유니티 에디터 상에서 로그를 찍어 텍스트로 표시하게 해도되지만 너무 귀찮기도하고 로그를 찍을수 없는 상황도 있다.<br/><br/>
 이럴때 유니티에서 제공하는 logcat을 이용하면 쉽게 확인가능하다. <br/><br/>
 Unity Registry에서 Android Logcat을 검색후 설치한다 <br/><br/>
![image (3)](https://github.com/cotes2020/jekyll-theme-chirpy/assets/124504898/1520c3d2-b5fe-4b6d-b395-5227255e3997)<br/><br/>
유니티 에디터 상단에 Window > Analysis > Android Logcat 로 logcat창을 띄울수있음 <br/><br/>
![image (4)](https://github.com/cotes2020/jekyll-theme-chirpy/assets/124504898/3a7d8763-228e-4d2e-a4d1-966d0daeb6db) <br/> 
<center/> Android Logcat </center> <br/>

이제 노트북에 폰을 연결하면 끝이다. <br/><br/>
연결이 완료되면 하단에 Connected라고 표시되면서 로그가 찍힌다 <br/>
![image (5)](https://github.com/cotes2020/jekyll-theme-chirpy/assets/124504898/5d3f97bc-c326-4e78-a885-b76d52bbee87) <br/><br/>
우리가 원하는건 유니티 로그이기떄문에 상단에 tag를 좌클릭한뒤 유니티만 체크해준다 <br/>
![image (6)](https://github.com/cotes2020/jekyll-theme-chirpy/assets/124504898/a9aa0ad5-e97f-4baa-94d1-01264c74b597) <br/><br/>
로그를 멈추게하고 싶으면 상단에 Disconnect를 클릭하면 멈추고 다시 실행시킬땐 Reconnect를 클릭하면 된다.