---
title: 오류 오답노트
author: cotes
date: 2023-04-12 12:03:00 +9
categories: [Summary Note]
tags: [summary note, error note, error]
pin: false
---

### 뒤끝서버
오류 : Initialize err: statusCode : 400
    errorCode : HttpRequestException

   초기화 실패 : statusCode : 400
   errorCode : HttpRequestException

: 네트워크(와이파이) 연결로 해결
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
오류 : NullReferenceException: Object reference not set to an instance of an object. LaneGame.BackendLogin.CustomSignUp (System.String id, System.String pw) (at Assets/Scripts/BackEnd/BackendLogin.cs:49)

오류 코드 : BackendLogin.Instance.CustomSignUp(inputTextId, inputTextPw);

원인 : 뒤끝을 초기화하지않고 뒤끝(메소드)을 불러오면서 생긴 오류

해결방법 : 뒤끝(메소드)을 불러오기전 뒤끝을 초기화 함으로써 (var vro = Backend.Initialize(true); ) 문제해결

![image](https://user-images.githubusercontent.com/124504898/231338823-a58d3f8d-3ab9-417a-b688-53b4f429a205.png)*수정 전(InputField.cs)*

![image](https://user-images.githubusercontent.com/124504898/231338989-9f09fb49-4353-4dba-b14c-8381f113c43d.png)*수정 전(BackendLogin.cs)*

![image](https://user-images.githubusercontent.com/124504898/231347012-48fb47fc-9c5b-4b31-97c3-1cbf4b40e788.png)*수정 후(BackendLogin.cs)*
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
오류 : NullReferenceException: Object reference not set to an instance of an object. LaneGame.InputField.OnLogin () (at Assets/Scripts/RunGame/UI/InputField.cs:38)

오류 코드 : BackendLogin.Login.CustomLogin();

원인 : BackendLogin()클래스의 새로운 인스턴스를 생성해야하는데 새로운 인스턴스를 생성하지않고 클래스를 호출했기때문에 null에러 발생

해결방법 : 인스턴스가 null이라면 새로운 인스턴스를 생성하고 최종적으로 인스턴스를 return해주는 Instance라는 싱글톤패턴을 생성해줌으로써 문제해결

![image](https://user-images.githubusercontent.com/124504898/231348897-fcb5cda0-7468-49e6-b444-388523bb4941.png)*수정 전(InputField.cs)*

![image](https://user-images.githubusercontent.com/124504898/231348377-5efbcb16-36f4-4085-be00-41ee031fba50.png)*수정 전(BackendLogin.cs)*

![image](https://user-images.githubusercontent.com/124504898/231348749-751bfd60-edd1-4e88-b9e3-450e01a733f4.png)*수정 후(BackendLogin.cs)*

![image](https://user-images.githubusercontent.com/124504898/231348533-d1d2cce5-dc11-4d54-ba7e-eae16ce4cbfd.png)*수정 후(InputField.cs)*