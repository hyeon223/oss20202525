### 오픈소스sw개론 과제1

---
### **getopt**

1) 용도
 
명령행 플래그와 매개변수의 구문을 분석함

2)

---
### **getopts**

1) 용도

---
### **sed**

1) 용도 

원본텍스트 파일을 편집함

#vi 에디터와 다른 점 

|vi 에디터| sed|
|---|---|
|실시간으로 편집됨|실시간의 편집이 아닌 명령어의 형태로 편집됨|
|원본파일 편집후에 저장하므로 원본파일이 변경됨|원본 파일을 건드리지 않고 편집하므로 기본적으로는 원본파일에 영향을 주지 않음(단, sed의 옵션으로 -i 지정시에는 원본 변경됨)|


2) 명령어 기본형식과 옵션

`sed 'command' FILE`

- OPTION

-e : 출력되는 값을 보여줌(기본값으로 되어있지만 다중 명령어 쓸 때에는 반드시 써야함)

-f : 스크립트를 파일로부터 읽어 명령어를 지정

-i : 출력은 하지 않지만 변경된 값을 원본파일에 저장

-n : 특정 값이 들어간 줄만 출력, 주로 p명령어와 사용됨


3) 명령어 사용 예제


|sed 명령어 사용예제|설명|
|-----|-----|

---
### **awk**

1) 용도

지정된 파일로부터 데이터를 분류하여, 분류된 텍스트 데이터를 바탕으로 패턴 매칭 여부를 검사하거나 
데이터 조작 및 연산 등의 액션을 수행하고, 결과를 출력하는 기능을 수행함 

2) 명령어 기본형식과 옵션

`awk [OPTION] 'pattern{action}' [ARGUMENT]`

- OPTION

-F : 필드 구분문자 지정

-f : awk program 파일의 경로 지정

-v : awo program에서 사용될 특정 variavle 값 지정

- pattern과 action 모두 생략 가능

```
//pattern 생략: 매칭여부를 검사할 문자열 패턴정보가 없으므로 모든 레코드 선택
$ awk '{print}' FILE   //파일의 모든 레코드 출력

//action 생략: 기본 action인 print가 실행됨
$ awk '/p/' FILE     //파일에서 p를 포함하는 레코드 출력
```
 
3)명령어 사용 예제


|awk 명령어 사용예제|설명|
|--------|----------|
|awk '{print}' FILE| 파일의 전체 내용 출력|
|awk '{print $n} FILE|파일의 특정한 필드값 출력,n번째 필드를 출력함|
|awk '{print "문자열"$필드값}' FILE|특정 필드에 문자열 추가해서 출력|
|awk '{print} FILE|패턴이 포함된 레코드 출력|
|awk '{print} FILE|특정필드에 연산 수행결과 출력|
|awk '{print}' FILE|필드 값 비교에 따라 레코드 출력|
 
---
