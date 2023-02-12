### 09 리소스활용하기

1. 리소스의 종류와 특징

● 리소스란 정적인 자원이고 크게 앱 리소스와 플랫폼 리소스로 구분.

● 앱 리소스 사용하기

- 앱 리소스란 개발자가 직접 추가한 리소스를 의미, 모듈을 만들면 네개의 디렉터리가 생기며 이 디렉터리에 리소스 파일을 각각 만든다.

- 앱의 리소스 종류

![3](https://user-images.githubusercontent.com/102038962/218295420-19037f18-c9d8-4c40-884e-0a9fe3e3a208.png)

![2](https://user-images.githubusercontent.com/102038962/218295425-b0094bf7-8a5e-4cab-866e-7c1af2d3f91f.png)

– 리소스 디렉터리는 임의로 이름을 정할 수 없다. 

– values에 추가하는 파일은 대문자 사용 못 한다.

– R 파일에 식별자로 등록해서 이용하기 때문

– 레이아웃 리소스 -> layout 디렉터리 : 레이아웃 XML 파일 저장

– 이미지 리소스 -> drawable 디렉터리 : PNG, JPG, GIF, PNG 파일을 저장할 수 있고 XML로 작성한 이미지도 저장 가능하다.

![1](https://user-images.githubusercontent.com/102038962/218295460-4a75f9ae-be92-4be2-823e-42ad5f9aee24.png)

– 실행 아이콘 리소스 -> mipmap 디렉터리 : 앱을 기기에 설치하면 나타나는 실행 아이콘의 이미지 리소스가 저장되는 디렉터리

– 값 리소스 -> values 디렉터리 : 문자열, 색상, 크기, 스타일, 배열 등 값을 XML로 저장할 수 있다. 여기에 저장되는   

리소스는 다른 디렉터와 다르게 파일명이 R인 파일에 식별자로 추가되므로 코드에서 이 식별자로 구분해서 사용하지않고 리소스 파일에 값을 지정한 태그의 name 속성값이 등록된다. 

따라서 그림에서 values 디렉터리에 있는 colors.xml, strings.xml 등의 파일명을 권장할 뿐 개발자가 자유롭게 정할 수 있으며 알파벳 대문자를 이용할 수도 있다. _237p

– 색상 리소스 -> color 디렉터리 : values 디렉터리에 <color> 태그로 등록한 리소스는 말 그대로 색상 하나를 리소스에 등록해 사용하겠다는 의미이지만 color 디렉터리의 
  
리소스는 특정 뷰 상태를 표현하고 그 상태에 적용되는 색상을 등록할 때 사용한다 예로 두개의 상태를 하나의 XML에 등록해 적용하면 편하다.

– 글꼴 리소스 -> font 디렉터리 : TTF 나 OTF 파일 저장 후 이용.
  
● 플랫폼 리소스 활용하기
  
– 안드로이드 플랫폼이 제공하는 많은 리소스를 활용한다

![4](https://user-images.githubusercontent.com/102038962/218295476-9922d1d9-3290-470b-8a91-10b58132735e.png)

![5](https://user-images.githubusercontent.com/102038962/218295487-ad92b79a-2a87-455b-8830-1305c2e465c8.png)


2. 리소스 조건 설정 
  
● 리소스 조건 설정이란?
  
어떤 리소스를 특정 환경에서만 적용되도록 설정하는 것을 말한다.  
  
![6](https://user-images.githubusercontent.com/102038962/218295508-5caa1fec-43f9-4699-91e8-a0d14e526ef2.png)


![7](https://user-images.githubusercontent.com/102038962/218295710-b4bdce51-4fee-4ca3-bc01-706d37a2e7c7.png)


![8](https://user-images.githubusercontent.com/102038962/218295741-bb2f5f5d-8e39-4cc0-bc5d-7ce83ab0ca3d.png)

  
![43](https://user-images.githubusercontent.com/102038962/218295756-478efd9b-9191-4177-a7f7-cd5a8a83c1ff.png)
  
● 화면 회전에 대응하기
  
가로와 세로 방향일 때 출력할 레이아웃 XML 파일을 각각 준비해야 하는데 어느 방향에서 어떤 XML 파일을 출력할 지를 지정해야 한다. 
  
코드로 할 수 있지만 리소스 조건으로 하면 편리하다. 우선 레이아웃 XML 파일을 2개 만드는데 이름을 같게한다.
  
![r](https://user-images.githubusercontent.com/102038962/218295770-d18c0ea9-d9ab-4378-8123-04d26717f423.png)

![rr](https://user-images.githubusercontent.com/102038962/218295784-ceabd09d-8273-40c8-9546-991160226b69.png)

● 국제 언어 제공하기
  
Strings.xml 파일에 <string> 태그로 문자열 리소스를 작성하는데 이 파일을 여러게 만들어 각 언어에 맞는 리소스 

문자열을 담고 어느 XML 파일을 적용해야 하는지를 리소스 디렉터리명으로 지정하면 된다.

![4r4r](https://user-images.githubusercontent.com/102038962/218298334-7ef45623-dccb-4508-926f-628832441d9b.png)

3. 폰 크기의 호환성
  
안드로이드 시스템에서 도와주는 부분이 있고 개발자가 직접 코드에서 해결해야 하는 부분이 있다.
  
● 논리적인 단위 알아보기
  
dpi는 dots per inch의 준말 1인치 안에 있는 도트의 개수

![ee](https://user-images.githubusercontent.com/102038962/218298343-4adc3eb5-7bb4-4d27-94a5-d749c6d43c0d.png)

이 때 도움을 받으려면 개발자가 콘텐트의 크기를 지정할 때 논리적인 단위를 사용해야 하는데 물리적인 단위로 지정하면 시스템의 도움을 받을 수 없다.
  
 * 크기 지정에 사용할 수 있는 단위
  
 - dp(dip: density-independent pixels): 스크린의 물리적 밀도에 기반에 둔 단위
  
 - sp(sip: scale-independent pixels): dp와 유사하며 글꼴 크기에 적용
  
 - pt(points): 스크린의 크기의 1/72을 1pt로 함 
  
 - px: 픽셀
  
 - mm: 밀리미터 
  
 - in: 인치
  
dp와 sp로 크기를 지정하길 권함.  

![ㄷㄷㄱ](https://user-images.githubusercontent.com/102038962/218295874-c54e5068-2998-4b82-b585-fafecd17bb3f.png)

![ㅈㄷㅈㄷ](https://user-images.githubusercontent.com/102038962/218295882-5960666a-4ae0-4bce-9a3a-51ddf8b72de7.png)

![ㅈㄷㅈㄷㅈㄷ](https://user-images.githubusercontent.com/102038962/218295890-d9cedabf-96d7-4389-a18a-f948e76b153d.png)
  
---
  
● 정리
  
1. 안드로이드에서 제공하는 리소스에는 anim, animator, layout, drawable, mipmap, menu, raw, xml, color, font 등이 있다.
  
2. 리소스는 res 디렉터리의 하위 디렉터리에 위치하며 지정된 디렉터리명을 이용해야 한다.
  
3. Values 디렉터리의 리소스들은 파일명으로 식별되지 않고 파일의 태그에 등록한 name 속성값으로 식별된다.
  
4. 리소스 디렉터리명에 붙임표(-)를 추가해 디렉터리의 리소스를 어떤 환경에서 이용해야 하는지 조건을 명시할 수 있다.
  
5. dp, sp 등의 논리적인 단위를 이용하면 시스템에서 크기를 늘리거나 줄인다.

