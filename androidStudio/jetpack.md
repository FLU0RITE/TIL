## 11 제트팩라이브러리

사용자의 요구에 적절히 대응하려면 다양한 뷰가 필요하다. 

구글에서는 이러한 기능을 제트팩의 androidx라는 라이브러리로 제공한다. 

이제 안드로이드 앱 개발 현장에서 대부분 androidx 라이브러리를 이용해 화면을 구성한다.

#### 1. 제트팩과 Android 소개 

제트팩 : 다양한 라이브러리 모음 

● 플랫폼 API

플랫폼 API는 기본 재료일 뿐 앱을 개발할 때는 더 다양한 기능이나 화면을 구현해야 한다. 

따라서 구글을 2018년 제트팩이라는 라이브러리 모음을 발표했다.

● 제트팩

다양한 라이브러리 모음으로 androidx로 시작하는 패키지명을 사용한다.

![1](https://user-images.githubusercontent.com/102038962/226821898-bc510bc0-0cbd-4ad0-b724-ac6f62b287f6.png)

![2](https://user-images.githubusercontent.com/102038962/226821920-a0707ac3-3cf4-4564-ab26-4f4cebe3df69.png)

![3](https://user-images.githubusercontent.com/102038962/226821937-9764fa01-16fa-43ad-959d-6edf1e6c9ea0.png)

![4](https://user-images.githubusercontent.com/102038962/226821960-12c8c6ea-9ea3-475c-9f8f-d0d82a70732a.png)

만들며 API 레벨 호환성 문제를 해결해 준다. 
Appcompat 라이브러리를 사용하려면 그래들 파일의 dependencies 항목(의존성 설정)에 다음처럼 선언해야 한다. 

그런데 이 선언은 안드로이드 스튜디오에서 모듈을 만들 때 자동으로 추가된다. 

– Appcompat 라이브러리 선언

Implementation ‘androidx.appcompat:appcompat:1.2.0’ 

Appcompat 라이브러리를 이용해서 액티비티를 만들 때는

플랫폼 API의 Activity가 아니라 다음처럼 appcompat의 

AppcCompatAction 클래스를 상속받아 작성한다.

![5](https://user-images.githubusercontent.com/102038962/226822032-c2906758-08a0-41db-bb0e-d742669bf1a1.png)

- 액션바

![6](https://user-images.githubusercontent.com/102038962/226822119-b3196876-2dfe-4633-8c90-40e0d3644edd.png)

- 액션바 색상 설정

![7](https://user-images.githubusercontent.com/102038962/226822192-0a231e41-d319-4a2a-8838-17f25fdf2e69.png)

![8](https://user-images.githubusercontent.com/102038962/226822231-e8e7f442-1f34-471c-ab03-d07e82500201.png)

테마 스타일은 res/values 디렉터리에 있는 themes.xml 파일에 선언되어 있다.

Themes.xml 파일의 스타일이 앱의 액티비티에 테마로 자동 설정되고 이 테마 파일에 선언된 색상이 액티비티에 적용된다.

– 액션바 숨기기 설정

액티비티의 창은 기본으로 액션바를 포함하는데 때로는 액션바를 출력하고 싶지 않을 때도 있다. 

테마를 만들 때 Theme.MaterialComponents.DayNight.NoActionBar를 상속받으면 액션바가 나오지 않는다.

– 업 버튼 설정

![9](https://user-images.githubusercontent.com/102038962/226822302-05ee7842-aa20-43c2-85a4-1959945f0ab7.png)

![10](https://user-images.githubusercontent.com/102038962/226822328-c7f215e3-9b7d-4c1d-8d69-5d02cd8de9dd.png)

![11](https://user-images.githubusercontent.com/102038962/226822350-a5da879b-462a-4b5f-ae7b-46974155b379.png)

![12](https://user-images.githubusercontent.com/102038962/226822379-36074897-c342-42ff-a260-1f3b3bedf78b.png)

● 메뉴 구성

메뉴는 액션바의 중요한 구성 요소로 액티비티 화면에서 사용자 이벤트를 사용할 수 있도록 한다.

![13](https://user-images.githubusercontent.com/102038962/226822414-495ff2cf-3e8f-43bd-852e-bb88eec4b6b5.png)

![14](https://user-images.githubusercontent.com/102038962/226822443-62fbd22c-6a95-4312-aa35-7feee336953e.png)

– 리소스로 메뉴 구현

onCreateOptionsMenu() 함수에서 Menu 객체의 add() 함수로 메뉴를 구성할 수도 있지만, 액티비티의 메뉴는 대부분 

정적으로 제공되므로 코드가 아니라 리소스 XML 파일로 구성한다. 

메뉴를 구성하는 XML 파일은 res 폴더 아래 menu 디렉터리를 만든다.

![15](https://user-images.githubusercontent.com/102038962/226822537-85ea1d8a-9f64-4c4e-8eab-f9816e3de81d.png)

![16](https://user-images.githubusercontent.com/102038962/226822581-03541df3-efc6-40b5-9419-c5f07e259289.png)

– 액션 뷰 이용

액션 뷰는 액션바에서 특별한 기능을 제공하며 대표적으로 androidx.appcompat.widget.SearchView가 있다. 

이는 액션바에서 검색 기능을 제공한다.

● 툴바

툴바를 사용하는 목적은 액션바와 같다. 그런데 액션바는 액티비티 창이 자동으로 출력하는 액티비티 구성 요소지만, 

툴바는 개발자가 직접 제어하는 뷰라는 점에 차이가 있다. 

툴바는 액션바보다 다양한 기능을 제공할 수 있다.

![17](https://user-images.githubusercontent.com/102038962/226822640-3bd3cab3-2b9a-4b1b-a47e-3955b1345c7a.png)

![18](https://user-images.githubusercontent.com/102038962/226822670-afbcd097-98b6-4b2c-aa7d-500084e61ad5.png)

● 호환성을 고려한 기본 뷰 클래스

Appcompat 라이브러리도 기본 뷰에 해당하는 뷰를 제공한다. 

이유는 호환성 문제를 해결하기 위함이다.

![19](https://user-images.githubusercontent.com/102038962/226822716-c26fbea0-7b30-4fba-8763-e23d959a6a43.png)

#### 3. 프래그먼트 - 액티비티처럼 동작하는 뷰

androidx에서 제공하는 라이브러리 가운데 프래그먼트와 뷰 페이저2는 중요도와 사용 빈도가 높다. 

프래그먼트는 플랫폼 API에서도 android.app.Fragment로 제공하지만 대부분은 androidx.fragment 

라이브러리를 이용해 구현한다.

● 프래그먼트 소개

이는 텍스트 뷰나 버튼 처럼 액티비티 화면을 구성하는 뷰인데, 그 자체만으로는 화면에 아무것도 출력되지 않는다. 

프래그먼트가 다른 뷰와 다른 점은 액티비티처럼 동작한다는 것이다. 즉, 액티비티에 작성할 수 있는 모든 코드는 

프래그먼트에도 사용할 수 있다.

이는 태블릿처럼 큰 화면에 많은 것을 담을 때 한 액티비티에 많은 것을 작성하면 문제가 되므로 사용된다. 물론 폰도 사용함.

![20](https://user-images.githubusercontent.com/102038962/226822774-60c77bbe-bc67-440a-9396-dfe49208d9fc.png)

![21](https://user-images.githubusercontent.com/102038962/226822790-3b97998d-fd7a-4936-bb6b-af3227e1cd01.png)

![22](https://user-images.githubusercontent.com/102038962/226822821-3e27bac4-f2e5-461b-b7ae-d897f0731484.png)

● 프래그먼트 구현

프래그먼트는 Androidx.fragment 라이브러리에서 제공한다.

![23](https://user-images.githubusercontent.com/102038962/226822879-d989c9f9-7101-4e1c-9659-7408d7a192d7.png)

![24](https://user-images.githubusercontent.com/102038962/226822904-e62efd98-c420-4892-9ec0-204364e59f37.png)

먼저 프래그먼트 화면을 구성하는 레이아웃 XML 파일을 작성해야 한다. 

이 작업은 액티비티를 만들 때와 차이가 없다. 

프래그먼트는 Fragment를 상속받아 작성하는 클래스이다. 

프래그먼트 클래스에 최소한으로 작성해야 하는 함수는 onCreateView()이다. 

이 함수가 자동으로 호출되며 반환한 View 객체가 화면에 출력된다.

![25](https://user-images.githubusercontent.com/102038962/226822951-4d3001be-223c-4556-a3bf-01fc4631da56.png)

– 액티비티의 레이아웃 XML에 등록하여 프래그먼트 출력 프래그먼트도 뷰이므로 액티비티의 화면을 구성하는 레이아웃 

XML에 등록하여 액티비티 화면에 나오게 할 수 있다.

![26](https://user-images.githubusercontent.com/102038962/226823023-6a5773f1-2215-43c0-a698-ff70f39c60c6.png)

– 액티비티 코드에서 프래그먼트 출력 액티비티의 레이아웃 XML에서 프래그먼트를 출력할 수 있지만 

때로는 코드에서 직접 프래그먼트 객체를 생성하여 화면에 출력해야 할 수 있다. 

이 때는 우선 액티비티의 레이아웃 XML파일에 프래그먼트가 출력될 뷰를 하나 준비한다.

![27](https://user-images.githubusercontent.com/102038962/226823070-9ed48024-b9c6-4519-b24f-6d1313e9360d.png)

![28](https://user-images.githubusercontent.com/102038962/226823096-b7fb1eab-0d3f-4c8f-adfb-8130c9d9f6b1.png)

– 프래그먼트 생명주기

프래그먼트는 액티비티처럼 동작하는 뷰이다. 액티비티에 작성하는 코드는 모드 프래그먼트에도 작성할 수 있다. 

따라서 프래그먼트도 액티비티와 생명주기가 같다.

![29](https://user-images.githubusercontent.com/102038962/226823143-caf6575a-721d-4e98-979a-aaa12a15d4ed.png)

#### 4. 리사이클러 뷰 - 목록 화면 구성 

● 리사이클러 뷰 기초 사용법

이 뷰는 목록 화면을 만들 때 사용한다.

![30](https://user-images.githubusercontent.com/102038962/226823187-5ea3b9a6-a9a1-4933-8aa9-1d3c09aed20b.png)

![31](https://user-images.githubusercontent.com/102038962/226823230-baa93af5-28eb-4a57-87d6-70a94ca6f0b7.png)

![32](https://user-images.githubusercontent.com/102038962/226823250-758c89f3-91af-4070-a8d3-80249b02323d.png)

![33](https://user-images.githubusercontent.com/102038962/226823274-62d4ef75-bfe7-4b89-a2de-2dbafbdfcaac.png)

![34](https://user-images.githubusercontent.com/102038962/226823303-308a334f-4ec2-4e38-9cf7-ee33eadc94ea.png)

![35](https://user-images.githubusercontent.com/102038962/226823327-3350a172-4b5c-485f-8269-d43da2d8af88.png)

– 뷰 홀더 준비

각 항목에 해당하는 뷰객체를 가지는 뷰 홀더는 RecyclerView.ViewHolder를 상속받아 작성한다.

![36](https://user-images.githubusercontent.com/102038962/226823374-4ba056fd-bfc9-432c-a66b-09449de7698e.png)

– 어댑터 준비

어댑터는 뷰 홀더의 뷰에 데이터를 출력해 각 항목을 만들어 주는 역할을 한다. 

리사이클러 뷰를 위한 어댑터는 RecyclerView.Adapter를 상속받아 작성한다.

![37](https://user-images.githubusercontent.com/102038962/226823423-3388bda8-c180-43f2-b4a8-fbb081fe64f6.png)

![38](https://user-images.githubusercontent.com/102038962/226823507-1553d4ce-018b-4e21-ba9f-e85ef3373b89.png)

![39](https://user-images.githubusercontent.com/102038962/226823550-3cf2cac3-f677-4a32-b9f2-aab6d552787d.png)

![40](https://user-images.githubusercontent.com/102038962/226823586-e6cd2a47-d182-4e5a-a4e7-db6d8ed9b8d6.png)

– 리사이클러 뷰 출력

어댑터를 준비했으면 마지막으로 리사이클러 뷰에 어댑터와 매니저를 등록해 화면에 출력한다.

![41](https://user-images.githubusercontent.com/102038962/226823663-23393990-50f4-4ebe-91be-0a0688d23f30.png)

![42](https://user-images.githubusercontent.com/102038962/226823705-fa494e06-d5d8-4073-a1dd-3472e8b9609c.png)

– 항목을 동적으로 추가 or 제거

리사이클러 뷰에 항목이 출력된 후 동적으로 새로운 항목을 추가하거나 화면에 보이는 항목을 제거해야 할 때가 있다. 

이 작업은 항목을 구성하는 데이터에 새로운 데이터를 추가하거나
제거한 후 어댑터의 notifyDataSetChanged()함수를 호출하면 된다.

![43](https://user-images.githubusercontent.com/102038962/226823792-b243eb9f-3b12-4567-b079-4e51e936acbd.png)

● 레이아웃 매니저

레이아웃 매니저는 어댑터로 만든 항목을 리사이클러 뷰에 배치한다. 

레이아웃 매니저는 RecyclerView.LayoutManager 를 상속받은 클래스로, 라이브러리에서 다음처럼 제공한다.


![44](https://user-images.githubusercontent.com/102038962/226823852-016da091-a5c0-4902-8a87-cffad04d8ced.png)

![45](https://user-images.githubusercontent.com/102038962/226823881-b63ef079-8145-41bf-82f9-18d0ad3cf0ae.png)


![46](https://user-images.githubusercontent.com/102038962/226823944-7b634e1c-f773-43a6-a2d0-368600d96759.png)

![47](https://user-images.githubusercontent.com/102038962/226823984-b27ba9d4-0627-46b0-b4c0-ed9d9f9ce299.png)

● 아이템 데코레이션

이는 리사이클러 뷰를 다양하게 꾸밀 때 사용한다. 

각 항목을 꾸미거나 레이아웃 메니저가 항목을 배치하기 전후로 설정할 수 있다. 

필요하면 리사이클러 뷰에 적용하면 된다.

![48](https://user-images.githubusercontent.com/102038962/226824023-2ce9ff71-d686-46b5-8121-cebc08b4ddfb.png)

onDraw()함수는 항목이 화면에 배치되기 전에 호출된다. 

이 함수의 매개변수로 전달되는 Canvas 객체로 각종 그림을 그릴 수 있다. 

이 함수가 그린 그림 위에 항목이 나타난다.

![49](https://user-images.githubusercontent.com/102038962/226824065-655c9db0-ab68-4d82-89c4-979b3617c27a.png)

onDrawOver() 함수는 모든 항목이 화면에 배치된 후 호출된다.

매개변수인 Canvas 객체로 그림을 그리며 항목위에 이 그림이 나타난다.

![50](https://user-images.githubusercontent.com/102038962/226824129-ee2dce70-0635-49a6-994a-50a3a2fe7afa.png)

getItemOffsets() 함수는 항목 하나당 한 번씩 호출되어 각 항목을 꾸미는 데 사용된다. 

매개변수 Rect 객체는 각 항목을 화면에 출력할 때 필요한 사각형 정보이다. 

이것을 이용해 네 방향의 여백 설정이 가능하다.

![51](https://user-images.githubusercontent.com/102038962/226824181-aaf7b60d-28f4-495c-b955-e77e9c6fd6d4.png)

#### 5. 뷰 페이저2 - 스와이프로 넘기는 화면 구성

뷰 페이저는 스와이프(손가락으로 화면을 탭하여 오른쪽이나 왼쪽으로 미는) 이벤트로 전환할 떼 사용한다.

뷰 페이저는 플랫폼 API에서 제공하지 않으므로 androidx라이브러리를 이용해 개발해야 한다.

![52](https://user-images.githubusercontent.com/102038962/226824224-278050f3-3fa2-4205-8d19-ed9ec87e8c2d.png)

그리고 레이아웃 XML 파일에 뷰 페이저2를 추가

![53](https://user-images.githubusercontent.com/102038962/226824388-efe9ba4c-4c98-4e21-a980-b17bb988a8b8.png)

– 리사이클러 뷰 어댑터 이용

리사이클러 뷰에서 살펴봤던 내용과 차이가 없다. 

똑같이 작성하되 단지 뷰 페이저2의 어댑터로 적용만 하면 된다.

![54](https://user-images.githubusercontent.com/102038962/226824469-1c8ce528-83c0-4ecc-bc40-b97f8bc8e4dd.png)

-프래그먼트 어댑터 이용

![55](https://user-images.githubusercontent.com/102038962/226824559-50bdfce4-1d6a-4403-8478-0040a4b6ce0e.png)

![56](https://user-images.githubusercontent.com/102038962/226824605-59fc2619-3930-46bd-831f-02f25ad10413.png)

![57](https://user-images.githubusercontent.com/102038962/226824626-6018f1a7-0d0c-4c27-b131-fe6865b58720.png)

#### 6. 드로어 레이아웃 - 옆에서 열리는 화면 구성

이는 액티비티 화면에 보이지 않던 내용이 왼쪽이나 오른쪽에서 손가락의 움직임에 따라 밀려 나오는 기능을 한다. 

마치 서랍처럼 열리는 메뉴를 구성할 때 사용한다.

![58](https://user-images.githubusercontent.com/102038962/226824674-6a7e105a-0164-48f3-87d1-93e8c7916b8d.png)

![59](https://user-images.githubusercontent.com/102038962/226824732-71c15d14-1c53-4056-b73d-321e4da0b070.png)

드로어 레이아웃을 액티비티에 적용하려면 액티비티의 레이아웃 XML 파일에서 드로어 메뉴가 출력되어야 하는 부분의 태그를 

DrawerLayout으로 선언한다. 

대부분 액티비티의 기본 화면이 보이기 그위를 덮듯이 나오게 하므로 액티비티 레이아웃 파일의 루트

태그를 DrawerLayout으로 선언한다. 이 레이아웃 아래에는 뷰를 2개 선언해야 한다. 

이렇게 하면 자동으로 첫 번째 하위 태그 부분을 액티비티에 출력하고 두 번째 하위 태그 부분이 안 보이다가 끌려 나온다.


![60](https://user-images.githubusercontent.com/102038962/226824776-ed518f9f-162a-4869-bd4a-9e8ad1f16204.png)

![61](https://user-images.githubusercontent.com/102038962/226824809-7cbb3cb0-34fc-4327-a5ec-671ba2fc25e8.png)

ActionBarDrawerToggle 생성자의 두 번째 매개변수는 토글 버튼으로 여닫는 드로어 객체이고

셋째 넷째 매개변수는 문자열 리소스로, 드로어가 열리거나 닫혔을 때의 상태를 표현한 문자열이다.

supportActionBar?.setDisplayHomeAsUpEnabled(true) 

구문은 토글 버튼으로 사용할 아이콘이 출력되게 한다. 

원래 액션바의 HomeAsUp 아이콘은 왼쪽 화살표 모양이다. 

만약 드로어를 열기 위해 제공하는 내비게이션 아이콘을 나오게하려면 toggle.syncState() 함수까지 설정해야 한다. 

이러면 드로어가 출력되기 전에는 내비게이션 아이콘이다가 출력되면 왼쪽 화살표 아이콘으로 바뀐다.

여기까지 설정하면 화면에 토글 버튼이 잘 보이기는 하지만 버튼 클릭을 했을 때 드로어가 열리지 않는다. 

토글 버튼도 액션사 영역에 나오는 아이콘이므로 내부에서 메뉴로 취급하기 때문이다. 

따라서 메누 이벤트를 처리하는 함수인 onOptionItemSelected()에서 토글 버튼의 이벤트 처리를 해야한다.

#### 7. 제트팩을 이용해 화면 구성하기 

제트팩의 Android 라이브러리를 이용. 

화면 구성 실습.

툴바, 메뉴, 프래그먼트, 리사이클러 뷰, 뷰페이저2, 드로어 레이아웃 등을 사용.

● 정리

다양하게 꾸밀 수 있게 할려고 한건데 이런 기능을 제트팩의 androidx 라이브러리로 제공한다.

1. 제트팩은 구글에서 안드로이드 앱 개발을 위해 제공하는 다양한 라이브러리의 모음이다.

3. androidx.appcompat은 API 레벨호환성을 제공하는 라이브러리이다.

5. Androidx.recyclerview는 목록 화면을 구성하는 라이브러리이다.

7. Androidx.viewpager2는 스와이프로 화면 전환을 제공하는 라이브러리이다.

9. Androidx.fragment는 액티비티처럼 동작하는 뷰를 제공하는 라이브러리이다.

11. Androidx.drawerlayout은 손가락으로 화면을 탭해서 옆으로 밀면 서랍처럼 메뉴가 열리도록 화면을 구성하는 라이브러리이다.

*****binding 선언을 안해서 오류때매 고생함********** 











