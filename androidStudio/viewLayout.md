### 뷰를 배치하는 레이아웃

#### 1. 선형으로 배치 - LinearLayout

● LinearLayout은 버티컬이나 호리즌탈을 사용하여 수직이나 평행하게 배치한다.  

● LinearLayout의 중첩을 통해 복잡한 화면을 만들 수 있다.  

● layout_weight 값을 설정해 주면 가중치에 따라 버튼이 화면에 차게 설정할 수 있다.  

● 그래비티, 레이아웃_그래비티  
![Image From 07_뷰를 배치하는 레이아웃](https://user-images.githubusercontent.com/102038962/217477026-b531cbb3-110f-4347-b337-e72adf9f604d.png)  
![3](https://user-images.githubusercontent.com/102038962/217477109-2cfa68aa-0842-4089-82eb-16305f6e6415.png)

#### 2. 상대 위치로 배치 - RelativeLayout 
![ㅓ](https://user-images.githubusercontent.com/102038962/217480264-56fe5e84-38d4-47ea-a3f9-2d545f466f24.png)

![Image From 07_2뷰를 배치하는 레이아웃](https://user-images.githubusercontent.com/102038962/217477181-8ce58d2f-624c-4fd4-9a34-021562d4948b.png)

![Image From 07_뷰d를 배치하는 레이아웃](https://user-images.githubusercontent.com/102038962/217477233-faa7d689-6187-4079-8c08-290934aa961f.png)

![Image From 07_d뷰를 배치하는 레이아웃](https://user-images.githubusercontent.com/102038962/217477288-646b0145-9369-4a80-a2f4-c4942cb62378.png)

#### 3. 겹처서 배치 - FrameLayout  

● 단순히 겹쳐서 출력하는 레이아웃이므로 특별한 속성이 없다. 

● 여러 뷰를 겹쳐 놓고 어떤 순간에 하나의 뷰만 출력할 때 사용는데, 대부분의 뷰를 표시 여부를 설정하는 visivility 속성을 함께 사용한다.

![Image From 07_뷰를 배치하는 레이아웃](https://user-images.githubusercontent.com/102038962/217477411-82382e61-a760-4ca9-90e9-a2ed8ef0ac68.png)

#### 4. 표 형태로 배치 - GridLayout

● LinearLayout 처럼 orientation과 다르게 줄바꿈 자동으로 해준다.

● Orientation : 방향 설정

● rowCount : 세로로 나열할 뷰 개수

● columnCount : 가로로 나열할 뷰 개수

● layout_row : 뷰가 위치하는 세로 방향 인덱스

● Layout_column : 뷰가 위치하는 가로 방향 인덱스

![d](https://user-images.githubusercontent.com/102038962/217477643-a1222dd2-8ee3-4d16-9d03-547a619b521c.png)

● layout_gravity=“fill_horizontal” 으로 특정뷰를 확장 출력.

![df](https://user-images.githubusercontent.com/102038962/217477713-0e398cdd-b06a-494c-857b-918b4a0cdea8.png)

![asdf](https://user-images.githubusercontent.com/102038962/217477742-bd8b2c95-0ca0-4478-8f09-4066b436b637.png)

● 열이나 행 병합하기
– 어떤 뷰가 테이블 여러 칸을 차지하게 설정 

● layout_columnSpan : 가로로 열 병합 

● layout_rowSpan : 세로로 행 병합

![asdfd](https://user-images.githubusercontent.com/102038962/217477805-1cfe96fe-6e86-419b-975d-a503a9eeeb55.png)

#### 5. 계층 구조로 배치 - ConstraintLayout 
● 레이아웃 편집기로 하는게 나음

*********************************
1. LinearLayout은 뷰를 가로나 세로 방향으로 배치하는 레이아웃.

2. RelativeLayout은 뷰를 다른 뷰의 상대 위치에 맞춰 배치하는 레이아웃.

3. FrameLayout은 뷰를 같은 위치에 겹쳐서 배치하는 레이아웃.

4. GridLayout은 뷰를 행과 열이 있는 테이블 구조로 배치하는 레이아웃.

5. ConstraintLayout은 레이아웃 편집기를 이용해 화면을 구성하는 레이아웃.




