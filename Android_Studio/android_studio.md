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
> button = (Button)findViewById(R.id.button0);    //findViewById : 변수 별명(ID) 지정
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
### 1. 뷰
>* View(뷰)
>*
