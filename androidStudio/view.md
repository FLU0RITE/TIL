### 뷰를 이용한 화면구성

안드로이드 앱의 기본 구조는 컴포넌트를 기반으로 한다.

화면을 출력하는 컴포넌트는 액티비티뿐이다.

화면에 내용을 표시하려면 뷰클래스를 이용해 구성해야 한다. 

문자열은 TextView 클래스를 이용하고 이미지를 출력하려면 ImageView 등의 클래스를 이용한다.  

이런 클래스를 뷰클래스라고 하고 액티비티가 실행되면서 뷰 클래스를 이용해 화면을 구성하고 이를 기기의 화면에 출력한다.  

액티비티에서 뷰로 화면을 구성하는 방법은 2가지 인데, 액티비티 코드로 작성하는 방법과 레이아웃 XML 파일로 작성하는 방법이다.  

#### 뷰클래스

계층 구조로 만들어 이용하는 패턴을 컴포지트 패턴 또는 문서 객체 모델 ( document object model )이라고 한다.  

#### 레이아웃 XML의 뷰를 코드에서 사용하기 
● ID 를 부여한다  
● Android:id=“@+id/text1” 의 형식을 사용한다

<img width="383" alt="스크린샷 2023-02-07 오후 6 17 47" src="https://user-images.githubusercontent.com/102038962/217202902-074a9edd-d59e-45d9-acf7-db4f32e8dfcf.png">

setcontentview()는 화면에 띄우는 함수 findviewbyid()는 R.java 파일의 상수 변수로 객체를 얻을 수 있다.  

![Image From 06_뷰를 이용한 화면 구성](https://user-images.githubusercontent.com/102038962/217203228-bb6bcbe8-5057-423a-a66c-0028e02575b1.png)

#### 뷰의 크기를 지정하는 방법
layout_width, layout_height 로 지정  

![Image From 06_뷰를 이용한 면 구성](https://user-images.githubusercontent.com/102038962/217204864-5256807d-f3f8-419f-9046-93767a33fc7f.png)

#### 뷰의 간격 설정

![4](https://user-images.githubusercontent.com/102038962/217204952-ecc6d1df-e182-4968-9071-fa8e018566e0.png)

![44](https://user-images.githubusercontent.com/102038962/217205027-b5a77bd9-1026-4f4a-a5a1-1794e5c9d7bf.png)

#### 뷰의표시여부설정
Visibility 속성은 뷰가 화면에 출력되어야 하는지 설정 Visible, invisible, gone으로 설정.  
gone 키워드는 아예 자리도 차지하지 않음.  

![33](https://user-images.githubusercontent.com/102038962/217205280-f95234e0-6ae7-4e25-9f56-f6015867cd09.png)

#### 뷰사용법 - 책 06-3 참고

● 액티비티가 실행되어 뷰를 화면에 출력한다.  

● 뷰를 액티비티코드에서 직접 생성하거나 레이아웃 XML에 명시해 화면구성을 해도된다.  

● 화면을 구성하는 뷰 객체들은 계층구조를 이룬다.  

● 뷰의 종류로는 문자열출력을 위한 TextView, 이미지 출력을 위한 ImageView, 사용자 이벤트를 위한 Button, 사용자 글 입력을 위한 EditText 등이 있다.  

● 레이아웃 XML에 등록되어 생성된 뷰 객체를 코드에서 얻으려면 id 속성을 설정해야하며, findViewById() 함수를 이용해 얻어도 되고 뷰 바인딩기법을 이용해도 된다.  






