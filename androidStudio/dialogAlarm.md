## 10 다이얼로그와알림이용하기

#### 1. API 레벨 호환성 고려하기

targetSdkVersion : sdk 사용 버전minSdkVersion : 최소 sdk 버전이다.

여기서 후자보다 높은 버전의 함수를 쓰려면 애너테이션(annotation)을 추가해 오류를 해결할 수 있다.

![12](https://user-images.githubusercontent.com/102038962/218458922-871b9194-e331-47ab-b8bf-2a2582306b7d.png)

하지만 이는 오류를 무시하는 설정이고 API 레벨 호환성 문제를 막으려면 직접 코드로 처리해야 한다. 

예로 addCallback() 함수는 다음과 같이 R 버전에서만 실행되게 할 수 있다.

![ddf](https://user-images.githubusercontent.com/102038962/218459006-c4082390-a00b-4a23-b8cc-398694068e71.png)

#### 2. 퍼미션 설정하기

특정 기능에 대한 접근 권한을 말한다.

다른 앱에서 내가 만든 기능을 사용할 수 없도록 보호하고 권한을 얻은 앱에서만 허용하고 싶을 때 퍼미션을 설정한다.

● 퍼미션 설정과 사용 설정

 - <permission> : 기능을 보호하려는 앱의 매니페스트 파일에 설정한다.
 
 - <uses-permission> : 퍼미션으로 보호된 기능을 사용하려는 앱의 매니페스트 파일에 설정한다.

![dd](https://user-images.githubusercontent.com/102038962/218459085-d01ed38c-0804-435f-b4dd-0de870297e7f.png)

![sdsd](https://user-images.githubusercontent.com/102038962/218459117-1e4e1b5a-310c-480d-a259-50bb381aabad.png)

![sddsd](https://user-images.githubusercontent.com/102038962/218459160-9695dbf8-dd76-492f-a923-cfeb6524e123.png)

![sd](https://user-images.githubusercontent.com/102038962/218459192-16a1c524-8f7a-4a6c-b87e-99ced8fcd19b.png)

![dddd](https://user-images.githubusercontent.com/102038962/218459234-1533dfeb-a204-4471-9d15-a0758976ed62.png)

● 퍼미션 허용 확인

API 레벨이 23 이후부터는 퍼미션 신고제가 아닌 허가제로 바뀌어서 사용자가 거부할 수 있게 되었다.
 
그래서 <uses-permission>을 선언하지 않은 것과 같아 허용하지 않았을 때도 생각을 해줘야한다.

![dddddd](https://user-images.githubusercontent.com/102038962/218459308-ed049864-ad8b-4465-9bff-0aec1eecb260.png)

![sdsddd](https://user-images.githubusercontent.com/102038962/218459331-4275e949-51bc-4272-a115-81be06853004.png)

![c](https://user-images.githubusercontent.com/102038962/218459374-7816d797-ebf9-437f-933e-622123f18549.png)

![ddss](https://user-images.githubusercontent.com/102038962/218459398-29dd1c24-3709-49da-a6ec-2f7c1cdaf651.png)

![dx](https://user-images.githubusercontent.com/102038962/218459429-e090fb62-afd5-4af3-9bf5-c542e3636032.png)

3. 다양한 다이얼로그

다이얼로그란 사용자와 상호 작용하는 대화상자이다. 

● 토스트 메시지 띄우기
 
토스트는 화면 아래쪽에 잠깐 보였다가 사라지는 문자열을 의미한다.
 
“종료 하려면 한 번 더 누르세요”를 띄우는 것 처럼

![ddssx](https://user-images.githubusercontent.com/102038962/218459499-61f509c5-2230-479d-a383-8de735ea0ada.png)

 - val LENGTH_LONG: Int 
 
 - val LENGTH_SHORT: Int

![qw](https://user-images.githubusercontent.com/102038962/218459557-b9579507-8722-4e82-8dbc-6f331a83cf9e.png)

● 날짜 또는 시간 입력받기
앱에서 사용자에게 날짜나 시간을 입력받는 데 사용하는 다이얼로그를 피커(picker) 다이얼로그라고 한다.
 
데이트 피커 : 날짜 입력 
 
타임 피커 : 시간 입력

![rr](https://user-images.githubusercontent.com/102038962/218459608-e66097b6-d717-4c27-8ded-a96cf1b0549b.png)

*보이는 리스너 부분을 구현 객체에 등록하면 다이얼로그에서 사용자가 설정한 날짜를 콜백 함수로 얻을 수 있다.

![dxx](https://user-images.githubusercontent.com/102038962/218459667-ddb6e655-7fac-49cf-bea4-e5cfa4f6b6d3.png)

![xxx](https://user-images.githubusercontent.com/102038962/218459701-9d88ff76-cbb7-453c-b32f-c78208fb5911.png)

![ww](https://user-images.githubusercontent.com/102038962/218459720-5ed13a4f-617e-4fa3-a9a5-86cba1c2b738.png)

● 알림 창 띄우기 
 
AlertDialog : 기본 알림 창

![wewe](https://user-images.githubusercontent.com/102038962/218459787-5d88986f-48e9-4100-aae3-147ec36394b7.png)

![rrwwr](https://user-images.githubusercontent.com/102038962/218459822-2cb8fea8-7b85-450a-b9d1-aeb98e1bff0c.png)

![ㅅㄱㄱㅅ](https://user-images.githubusercontent.com/102038962/218460002-1a741d7b-a1e0-4c9b-a223-f30df0ca7a64.png)

![ㅇㅇㅇ](https://user-images.githubusercontent.com/102038962/218460048-cce946ea-6c50-4013-a649-0512f894edd7.png)

![ㅌㅌ](https://user-images.githubusercontent.com/102038962/218460169-1288a3ba-0b59-4085-bb3e-b6cd3fcf7ef1.png)

● 커스텀 다이얼로그 만들기 
 
– AlertDialog 이용한다.
 
– 사용하려면 LayoutInflater라는 클래스를 이해해야 한다. 
 
– LayoutInflater 클래스는 레이아웃 XML 파일을 코드에서 초기화(전개)하는 기능을 제공한다.
 
– 초기화란 XML 파일에 선언한 뷰를 코드에서 이용하고자 생성하는 작업을 의미.
 
– XML파일은 텍스트 파일일 뿐, 결국 코드에서 이용하려면 XML에 선언한 대로 객체 생성후 메모리에 할당해야하고 이것을 LayoutInflater가 해준다.

![ㅇㅇㅇㄴ](https://user-images.githubusercontent.com/102038962/218460271-348ea05b-8a4a-471c-8393-8f74eee0fdc3.png)

![ㅊㅊㅌ](https://user-images.githubusercontent.com/102038962/218460298-093bbd1a-419a-4e3d-a7d0-48b2f99a7261.png)

![ㅍㅊㅍ](https://user-images.githubusercontent.com/102038962/218460380-127bb6f3-fc09-4540-98ce-270d4e208aa4.png)

4. 소리와 진동 알림 
 
● 소리 알림
 
– 시스템에 등록된 소리 이용법

![ㅇㅌㅌ](https://user-images.githubusercontent.com/102038962/218460452-b7eb33fe-d678-45bd-ab50-db727401ac9d.png)

– 다른 음원 사용법
 
음원 파일을 리소스에 등록해서 이용해야 하는데 음원 리소스 디렉터리는 res/raw이며, 음원을 재생하는 클래스는 MediPlayer이다.
  
![ㅊㅌㅌㅌ](https://user-images.githubusercontent.com/102038962/218460597-3f807d20-b79b-40f5-b1f8-bbf09bd6147d.png)

● 진동 알림
  
![ㅊㅊㅌㅌㅌ](https://user-images.githubusercontent.com/102038962/218460714-6dfa4125-9c6d-470d-b3bc-2e56e9251509.png)
  
![ㅊㅊㅊㅋㅋㅋㅋ](https://user-images.githubusercontent.com/102038962/218460841-b6dfc5d0-e0e1-487d-b4d016b9fbe05136.png)

![ㅎㅎ](https://user-images.githubusercontent.com/102038962/218460898-6ddc6a2b-c971-4c21-b561-090c4baee306.png)

![ㅊㅊㅌㅋ](https://user-images.githubusercontent.com/102038962/218460967-15ebeab2-46fa-4993-8fe9-4015b56cf790.png)

![ㅗㅗ](https://user-images.githubusercontent.com/102038962/218461008-6baad551-e71c-44d1-9bd5-8d0b5b1c2bd7.png)

  
#### 5. 알림 띄우기 
 
● 알림 채널
 
– 상태 바에 앱의 정보를 출력하는 것을 알림(notification)이라고 한다.
 
– 앱에서 시스템에 의뢰하면 시스템에서 관리하는 상태 바에 앱의 알림을 출력할 수 있다.
  
![ㄱㄱㄱㄱㄱㄱ](https://user-images.githubusercontent.com/102038962/218461063-d25f8093-eec2-43cb-8c1f-69ab1d79195e.png)

– 알림(notification) 만드는 법이 매우 길다
    
![ㅁㄴㅇㄹ](https://user-images.githubusercontent.com/102038962/218461138-7d631ec3-9ffa-46bf-a17e-c150289938e1.png)

궁금하면 294p 참고. 
 
● 알림 객체
 
– 알림 빌더를 통해 Notification 객체를 만들어야 한다.
 
– 이 객체에 출력할 이미지, 문자열 등의 정보를 담는다.
 
– 상태바에 이미지가 출력되는 것을 스몰 아이콘이라고 한다. 
 
– 알림은 스몰 아이콘과 발생 시각, 제목, 내용 등으로 구성되는데 이것을 알림 객체에 설정해야 한다.
  
![ㅂㅈㄷㄱ](https://user-images.githubusercontent.com/102038962/218461239-34ec8ce0-a6bb-4044-ac92-220dea73276a.png)

![ㅇㄴㅁ](https://user-images.githubusercontent.com/102038962/218461274-bb751076-9c7d-4e68-bbfe-799f7898e3f5.png)

● 알림 구성
  
– 알림 터치 이벤트
  
![ㅋㅌㅊㅌㅌ](https://user-images.githubusercontent.com/102038962/218461327-a9cdecfd-5c81-4563-8680-428ef873aeec.png)

알림을 터치했을 때 앱의 액티비티 화면을 실행하려면 알림의 터치 이벤트를 구현해야 한다. 
 
알림은 시스템에서 관리하는 상태 바에 출력하는 정보이므로 앱의 터치 이벤트로 처리할 수 없다. 
 
onTouchEvent()로 처리할 수 없으며 사용자가 터치했을 때 실행해야 하는 정보를 Notification 객체에 담아 두고,
 
실제 이벤트가 발생하면 Notification 객체에 등록된 이벤트를 처리내용을 시스템이 실행하는 구조로 처리한다.

사용자가 알림을 터치하면 앱의 액티비티 또는 브로드캐스트 리시버를 실행해야 하는데 이를 실행하려면 인텐트(intent)를 이용해야 한다.
 
인텐트는 간단히 ‘앱의 컴포넌트를 실행하는데 필요한 정보’이다.
 
인텐트는 코드에서 준비하지만 이것으로 실제 컴포넌트 실행하는 시점은 앱에서 정할 수 없다.
 
이를 알림 객체에 담아 이벤트 발생시 실행해 달라고 시스템에 의뢰해야 한다.
 
이것을 Pendingintent 클래스를 이용하는데 컴포넌트별로 실행을 의뢰하는 함수를 제공한다.
  
![ㅇㅇㅁㅁㅁ](https://user-images.githubusercontent.com/102038962/218461430-5d773624-86c6-4ea4-8025-73edf93a7beb.png)

![ㅇㅇㅊㅊㅊ](https://user-images.githubusercontent.com/102038962/218461457-df2ae456-fc19-41a5-b97b-e704f1e834c8.png)

– 액션
이벤트 처리간 목적인 액션은 최대 3개까지 추가 할 수 있다. 
 
사용자가 액션을 터치 할 때 실행할 인텐트 정보를 PendingIntent로 구성해서 등록해야 한다. 

액션을 등록할 때는 addAction() 함수를 이용한다.
  
  
![ㅊㅊㅍㄴㄴ](https://user-images.githubusercontent.com/102038962/218461521-c19cdf99-1f4b-4620-8ca0-1e4c22c3552e.png)

– 원격 입력
 
알림에서 사용자 입력을 직접 받는 기법이다. 
 
원격 입력도 액션의 한 종류이다.
 
따라서 PendingIntent를 사용한다.
 
RemoteInput에 사용자 입력을 받는 정보를 설정한 후 액션에 추가하는 구조이다.
 
– 프로그레스

![ㅇㅇㄴㄴㅋㅋ](https://user-images.githubusercontent.com/102038962/218461604-d1967d96-8c71-49a3-9884-266b91620d13.png)

일의 진행 상황을 프로그레스에 바로 알려준다.

![ㅇㅇㅊㅊㅋ큐ㅠ](https://user-images.githubusercontent.com/102038962/218461667-5802eed3-9f87-4978-9380-59446c4a7283.png)

● 알림 스타일
 
– 큰 이미지 스타일
 
BigPictureStyle : 알림에서 큰 이미지를 출력할 때 사용 ex) 캡쳐
  
  ![ㄹㅁㄹㅁ](https://user-images.githubusercontent.com/102038962/218461784-32f8ede3-2e14-4563-92f2-b4099c1cc480.png)

– 긴 텍스트 스타일
 
BigTextStyle : 내용을 일부 보여준다 ex) 메일
    
![ㅋㅍㅋㅍㅌㅊ](https://user-images.githubusercontent.com/102038962/218461829-8b281b84-75cd-4e89-a331-835142543261.png)

– 상자 스타일
 
InboxStyle : 문자열을 목록으로 출력해 하나의 알림에 문자열을 여러개 나열한다.
  
![ㅋㅍㅋㅍㅌㅊㅌ](https://user-images.githubusercontent.com/102038962/218461877-8829dba0-95c6-4173-bdb9-553791d22273.png)

– 메시지 스타일
 
Message : 여러 사람이 주고받은 메시지를 구분해서 출력
  
![ㅍㅍㅌㅌㅋㅋ](https://user-images.githubusercontent.com/102038962/218461973-a5defb12-2610-446e-8718-779c7b33b183.png)

  
6. 카카오톡 알림 만들기 
 
import androidx.core.app.RemoteInput 이것도 써줘야 했다 remoteInput 하려면..
 
● 정리
1. minSdkVersion보다 상위 버전에서 제공하는 API를 이용한다면 API 레벨 호환성을 고려해서 작성해야 한다.
 
2. <permission>으로 보호받는 기능을 이용하는 앱은 매니페스트파일에 <uses-permission>을 선언해야한다.
 
3. 안드로이드 다이얼로그의 기본은 AlerDialog이며 화면에 문자열 외에 다양한 뷰를 출력할 수 있다.

4. 알림은 Notification 정보이며 기본 정보 이외에 BigTextStyle, BigPictureStyle, InboxStyle, MessageStyle 등의 
   스타일로 구성할 수 있다.
  
  
  
  
  
  
  
  
  



