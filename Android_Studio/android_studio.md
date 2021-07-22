**21.07.14**
# 1장 안드로이드의 개요와 개발환경 설치
## 01. 안드로이드의 개요
>### 1. 스마트폰의 개요(20p)

>* 스마트폰
>   * 통화기능 + 컴퓨터 + 다양한 기능 내장(MP3, 카메라, DMB, GPS 등)
>
>* 스마트폰의 역사
>   * 1992년 IBM사의 사이먼(최초)
>   * 1996년 노키아9000
>   * 2002년 마이크로소프트 포켓PG
>   * 2007년 아이폰
>   * 2008년 안드로이드 폰
>   * 2010년 윈도폰7
>
>* 스마트폰의 운영체제(21p)
>   * 2002년 2분기 기준 세계시장 점유율
>   * 안드로이드 74%, 아이폰 25%,  윈도폰 0.01%
>
>### 2. 안드로이드
>* 안드로이드의 주요 기능(24p)
>   * 애플리케이션 프레임워크를 통해서 제공되는 API를 사용함으로써 **코드를 재사용**하여 효율적이고 빠른 애플리케이션 개발 가능
>
>* 안드로이드의 특징(25p)
>

## 02. 안드로이드 개발 환경(28p)
>### 2. 안드로이드 개발 환경의 구성

