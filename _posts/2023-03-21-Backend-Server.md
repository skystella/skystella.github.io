---
title: 뒤끝서버 정리노트
author: cotes
date: 2023-03-21 19:46:00 +9
categories: [Summary Note]
tags: [summary note, backend-server]
pin: false
---


# 뒤끝서버

### - Param
Param : 뒤끝 서버와 통신을 할 때 넘겨주는 파라미터 클래스
<br/>

| 메소드 | 리턴 값 | 설명 |
| ----- | ------- | ---- |
| Add | void | Param에 데이터를 추가합니다. |
| AddCalculation | void | Param에 연산을 위한 데이터를 추가합니다. |
| Parse | Param | json 형태의 데이터 혹은 클래스를 Param으로 변환합니다. |
| Clear | void | Param에 추가되어 있는 데이터를 초기화 합니다. |
| Clone | Param | Param을 복사합니다. |
| GetJson | string | Param에 저장된 데이터를 Json 형태로 리턴합니다. |
| GetValue | SortedList | Param에 저장된 SortedList를 리턴합니다. |

**- Clear()**
Param에 저장된 데이터를 초기화합니다.
<br/>

```C#
Param param = new Param();
''''
param.clear();
```
<br/>

**- Clone()**
Param을 복사합니다.
```C#
Param copyParam = param.Clone();
```
<br/>

**- GetJson()**
Param에 저장된 데이터를 Json 형태의 Stirng으로 리턴합니다.
```C#
Param param = new Param();
''''
var json = param.GetJson();
```
<br/>

**- GetValue()**
Param에 저장된 데이터를 리턴합니다.
```C#
Param param = new Param();
''''
var sList = param.GetValue();
```
<br/>

**- Add()**
Param에 컬럼을 추가합니다.

파라미터
| Value | Type | Description |
| ----- | ------- | ---- |
| key | string | Add할 컬럼의 key 값입니다. |
| value | T | Add할 컬럼의 value값입니다. |

```C#
Param param = new Param();
param.Add("hp", 512);
```
<br/>

**- AddNull()**
Param에 빈 컬럼을 추가합니다.

파라미터
| Value | Type | Description |
| ----- | ------- | ---- |
| key | string | 키값 |

```C#
Param param = new Param();
param.AddNull(string key);
```
<br/>

**- Parse()**
Param에 컬럼을 추가합니다.

파라미터
| 변수명 | 자료형 | 설명 |
| ----- | ------- | ---- |
| jsonString | string | json 형태로 저장된 string 데이터를 Param 형태로 변환합니다. |
| jsonData | JsonData | jsonData 데이터를 Param 형태로 변환합니다. |
| value | T | 개발자가 선언한 클래스를 Param 형태로 변환 합니다. |

```C#
JsonData json = new JsonData();
''''
Param param = Param.Parse(json);
```
<br/>

### BackendReturnObject 메소드 리스트
<br/>

| 메소드 | 리턴 값 | 설명 |
| ----- | ------- | ---- |
| GetStatusCode() | string | statusCode 값 받아오기 |
| GetErrorCode() | string | errorCode 값 받아오기 |
| GetMessage() | string | message 값 받아오기 |
| HasReturnValue() | bool | returnValue가 존재하는지 확인 |
| GetReturnValue() | string | returnValue 값 받아오기 |
| GetReturnValuetoJSON() | JsonData | returnValue 값을 JsonData로 변환하여 받아오기 |
| ToString() | string | statusCode, errorCode, message, returnValue가 존재하는 경우, 해당 내용을 모두 string형태로 반환 |
| HasRows() | bool | returnValue에 rows 존재 여부 확인 |
| Rows() | JsonData | returnValue 내부에 rows를 JsonData로 변환하여 반환 |
| HasInDate() | bool | returnValue에 inDate 존재 여부 확인 |
| GetInDate() | string | returnValue 내부에 inDate를 반환 |
| HasFirstKey() | bool | returnValue에 firstKey 존재 여부 확인 |
| FirstKey() | JsonData | returnValue 내부에 firstKey를 JsonData로 변환하여 반환 |
| FirstKeyString() | string | returnValue 내부에 firstKey를 String으로 변환하여 반환 |
| JsonDataContaionsKey <br/> (JsonData data, string key) | bool | data 내에 key가 존재하는지 확인하여 반환 |
| IsSuccess() | bool | 요청이 성공했는지 실패했는지 확인<br/> (성공: 200번대 statusCode, 실패: 300 이상의 statusCode) |
| IsServerError() | bool | 리턴 statusCode가 서버 에러(500번대)인지 판별하여 반환 |
| LastEvaluatedKeyString () | string | returnValue 내부에 LastEvaluatedKey를 <br/> String으로 변환하여 반환 (notice/event offset으로 사용) |
| Flatten (JsonData jsonData) | JsonData | JsonData 내 존재하는 자료형을 언마샬하여 반환 |
| GetFlattenJSON () | JsonData | GetReturnValuetoJSON()의 리턴 값에 포함하고 있는 자료형을 언마샬하여 반환 |
| FlattenRows() | JsonData | Rows()의 리턴 값에 포함하고 있는 자료형을 언마샬하여 반환 |
