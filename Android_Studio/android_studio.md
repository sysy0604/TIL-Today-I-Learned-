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
>
>* layout_margin 속성
>   * 자신과 부모 레이아웃이나 위젯 사이의 간격, 주위 다른 위젯과의 간격을 지정.
>   * 자신과 다른 레이아웃 사이의 간격을 지정함.
>
>
>* 태그
>* 버튼
>   * 내가 내포할 자식이 있을땐 `<Button    />`
>   * 없을때는 깔끔하게 닫는게 좋다. `<Button   Button/>`
>   * 라디오버튼
>   * 선택박스버튼

>
