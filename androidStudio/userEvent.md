### 08 - 사용자이벤트처리하기

#### 1. 터치와 키 이벤트

```kotlin
Override fun onTouchEvent(event: MotionEvent?:): 
Boolean {
  return super.onTouchEvent(event) 
}
```

콜백 함수 onTouchEvent 선언 

#### ● 터치 이벤트 종류

– ACTION_DOWN: 화면을 손가락으로 누른 순간의 이벤트 

– ACTION_UP:화면에서 손가락을 떼는 순간의 이벤트 

– ACTION_MOVE:화면을 손가락으로 누른 채로 이동하는 순간의 이벤트

#### ● 터치 이벤트 발생 좌표 얻기

onTouchEvent() 함수의 매개변수인 MotionEvent 객체로 얻는다.

– x: 이벤트가 발생한 뷰의 X 좌표 

– y: 이벤트가 발생한 뷰의 Y좌표 

– rawX: 화면의 X 좌표 

– rawY: 화면의 Y 좌표

![Image From 08 - 사용자 이벤트 처리하기](https://user-images.githubusercontent.com/102038962/217750257-762aa12a-f34c-4040-b4ed-956ff34b1da5.png)

#### ● 키 이벤트의 콜백 함수

– onKeydDown: 키를 누른 순간의 이벤트 

– onKeyup: 키를 떼는 순간의 이벤트

– onKeyLongPress: 키를 오래 누르는 순간의 이벤트 

#### 2. 뷰 이벤트

#### ● 뷰 이벤트의 처리 구조

뷰 이벤트는 콜백 함수만 선언해서는 처리할 수 없다.

![s](https://user-images.githubusercontent.com/102038962/217750307-c63295d2-847f-4e3f-a9ec-8b1d2e180b24.png)

![d](https://user-images.githubusercontent.com/102038962/217750345-371cc652-6520-443e-b593-e8a9d3d60276.png)
클릭과 롱 클릭 이벤트 처리
![sd](https://user-images.githubusercontent.com/102038962/217750373-51f4cb27-e6e2-42ea-bc1e-b74ed5b6c36f.png)

3. 스톱워치 만들기

● 실수 다량 발생
● 오토 임포트도 안해 놈
● 아이디 입력 실수
● 무언가 틀리면 코드를 잘 봐야 함 

% 정리 %

1. 터치 이벤트의 콜백 함수는 onTouchEvent이다.

2. 키 이벤트의 콜백 함수는 onKeyDown, onKeyUp 등이 있다.

3. 뷰 이벤트는 이벤트 소스와 이벤트 핸들러를 리스너로 연결하여 처리한다.