## 03. 안드로이드 개발 환경 설치(31p)
>### 1. 설치 순서(571p 원클릭 파일 다운 권유)
>* 인텔 HAXM(하드웨어를 가속화 시켜주기 위한 매니저) 설치
> → Android Studio 다운로드(http://developer.android.com)
> → Android Studio 설치
> → Android Studio 환경 설정
> → 안드로이드 SDK 업데이트
> → Android Virtual Device(AVD) 생성
> → 앱 개발
>
>*
***
# 2장 처음 만드는 안드로이드 어플리케이션
**21.07.16**
>562p 안드로이드 기기에서 실습하기
>* file - setting - autoimport  //명령어 자동으로 입력해주는 설정.
>
>* <버튼 클릭시 이벤트 실행>
>
>button = (Button)findViewById(R.id.button0);    //findViewById : 변수 별명(ID) 지정
>button.setOnClickListener(new View.OnClickListener() {  //토스트 메시지. //클릭시 무조건 호출하는 메소드.
>            @Override
>            public void onClick(View v) {
>            
>            }
>        });
>
>Toast.makeText(getApplicationContext(), "버튼이 눌렸습니다.", Toast.LENGTH_SHORT).show();  //버튼 눌렸을 때 토스트메시지 출력
>
**21.07.19**
>104p 직접 풀어보기2-3 실습
>* 변수 4개 설정. 하나씩 해당 코드 적용
> Intent mlntent = new Intent(Intent.ACTION_VIEW, Uri.parse("")); //Intent : 화면 전환을 위한 수단
>
>* Intent mlntent = new Intent(Intent.ACTION_VIEW, Uri.parse("http://m.naver.com"));   //홈페이지 창 열기(네이버)    //Intent : 화면 전환을 위한 수단
>* Intent mlntent = new Intent(Intent.ACTION_VIEW, Uri.parse("tel:/114"));   //전화 걸기(114)
>* Intent mlntent = new Intent(Intent.ACTION_VIEW, Uri.parse("content://media/internal/images/media"));   //갤러리 열기
>* finish();   //앱 종료
>* button1.setBackgroundColor(Color.GRAY);  //버튼 배경색 지정
>* button1.setTextColor(Color.BLACK);       //버튼 글자색 지정
>
>
# 4장 기본 위젯 익히기
## 01. 뷰의 개요
### 1. 뷰와 뷰 그룹
>* View(뷰) 클래스 (154p)
>   * 안드로이드 화면에서 실제로 사용되는 것들은 모두 View클래스 상속을 받음.
>   * 다른 말로 '위젯'이라고도 함.
>   * 다른 위젯을 담을 수 있는 위젯을 **레이아웃** 이라고 함. 레이아웃은 ViewGroup 클래스 아래에 존재.
>
### 2. View클래스의 XML 속성(157p)
>* id 속성
>   * id속성은 모든 위젯의 아이디를 나타냄
>   * JAVA코드에서 위젯에 접근할 때 id 속성에 지정한 아이디 사용
>   * id속성은 위젯에 아이디를 새로 부여하는 속성.
>   * 어떤 동작을 하기 위한 속성일 때 id속성을 지정한다. (일반적으로 클릭 또는 터치했을때)
>   * 클릭이나 터치를 해도 아무 동작이 필요 없는 속성인 경우는 id 속성을 굳이 지정하지 않아도 된다.(
>  
>* layout_width, layout_height 속성
>   * 모든 위젯에 필수로 들어감.
>   * match_parent : 자신의 부모(대개는 레이아웃)에 너비나 높이를 맞춘다.
>   * wrap_content : 내용물 만큼 딱 맞춰서 너비나 높이를 맞춘다.
>   * 안드로이드 버전마다 해상도가 다르기 때문에 절대적인 수치보단 상대적인 수치를 쓴다.
>
>* background 속성
>   * 주로 #RRGGBB값으로 지정 (16진수)
>   * 각 값은 빨강, 초록, 파랑을 의미.
>   * RR,GG,BB위치는 16진수 00~FF로 표현 가능
>   * 앞에 2자리를 추가하여 투명도 표현 가능.  #AARRGGBB
>   * AA는 알파값. 00~FF. 00는 완전 투명, FF는 완전 불투명
>
>* padding 속성
>   * 위젯의 경계선으로부터, 위젯 안의 요소가 떨어지도록 설정.
>   * 자신의 내부에 들어있는 위젯과 자신의 경계선 사이 간격을 지정
>   * 전체 여백 지정(?)
>
>* layout_margin 속성
>   * 자신과 부모 레이아웃이나 위젯 사이의 간격, 주위 다른 위젯과의 간격을 지정.
>   * 자신과 다른 레이아웃 사이의 간격을 지정함.
>   * 위젯 각각의 여백 지정(?)
>
>* visivility 속성
>   * 위젯을 보일 것인지 여부를 결정
>   * 디폴트인 visivle은 보이는 상태. invisible과 gone은 안 보이는 상태
>   * invisible : 보이지 않을 뿐, 원래의 자리는 계속 유지함
>   * gone : 보이지도 않으며 자리까지 없어짐
>
>* enabled, clickable 속성
>   * enabled : 위젯의 동작 여부
>   * clickable : 클릭이나 터치가 가능하도록 함
>   * true와 false로 지정 (디폴트 : true)
>   * XMl보다 JAVA코드에서 주로 사용함.
>
>* rotation 속성
>   * 위젯을 회전시켜서 출력.
>   * 값은 각도로 지정함.
>   
>* [직접 풀어보기 4-2(167p)]
>   
>* 태그
>* 버튼
>   * 내가 내포할 자식이 있을땐 `<Button    />`
>   * 없을때는 깔끔하게 닫는게 좋다. `<Button   Button/>`
>   * 라디오버튼
>   * 선택박스버튼
>
## 02. 기본 위젯 다루기(168p)
### 1. 텍스트 뷰
>* 텍스트 속성
>   * text 속성 : 텍스트뷰에 나타나는 문자열을 표현
>   * textColor 속성 : 글자의 색상을 지정. #RRGGBB 나 ##AARRGGBB 형식 사용
>   * textSize 속성 : 글자의 크기를 dp, px, in, mm, sp 단위로 지정
>   * typeface 속성 : 글자의 글꼴을 지정.
>   * textStyle 속성 : 글자의 스타일을 지정.
>   * singleLine 속성 : 글이 길어 줄이 넘어갈 경우, 강제로 한 줄만 표시하고 문자열의 맨 뒤에 '...'을 표시.

### 2. Java코드로 XML 속성 설정(170p)
>* xml코드 속성들은 다 java코드의 매서드에 존재함. 그러나 java코드가 많아지면 느려지기 때문에, 꼭 필요한 코드만 java에 적는게 좋다. 나머지는 XML에서 작성
>
### 3.버튼과 에디트텍스트(172p)
>* 버튼 : 버튼을 클릭하는 이벤트를 가장 많이 사용함.
>   * 버튼 클릭 시 동작하는 Java코드 3단계
>       1) 버튼 변수 선언
>           button mybutton;
>       2) 변수에 버튼 위젯 대입
>           mybutton = (button) findViewById(R.id.button1);
>       3) 버튼을 클릭할 때 동작하는 클래스 정의
>           mybutton.setOnClickListener(new View.OnClickListener()
>           {
>               public void onClick(View v)
>               {
>               //동작 내용을 이 부분에 코딩
>               }
>           }
>
> * 에디트텍스트 : 값을 입력받은 후 해당 값을 Java코드에서 가져와 사용하는 용도
>    * 에디트텍스트 사용 형식
>       1) 에디트텍스트 변수 선언
>           EditText myEdit;
>       2) 변수에 에디트텍스트 위젯 대입
>           myEdit = (EditText) findViewById(R.id.edittext1);
>       3) 에디트텍스트에 입력된 값 가져오기 -> 주로 버튼 클릭 이벤트 리스너 안에 삽입(해당 데이터 타입으로 변환해서)
>           String myEdit.getText().toString(); //사용자에게 키보드로 입력받는 코드(문자열)
>
>* [실습 4-1 초간단 계산기 앱 만들기 (174~179p)] 
>   * OnClick : 눌렀다 떼다. 눌렀을땐 동작 x. 떼는 순간에 이벤트 발생
>   * OnTouch : 눌렀을 때 동작 따로, 뗐을 때도 동작 따로. 따로따로 이벤트 발생 가능.
>   * .parse : Int형으로 변환해주는 메소드. Integer 안에 있음. ex)Integer.parseInt(변수명)
>
## 03. 기본 위젯 활용하기(182p)
### 1. 컴파운드 버튼
>* 체크박스
>   * 체크할 때 마다 체크, 언체크로 변경
>   * 여러 개의 체크박스가 있어도 서로 독립적으로 동작.
>       * 여러 개 동시 체크 가능.
>
>* 체크박스에서 체크와 언체크가 바뀔 때 Java 처리
>   * 버튼 클릭과 절차가 거의 동일함
>       1) 체크박스 변수 선언
>           CheckBox mycheck;
>       2) 변수에 체크박스 위젯 대입
>           mycheck = (CheckBox) findViewById(R.id.android);
>       3) 체크박스가 변경될 때 동작하는 클래스 정의
>           
>* 스위치와 토글버튼
>   * 스위치와 토글버튼은 모양만 조금 다름. 용도는 거의 동일
>   * 스위치의 주 용도 : 온/오프 상태 표시
>
>* 라디오버튼과 라디오그룹
>   * 라디오버튼 : 어러 개 중 하나만 선택해야 하는 경우에 사용.(근데 둘 다 체크됨?????. 그래서 **그룹으로 꼭 묶여야 함**)
>   * 라디오그룹 : 라디오버튼만 여러 개 나열하면 클릭하는 것마다 모두 중복 선택이 되므로, 라디오그룹과 함께 사용해야 함.
>
### 2. 이미지뷰와 이미지버튼(185p)
>* 이미지뷰(ImageView)
>   * 그림을 출력하는 위젯. 그림이 필요하거나 화면을 화려하게 구성할 때 사용. //이미지액자. //틀. //이미지뷰라는 틀을 만들어놓고, 그 안에 그림을 삽입.
>   * 이미지뷰에 보여줄 그림 파일은 프로젝트의 [res] - [drawable]에 있어야 함.
>   * 접근은 XML에서 "@drawable/그림 아이디"형식으로 함. 확장자 빼고
>   * 이미지 파일명은 한글x, 영어 대문자x (영어 소문자, 숫자만 가능.)
>   * 하나의 이미지뷰에 사진을 바꿔가며 보여주는 형식. 물론 여러개의 이미지뷰도 가능.
>   
>* 이미지뷰 및 이미지버튼의 XML속성(186p)
>   * **src : 이미지 경로**
>   * maxHeight/maxWidth : 이미지의 크기 지정
>   * scaleType : 이미지의 확대/축소 방식 지정
>   
>* [실습4-2 애완동물 사진보기 앱 만들기 (187~193p)]
>   * .setImageResource(R.drawable.이미지파일명); : 이미지뷰에 이미지를 띄우는 속성
>   
