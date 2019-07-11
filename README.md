(1)  App
     JVM 
     OS
     HW 

(2) JDK = jdk + jre 

(3) 환경변수 
     - JAVA_HOME 
	 - Path
	 - classpath 

	 cf) API

(4) EE  SE  Android 

(5) 클래스 구조 
    package 선언 
	import 구문 
	class 선언 
	{
		멤버변수
		생성자
		메소드 
	}

(6) 객체지향의 용어 
    1) 객체(Object): 모든 것, 클래스로부터 나온 구현물
	    (ex: 붕어빵 )
	2) 클래스(Class): 객체를 만들기위한 틀 
	    (ex: 붕어빵틀 )
	3) 속성(Attribute): 객체의 특성 ( ==멤버변수 )
	    (ex: 앙꼬, 가격, 색깔, 모양 .. ) 
	4) 생성자(Constructor): 객체가 만들어질 때 수행되는 일(기능) 
	    (ex: 반죽을 틀에 붓는다 )
	5) 메소드(Method): 객체가 하는 일(기능) 
	    (ex: 배부르게한다, 따스하게한다 )

(7) 클래스 설계 
    ( ex: 붕어빵 )
	  ex) day03/붕어빵.java 

(8) 주석( Comment )
    1) 한 라인 //
	2) 여러 라인 /* */
	3) 문서화(나중에..) /** */

(9) OOP(Object Oriented Programming)의 특성 
    1) 상속성( Inheritance ) : 부모객체의 모든 것을 자식객체에서 사용할 수 있는 성질,  재사용(Reuse) 증대
	   ex) day04/Human.java 
	   
    2) 다형성( Polymorphsm ) : 객체(클래스)가 연산을 수행하게 될 때 하나의 메소드에 대해 각 객체(클래스)가 가지고 있는 고유한 방법(특성)으로 응답하는 능력
										교수님 : 같은 타입의 이름이 같은 메소드의 내용이 달라지는 성질 
							 : 위키 - 프로그램 언어의 각 요소들(상수, 변수, 식, 오브젝트, 함수, 메소드 등)이
							          다양한 Type에 속하는 것이 허가되는 성질, 반대는 단형성
								다형성 - 객체.PolymorphToStringMethod()
								단형성 - StringFromInteger(integer값)

	   ex) day05/Figure.java

    3) 은닉성( Information Hiding ) : 외부클래스로부터 속성값(데이터)을 감추는 성질
	   ex) day05/Account.java 

    4) 캡슐화( Encapsulation ): 메소드 내용을 알 필요없이 그 형태만 알면 호출해서 사용할 수 있는 성질  
	   ex) day05/Cal.java 

	5) 추상화( Abstraction): 객체의 속성중 가장 중요한 것에만 중점을 두어 걔략화 하는 것, 즉 모델화 하는것   

////////////////////////////////// 숲 ////////////////////////////////////

(10) 변수( Variable )
    1) 유효범위
	   <1> 멤버변수 
	       1> 해당클래스내에서 유효
		   2> 종류: 클래스소속 | 객체소속  , 멤버는 반드시 소속을 가진다.
	       3> 초기화를 하지 않아도 됨 
		   ex) day05/A.java 
		
	   <2> (메소드)지역변수 
	       1> 해당 메소드내에서만 유효 
		   2> 종류: 선언초기화 | 파라미터 
		   3> 반드시 초기화를 개발자가 해줘야 함★(선언초기화지역변수는 반드시 초기화 필수)
		   4> 지역변수는 소속이 없다.
		   ex) day05/A.java
	
	2) 저장되는 데이터의 형태 
	   <1> 기본형(primitive type) 8개 
	       1> call by value 
           2> 형태: 소문자로 시작 
		   3> 종류
		      byte(1) ▶ short(2) ▶ int(4) ▶ long(8) ▶ float(4) ▶ double(8) 
			             char(2)  ▶

		      boolean(1)

				-char은 0~2^16-1이기 때문에 -2^15~2^15-1인 short로 형변환이 불가능
				 but int로는 가능

		   4> 담을 수 있는 값의 범위 
		      - byte     -128 ~ 127 ( 2^8 )
			  - short    -2^15 ~ 2^15-1 ( 2^16 )
			  - char     0 ~ 2^16-1 ( 2^16 )
			  - int      -2^31 ~ 2^31-1 ( 2^32 )
			  - long     -2^63 ~ 2^63-1 ( 2^64 ) 
			  - float    무한대 (부호비트1 지수8 가수23 =>32비트,bias 127)
						  (0.0345 양수이지만 지수부분은 음수이다 8비트에서 
						  부호비트 따로 만드는 번거로움 피하기 bias 위해더해줌)
			  - double   무한대 (부호비트1 지수11 가수52 =>64비트)
			  - boolean  false | true 


		   5> 형변환 필요성 
		      연산시 같은 Type 끼리만 계산되기 때문 

		   6> 자동형변환의 방향 
		      범위가 작은 Type -> 큰 Type 

		   7> 초기값 
		      정수(0, 0L), 실수(0.0f, 0.0), 불린(false)

		   8> 존재이유: 실행의 효율성 
		      ( Wrapper 클래스를 이용하면 모든 객체화 시킬 수 있음 ) 
				Wrapper Class ->기본형 변수와 마찬가지로 8개
				Long.MAX_VALUE => static 변수
				Inteager.MAX_VALUE
		   
		   9> 예외 형변환 
		      정수형(byte, short, char, int) 끼리의 산술연산시에는 
			  그 연산의 결과가 무조건 int 로 나옴 
			  - long은 정수형X
	
		   10> 컴퓨터의 소수 오차
		      float 과 double 오차를 가질 수 있음 

			  ex) day05/숫자형.java
		      

	   <2> 참조형(reference type)
	       1> call by reference 
		   2> 형태: (일반적으로) 대문자로 시작 
           3> 종류: 8가지 기본형을 제외한 모든 Type
		   4> 초기값: null
		   5> 자동형변환 ( 자식 -> 부모 )
		      ex)   Object
			           ▲  
					Human 
                       ▲
					SuperMan 
           6> 일반적인 형변환
		      Human m = new SuperMan(); //자동 
			  SuperMan sm = (SuperMan)m; //강제

			7> System.out.println(m); 하면 m의 주소가 찍힘

  
	3) 소속 
	   1) 클래스(소속)변수: static 붙으면  
	   2) 객체(소속)변수: static 붙지 X 
	   3) 멤버는 반드시 소속이 있고 지역변수는 없다.

	   ex) day05/소속.java

	4) 초기값 변경 유무 
	   1) 상수: final 붙으면 
	   2) 변수: final 붙지 X 

	   ex) day05/상수.java 

	  
	  cf) 변수 이름 정리 
	    - 멤버(==전역), 
	    - 지역(파라미터(==매개) + 선언초기화) 
	    - 기본형(==원시데이터)
	    - 참조(==레퍼런스)
	    - 클래스(==static변수, ==정적) 
	    - 인스턴스(==객체소속, ==동적) 
	    - 상수(==final, ==Constance )


(11) 연산자(Operator)
	1) 설명 : 데이터를 연산하게하는 기호
	2) 종류
		<1> 산술연산자 ex)+,-,*,/,%
			cf)java에서는 +연산자를 String에 사용시
				+연산자 Overriding 되어 '결합연산자'가 됨

		<2> 증감 연산자 ex)++,--

		<3> 대입 연산자 ex)=

		<4> 산술 할당(대입) 연산자 ex)+=,-=,*=,/=,%=

		<5> 비트 연산자 ex) &, |, ^, ~, shift Operator(<<,>>,>>>)
		
		<6> 비교 연산자 ex) ==, !=, <, <=, >, >=

		<7> 논리 연산자 ex) &&, ||, !

		<8> 논리 할당(대입) 연산자 ex)&=, |=

		<9> 조건 삼항(항 3개) 연산자 ex) (A?B:C)

		<10> Instanceof 연산자 ex)개체이름 instanceof 클래스이름
			-객체 클래스 확인

	3) Operator.java
	
(12) 조건문
	1)설명 : 해당 조건이 맞으면 수행되는 구문
	2)구조 :
		<1>if문			: if(조건1 boolean형){"조건1 true면 수행"} 
						  else if(조건2 boolean형){"조건2 true면 수행"}else {"모든 조건 부합X일때 수행"}

		<2>삼항연산자	: ((조건)?(조건 true 수행):(조건 false 수행))
						-삼항 안에 삼항 가능

		<3>Switch-Case	: switch(정수형+String(7버젼이상)){case a: 수행 case b: 수행2 default : 나머지수행} 
						  switch(정수형+String(7버젼이상)){default : 나머지수행 case a: 수행 case b: 수행2 } 
						-default가 case앞에 둬도 가능, but 수행된후 자동으로 default 위치 아래 case 로 넘어감

	3)삼항연산자 , Switch Case 는 if문으로 모두 전환가능

	4)Conditional.java
	
(13) 반복문
	1) 설명 : 조건이 맞을 때까지 반복하는 문장
	2) while(boolean){} : 초기식(int i=0),조건식(i<10),증감식(i++)
				   -무한루프 x =>초기식 loop밖, 조건식 loop안, 증감식 loop안
				   -게임 or 프로그램같은거는 loop가 계속 돌아가야함 -> 리소스 덜 먹게 코딩해야함

	3)do{}while(boolean) : 처음 한번 블럭내부일하고 while문 실행 

	4)for(초기식;조건식;증감식){}	:
									
	
	5)for(초기식:배열)


	-제어문(조건문,반복문) 중괄호가 없을 경우 첫 구분자(;)까지 블럭으로 잡음 

(14) 제어의 이동
	1) 제어 : 어떤 프로그램이 실행되고 있을 때 어느 한 시점에서의 CPU연산은 어떤 특정코드부분을 실행하고 있을 것이다.
			그 코드 부분을 제어점이라하고 그 제어점들의 순차적인 집합을 제어라 한다.
			즉, 프로그램의 "실행흐름(Line)"을 제어라 함
			cf )제어비유 : 부메랑

	2) 일반적인 제어 경로 
		JVM->main()->....->main()->JVM

	3) 제어권
		CPU가 연산을 실행할 수 있는 권한

	4) 제어이동 예약어(★★★) 
		1)break : 자기를 둘러싼 반복블럭을 나감
			<1> 반복블럭(Loop) 
			<2> switch블럭  
				-일반 블럭은 못나감
			<3> 예외 : Labeled break(aa:)을 사용할 경우 원하는 블록을 나감

		2)continue : 해당 조건(보통 if랑 같이씀)에 맞으면 "건너뜀" => 증감식
			<1> 반복블럭(Loop) : Loop block 맨끝에 쓰이면 아무의미없음 => 어차피 증감식으로감
			<2> 예외 : Labeled Continue

		3)return : 호출한 곳으로 "되돌아감"
			<1> void 메소드나 생성자는 return; 을 안써 줄 경우 루틴 맨밑에 생략
				-main에서 return 하면 JVM으로 돌아감 => 프로그램 종료

	
(15) 배열(Array)
	
	1)설명 : 같은 타입의 '참조형','기본형' 데이터를 저장하는 '크기가 고정된 저장소 객체'

	2)선언 : type 배열변수 [] 
		-ex : int is[],int is [],int []is,int[] is,  = new int[3] , 방법 4가지

	3)생성 : new type[크기]
		-ex : new String[2] , new int[2]

	4)초기값 : 
		<1> 기본형 = 정수 : 0, 실수 : 0.0 ,불린 : false
		<2> 참조형 = null
	
	5)초기화
		확보된 공간(방)에 데이터를 넣는 것
		-ex : strs[0] = "봄";

	6)선언 및 생성
		type 배열변수 = new type[크기]
		-ex : String strs[] = new String[5];
	
	7)선언, 생성, 초기화
		type 배열변수 = {데이터1,데이터2, .... }
		-ex : String strs[] = {"봄","여름","가을","겨울"};

		-cf : 선언만 분리할 수 없음 
				String strs[];
				strs = {"봄","여름","가을","겨울"}; 
				컴파일안됨

	8) 배열의 형변환
		같은타입으로 저장되기때문에 형변환(강제,자동)해야함
		-ex :	기본형 : short ss[] = {shor,byt,(short)intege}; 
				참조형 : Human mans[] = {new Human(),new SuperMan(),new Pepsiman()};
				모든배열  = > Object objs[] = {new String(""),new Human(),100}  
					java 5이후로는 기본형도 가능 int -> Integer -> Object, Autoboxing 후 입력
					AutoBoxing : 기본형-> 래퍼클래스 ex : int -> Integer 
					UnBoxing : 래퍼클래스 ->기본형 ex : Integer -> int 


(16) 다차원 배열
	1) 이차원배열 : 일차원 배열을 갖는 배열,  n 차원 배열 : n-1차원 배열을 갖는 배열
	2) int aa[][] 
	

(17) 예외 처리
	1) 예외(Exception) : 프로그램이 정상적으로 진행되지 못하게 하는 '돌발상황'

		-ex : 토렌트에서 상대방 파일을 읽다가 상대방이 그 파일을 삭제
			   채팅하다가 상대방이  방을 나감

	2) 종류
						Object
							|
					 Throwable
					|	           |
				Error          Exception
								|            |
			CheckedException      RuntimeException
	
	-Error 는 사용자가아닌 JVM 에서 잡는 오류
	-CheckedException = CompileException => 컴파일시에 체크, RuntimeException 에 포함되지 않는 모든 에러
	-RuntimeException =>  실행시 체크, 컴파일문제는 없음=>개발자 원하면 처리해줌
									절대 발생할 수 없는(유효성검사해서 온)데이터에 대해서는 굳이 해줄 필요는 없음

	3) 목적 : 프로그램 진행시 '발생할 수 있는 돌발상황'을 예외로 미리 정해놓고,
				해당하는 예외가 발생했을 경우 적절한 조치를 취해서 프로그램이 정상적으로 
				작동하도록 하는 것

	4) 특징 
		<1> 예외는 메소드나 생성자에서 발생
		<2> 예외를 발생시킬 때에는 throw 를 사용하고  => 무조건 발생시킴     -
				예외가 발생한다는 표식을 할때는 throws 를 사용함 =>특정예외처리를 호출한 곳으로 떠넘김
					=> 호출한 곳으로 떠넘기기때문에 가능성 표시한다고 말할 수 있음
					=> 메소드안에 throw 없어도 컴파일됨 , 그냥 가능성만 표현했기 때문에
				main 에서 throws 하면 JVM으로 예외처리 떠넘김 
		<3> 구조 
				메소드,생성자 throws (Exception 클래스){
					throw new (Exception 생성자) => throw Exception객체 랑 같은 말
				}
		<4> 처리는 직접처리 방법(try) 과 떠넘기는 방법(throws)이 있음
		<5> 자신의 예외 또는 그 상위 예외로 처리가 가능
			-ex : FileNotFoundException 걸리면 IOException 으로 처리가 가능함
			-ex : 어떤 예외던지 Exception 을 상속 받았기 때문에 모든 예외는 Exception 로 처리 할 수 있음


		-> throw new Exception();  예외 객체를 발생시킬경우 -> 직접처리 or 던지거나

	5) 방법
		<1> 직접 처리 방법
			try
			{
				예외 발생시키는 생성 or 메소드 호출 구문
			}
			catch (발생된 예외 객체, 매개변수)
			{
				처리 로직(with 객체)
			}

		<2>
			throws 절을 이용 ( 호출한 곳이나 JVM 에게 예외 처리를 떠넘김)

	6) try블럭에 2개 이상의 예외가 발생할 경우
		<1> 상속관계 Exception 인 경우
			-> 자식 예외부터 잡아줌

		<2> 상속관계가 아닌 Exception 인 경우
			->catch 절 순서가 상관없음

	7) finally
		<1>	try or catch 절 한번 수행 후 '반드시 수행 되는 절'

		<2> 특징
				1> try-catch ,try-finally(이건 예외처리라고 보기힘듦) , try-catch-finally, 이렇게 기술 다른 방법은없음
				2> try, catch 안에서 return 해버리면 return 하기전에 finally 먼저 실행된 후 return 함 , 즉 finally가 더쎔
				3> System.exit(0)-> 제어 JVM으로 넘김 , finally는 System.exit(0)를 못이김

	9) 기타
		<1> 객체 변수를 프린트 할 경우 클래스 이름과  주소가  표시되는데 
				-> 예외 객체를 표시할 때에는 그냥 예외 이름만 알려줌 x  ->doEx4 메소드에 테스트함


(18) 제한자 (Modifier)

	1) 클래스, 인터페이스, 변수, 상수, 매소드 생성자 앞에 붙어서 기능을 제한하는 '키워드'

	2) 종류
		<1> 접근제한자 ( Access Modifier )
			-클래스(public, default) , 멤버,메소드,생성자(public, protected, default, private)

			1> public : 제한이 없음
			2> protected : 같은 패키지 안 or 상속관계(다른패키지도 가능)
			3> default : 같은 패키지 안에서만 사용가능
			4> private : 같은 클래스 안에서만 사용가능
			
			- 범위가 넒음  public > protected > default > private
			- 가장 강력한 순서는 위에 반대
			- 클래스 : public , default  두가지 밖에 안됨 
						public 클래스는 파일이름과 같아야 컴파일됨, B.java -> BB.class 못만들음
						한파일에 여러가지 클래스 만들때 public 은 파일이름과 같은 클래스 하나밖에 못만들음

			- default 파랑색인 이유 : switch 문 때문에 즉, default 클래스하면 컴파일 안됨

			- 생성자자 앞에는 4가지 모두 붙을 수 있다. but private 생성자만들시 자식에서 super()를 못씀

		<2> 소유제한자 ( static )
			-멤버,메소드만 가능 , 생성자 : 객체 생성할때 사용하는 메소드라 클래스소속으로는 맞지않음

			1> 붙으면 클래스 소유, 안붙으면 객체 소유

			2> 특징
				- 멤버와 메소드에만 붙을 수 있음
				- 객체만들기전에 클래스가 먼저 메모리에 올라감 -> 그때 Static 변수가 메모리에 올라가는 것임-> 객체생성안하고 static 자원 접근 가능
					객체의 멤버위에 컴퓨터 전역변수 느낌
				- 같은 클래스 내의 static resource는 클래스 이름을 생략해서 쓸 수 있다.  ex(Classname.resource => resource)
				- 모든 객체가 공유, Satic 클래스에서 static 변수를 만들면, 같은 클래스로 만든 모든 객체에서 공유됨(객체.static변수 가능)
					객체1.static변수 = 객체2.static변수 = 클래스.static변수 = static변수(같은 클래스 static내에서) 모두 같은 메모리를 나타냄
					보통(일반적) 같은 클래스내에서는 생략해서 사용하고 , 다른 클래스에서는 클래스.static변수 로 사용함
				- static 메소드 내에서는 this 나 super를 쓸수 없다. 
				- static 변수는 지역변수로 선언될 수 없음
				

		<3> 수정제한자 ( final )
			- class(상속금지) , 멤버(수정금지), 메소드(오버라이딩금지) 

			1> 붙으면 수정을 못하게 함
			2> 특징 
				- final 은 클래스, 메소드, 멤버에 붙을 수 있고 생성자에는 못 붙음
				- final class 는 subclass 를 생성할 수 없다.
				- final variable은 선언과 동시에 초기화도 해줘야하고 변경하지 못함
				- final method는 상속받아서 사용을 가능한데 Overriding은 못한다.
				- 관례로 final variable은 대문자로 변수명 사용
				- 일반적으로는 static final variable 을 사용 메모리에 사용이 줄어듦, 그냥 final variable 은 객체만들때마다 생성

		<4> 추상제한자 ( abstract )
			- class와 메소드에만 붙음 

			1> 붙으면 추상화(그림화 x, 될화 化)가 됨
			2> 특징
				- 클래스 앞(추상클래스)과 메소드 앞(추상메소드)에만 붙을 수 있음
				- 추상클래스 안에만 추상메소드 구현할 수 있음
				- 추상 메소드는 subclass에서 overriding 해줘야 객체 생성가능, 
					생성자는 overriding 기능이 없기때문에 abstract 생성자를 사용할 수 없다.
				- 추상클래스로는 객체를 생성할 수 없다. 
				- 추상클래스 객체를 만들기 위해서는 완벽한 서브 클래스를 만든 후에    
					서브 클래스 객체를 생성하고 추상클래스로 업캐스팅 해야함

					완벽한 서브 클래스란 슈퍼 클래스에서 정의한 추상메소드를 모두 Overriding 한 클래스
					
				- 멤버변수,생성자는 추상화 할 수 없다.
				- 추상클래스도 일반적인 멤머변수,생성자,메소드를 가질 수 있음 -> 잘 사용안함
				-  abstract method = body 없는거 =추상메소드  <->  default method =  body 있는거 = 구현 메소드

		<5> 기타제한자
			synchronized(쓰레드), transient(네트워크 보안), native(System 자원) 

		-제한자 순서는 없는데 접근 - 소유 순서가 관례

(19) 식별자
	
	1)식별자 : 개발자 임의로 만드는 패키지,클래스,메소드,변수 이름
				- 식별자는 예약어(파랑)를 사용할 수 없음
	2)규칙
		<1> 첫문자가 숫자여서는 안됨 
			- package aa.2b; 이런거 불가능
		<2> 특수문자는  $와 _만 가능 (첫문자도 가능)
		<3> 길이 제약은 없음

	3)관례 (***)
		<1> 의미있는 단어를 사용
		<2> 클래스와 인터페이스 이름의 첫문자는 대문자로 함
		<3> 변수/ 메소드 / 패키지 이름은 첫문자를 소문자로 함
		<4> 단어와 단어사이의 결합으로된 식별자는 
				다음단어의 첫문자를 대문자로하거나 _로 연결함  
				(ex : do_it, doIt,ArrayIndexOutOfBoundException 등) 
		<5> $는 잘 사용하지 않음
		<6> 상수(final)는 모든 문자를 대문자로 하고 단어연결은 _로함 (첫문자 대문자로해도 의미없기 때문에)
				(ex : MAX_LENGTH)
		
(20) this 와 super
	1)this 
		<1> 정의: 자신의 '객체' 또는 '생성자'를 의미하는 대명사
				- this는 나중에 만들어질 객체의 주소를 의미하는데 당연히 객체에는 생성자가 없음 
				그래서 생성자로 쓰일때는 this()라는 괄호를 따로 붙여주는거 같음		
				
		<2> 사용
			1> 메소드안에서 지역변수와 이름이 같은 멤버변수를 접근할 때
			2> 자신의 생성자를 호출할 때 
			3> 자신의 객체를 다른 객체에게 넘겨줄 때 
			
			- this() ,생성자로 쓰일때 생성자 super()와 마찬가지로 첫라인이어야함
			- this.메소드()로 사용할 수 도 있음, 그런데 생략하는게 더 좋음 
			- 객체가 생성되기전 this로 다른객체 생성할수 있음

	2)super
		<1> 정의 : 부모의 '객체' 또는 '생성자'를 의미하는 대명사
		<2> 사용
			1> 부모의 생성자를 호출할 때
			2> 자식클래스에서 오버라이딩하기 전의 부모메소드를 호출할 때
			3> 이름이 같은 부모의 상수를 자식에서 호출할 때 =>거의 안씀

		- 모든 생성자의 첫 라인에는 super();가 생략됨, super()는 무조건 생성자블럭의 첫라인이어야 컴파일 가능
		- 객체로 사용될때에는 라인순서에 관계없음

(21) Collection Framework(계열)

	1) 같은 타입의 참조형(Object 자식) 데이터만 저장하는 저장소 객체로써 그 크기가
		고정되어 있지 않은 클래스 ('가변 배열' 클래스)
		
	2) 계층도

		<1>
	interface					   Collection			
								   |			    |
	interface					List          Set//정렬x
								   |				|				
	class		ArrayList, Vector...        SortedSet//여기서부터 정렬
												|
											 TreeSet...
		
		<2>
	interface							  Map
											|
	class				Hashtable/HashMap/TreeMap

				-Map 과 Collection 계열
				-객체 계열이 아님(인터페이스) Object를 상속 받지 않음

	3)	특징

		<1> List
			1> 순서를 보존
			2> 중복을 허용

		<2> Set ( 수학에서 집합 )
			1> 순서를 보전 X 
			2> 중복을 허용 X
			3> SortedSet 부터 정렬됨 , 그냥 Set 은 정렬안됨

		<3> Map (일대일 대응) // 파이썬 딕셔너리 같은데
			1>순서를 보전 X // 정렬도 안됨!  해쉬함수에 따라 키 순서가 정해지기때문에 순서가 없다.
			2>key 중복 X, value 중복O


		-Enhanced For Loop : Set, List, Array만 가능
		-ArrayList<Integer> 에서 <Integer>이 Generic 
							
(21-2) Collection 부가설명

	1)List :저장순서O,중복O
		<1>선형리스트
			1>Vector
				-쓰레드사용 동기화 가능
				-무거움
			2>ArrayList
				-데이터 추가 삭제시 ,추가되거나 삭제된 인덱스 이후부터 데이터집합이
					한칸밀리거나 당겨져옴 즉 복사하는것임 => 많은 추가삭제 => 성능저하
				-인덱스를 이용한 검색능력 좋음 
		<2>연결리스트 
			1>LinkedList
				- 추가 삭제에 좋음
				- 검색을 첫 데이터부터 순서대로 가기때문에 느림
				- 인덱스 없기 때문에 Iterator 사용
	2)Set : 저장순서X,중복X
		-순서가 없어서 Iterator을 사용 , Enhanced For Loop도 가능
		<1> SortedSet : 정렬기능 인터페이스
			1>TreeSet
				-이진 탐색 트리 사용(Red-Black Tree)
				-정렬방법(오름차순, 내림차순)을 지정할 수 있음
				-저장순서X
				-'정렬'되어있기 때문에 다음과 같은 함수 사용가능
					headSet(item) : 지정된 객체보다 작은값의 객체를 반환
					subSet(from,to) : ~부터 ~까지 반환
					tailSet(item) : 지정된 객체보다 큰값의 객체를 반환
		<2> UnSortedSet : 
			1>HashSet(해싱)
				-순서 없기 때문에 Iterator 사용,Enhanced For Loop 사용해도됨
				-해싱을 이용하여 구현
				-'빠른 접근 속도' -> TreeSet보다 빠름
			2>LinkedHashSet 
				-HashSet을 상속받음
				-추가된 순서대로 접근가능!

			
	3)Map : 키중복X,값중복O,순서X
		<1> Hashtable
			-HashMap보다 느린데 동기화지원
			-null불가 => 이게 HashMap과 큰 차이
		<2> TreeMap
			-정렬된 순서-> 검색 빠름
			-추가/삭제시 성능 안좋음
		<3> HashMap
			-중복X,순서X,Null허용,동기화X
		<4>	LinkedHashMap
			-추가된 순서대로 접근가능!
	4)Iterator & Enumeration : 추출전용 인터페이스
		<1> 차이점
			1> 스냅샷 : 직전 상태를 복사
			2> Iterator은 스냅샷 안함, Enumeration은 스냅샷함
			3> Iterator는 읽는 도중 참조 객체가 변경되면 오류
			4> Enumeration은 복사했기 때문에 참조객체가 변경되어도 문제없음
			5>쉽게정리 , Enumeration은 객체를 복사 => 참조객체가 삭제나 수정=> 타격X

		<2> 특징
			1>주로 인덱스가 없는 자료구조를 순차적으로 추출할 때 사용
			2>주로 순서가없는 자료구조를 추출할 때 사용
			3>hasNext, next메소드를 이용한 while문 으로 값 추출
			4>Enhanced For Loop를 사용할 수 있는 List,Set,Array 에서는 잘 사용 안 할듯


(22) Interface 

	1) 모든 멤버변수가 상수(final)이고, 모든 일반 메소드가 추상메소드(no body)로 구성된 '틀'
		(단, static,default 메소드는 바디가 있어도 포함될 수 있다. - JDK8 이상) 
		( 비유 : '껍데기', '메뉴판' )
	2> 구조
		interface A1	{}
		interface A2	{}
		interface A extends A1,A2{} //인터페이스->인터페이스 extends
		class AC implements A {} // 인터페이스 -> 클래스 implements

	2) 사용
		<1> 기본 사용				A,AChild,AUser.java
		<2> JDK 8 이상, 변화		B.java
		<3> 다중상속				C.java

	2) 특징
		- 클래스랑 마찬가지로 인터페이스도 접근제한자는 public, default만 가능	
		- 인터페이스 객체는 완벽한 자식클래스 객체를 생성한 뒤 형변환하여 생성 // 추상클래스와 같음
		- 인터페이스 안에 구현안된 메소드 있을시 인터페이스 앞에 abstract 가 생략
		- 인터페이스의 모든 메소드 앞에는 public abstract 가 생략  // protected abstract 이런거 안됨
		- 인터페이스의 모든 멤버 변수는 앞에 public static final 가 생략
		- 부모의 접근제한자보다 범위가 같거나 넓어야 오버라이딩 가능 -> 24번에서 설명
		- 인터페이스 끼리 상속은 extends로 사용하고 다중상속이 가능 (클래스 상속은 다일상속)

		-JDK 8이상에서는 interface에서 완전한(바디구현) static 메소드가 정의 될 수 있는데
			인터페이스가 다른 클래스나 인터페이스로 상속할 때 static 메소드는 넘어가지는 못함 (클래스 상속는 static도 상속 받음) 
			default 메소드는 넘어갈 수 있음

(23) 인터페이스 vs 추상클래스 


------------------------------------------------------------------------------------
					추상클래스						vs					인터페이스

1.		단일상속											다중상속
2.		완전한 클래스나 추상클래스로 상속			또다른 인터페이스로만 상속
3.		일반메소드랑 추상메소드 사용가능			추상메소드만 가능
4.		abstract 선언해야함							abstract 생략됨
5.		추상메소드는 public protected 사용가능	public 만 사용
6.		멤버가 static ,final, static final 사용가능	public static 만 가능

------------------------------------------------------------------------------------

	1) 공통점
		1> 추상메소드가 포함될 수 있다.
		2> 객체를 만들때는 완벽한 자식클래스로부터 객체를 생성하여 형변환 시킴
	2) 차이점
		1> class,interface 예약어가 다름 
		2> 추상클래스는 일반 멤버와 일반 메소드가 포함될 수 있다.

	

	3) 인터페이스 다중상속 추상메소드
		추상 단일상속  - 일반적메소드 + 추상메소드

(24) 오버라이딩 과 오버로딩

	-이름이 비슷해서 묶음, 내용은 다름

	1) (메소드) 오버라이딩
		<1> 상속관계에 있는 클래스에서 부모메소드의 내용을 자식클래스에서 변경하는 것
		<2> 조건
			1> 자식메소드의 접근제한자가 부모메소드의 접근제한자보다 같거나 넓어야 함
				-부모 : public,		자식 : public
				-부모 : protected	자식 : public, protected
				-부모 : default		자식 : public, protected, default
				-부모 : private		자식 : public, protected, default, private
			2> 반환타입은 일치해야 함 - > not compile
			3> 매개변수 타입, 개수 일치해야 함 - > 다르면 오버로딩
			4> 생성자 X 메소드 O

	2) 오버로딩
		<1> 호출시 그 해당 생성자나 메소드에 매핑되어 호출되도록 파라미터의 갯수나 
				타입 순서가 다르면서 이름은 같은 생성자나 메소드를 여러개 정의하는 것
				-> 매개변수의 순서 개수 타입에 띠라 같은 이름의 생성자나 메소드의 기능을 다르게 정의하는 것
				-> 관례 같은 종류의 기능을 하는 메소드는 오버로딩하는것이 좋다. =>가독성!  
		<2> 종류
			1> 생성자
			2> 메소드
		<2> 조건 
			1> 파라미터의 종류나 갯수, 순서가 일치해서는 안됨
			2> 반환 탑입과 무관함
			3> 상속과 관계과 없음
			4> 형변환이 가능한 파라미터라도 오버로딩으로 인정함
			
(25)	패키지(package)
	1) 비슷한 종류(기준은 설계자가 정함)의 클래스나 인터페이스들의 묶음

	2) 생김새
		클래스의 최상단에 package 라는 예약어를 사용
		( ex : package aa.bb; A.class
	    	   package aa.cc; A.class
		
		depth :클래스 깊이
		depth 1 = aa
		depth 2 = aa.bb  
		...... 

	3) 컴파일
		<1> 상대경로 컴파일
			#>javac -d . XXX.java 
			. 현재 디렉토리 
			.. 상위 디렉토리
			../../ 두번 올라간 디렉토리
		<2> 절대경로 컴파일
			#>javac -d C:\ XXX.java 
	
	4) 실행 
		컴파일 되었던 위치(패키지 최상단)에서 실행	 -> 패키지폴더 안에 들어가서 클래스 실행하면 안됨 

		#>java aa.bb.A 이렇게 실행해야함 , aa.bb 폴더가서 #>java A 하면 에러
		
		클래스이름은 같아도 패키지는 같으면 안됨


	5) 압축
		#>jar -cvf 모듈이름.jar 패키지디렉토리 

			c : 새로운 jar 패키지 파일을 생성
			t : jar 패키지내의 파일 리스트를 출력
			x : jar 패키지의 압축을 품
			f : c, t, x 옵션에 대해 사용할 jar 파일 이름을 지정합니다.
			v : jar 패키징 도구 수행중 수행 관련 메세지를 출력
			m : mainfest 파일 이름을 지정
			O : 압축하지 않고 묶기만 함
			M : mainfest 파일을 생성하지 않음
			u : jar 패키지의 내용을 업데이트
			i : 해당 jar 파일과 Class-Path 필드를 통해 참조되는 jar 파일에 대한 정보를 INDEX.LIST 파일로 생성
			-C : 압축할 때 사용할 기준 디렉토리를 지정​

	6) classpath
		<1> 클래스를 메모리에 로딩하기 위해서는 JVM에서 해당 클래스를 찾아야 하는 데, 
				그 경로를 바로 'classpath'라 함

		<2> 특징 
			 classpath 걸어주면 System 어디에서든지 해당 클래스들을 사용할 수 있음

		<3> 사용방법 ( ****** )
			1> -classpath 옵션법 (유효범위 : javac.exe, java.exe)
				[1] 디렉토리법
					컴파일
					#> javac -classpath 패키지디렉토리 XXX.java
					실행
					#> java -classpath .;패키지디렉토리 XXX
						. =>환경변수의 classpath
						; =>구분자
				[2] jar법
					컴파일
					#> javac -classpath 절대경로\XX.jar XXX.java
					실행
					#> java -classpath .;절대경로\XX.jar XXX


				[3] 예제
					Soo에 aa.bb 패키지, Soo에 aa.jar, Soo XXX.java
					#> javac -classpath C:\Soo XXX.java
					#> javac -classpath C:\Soo\aa.jar XXX.java

			2> set classpath법 (유효범위 커멘드창(cmd))

				[1] 디렉토리법
					#> set classpath=.;패키지상위 폴더 절대경로
					#> javac XXX.java
					#> java XXX
				[2] jar 법
					#> set classpath=.;jar절대경로(~~XXX.jar)
					#> javac XXX.java
					#> java XXX

				[3] 예제
					Soo에 aa.bb 패키지, Soo에 aa.jar, Soo XXX.java
					#> set classpath =.; C:\Soo
					#> set classpath =.; C:\Soo\aa.jar

			3> 환경변수법(유효범위 : 해당 OS)
				환경변수 classpath가서 .;경로1;경로2 ...


(26) 주요 클래스
	1) java.util.Calendar
		- 객체 생성 : 
			Calendar c = Calendar.getInstance(); //현재 시간 
		- 날짜 세팅 : 
			c.set(year,month-1,day)
			c.setTime(Date d)
		- 필드 :
			Calendar.YEAR
			Calendar.MONTH
			Calendar.DATE
			Calendar.DAY_OF_WEEK 
			등등 api가 면있음
		- 세팅된 날짜 디테일 :
			c.get(int field)
			c.get(Calendar.YEAR) // 년
			c.get(Calendar.DAY_OF_WEEK) // 요일
		- 그달의 마지막날 : 
			c.getActualMaximum(Calendar.DAY_OF_MONTH);
		- 그달의 마지막주
			c.getActualMaximum(Calendar.WEEK_OF_MONTH)
		- UTC 기준 timestamp //
			c.getTimeInMillis()

	2) java.util.Date
	
(27) 쓰레드
	1) 설명 : 프로세스를 구성하는  '제어의 흐름' (제어적 측면)
	2) Process 와 Thread 차이 
		<1> Process : 프로그램 실행 단위 , 위키 : 실행된 프로그램
		<2> Thread : 프로세스를 구성하는 '작업 단위' (작업 측면)
	3) 장점
		쓰레드가 경량프로세스라고 불리는 이유는 프로세스의 공통 리소스를 공유하기 때문이임
	4) 생성 & 실행
		<1> java.lang.Thread 를 상속받는 법 ->  클래스 상속
			1> extends Thread
			2> run(); 오버라이딩
			3> 쓰래드가된 객체.start();
		<2> java.lang.Runnable 을 상속받는 법 -> 인터페이스 상속 
			1> implements Runnable
			2> run(); 오버라이딩
			3> new Thread(this).start();
	5) LifeCycle
		<1> 5가지 상태로 구성
			 New -> Ready -> Running(CPU할당)-> Terminated
							└	Waiting <┘
				-Running -> Waiting : 입출력이나 Thread.sleep()같은 메소드
				-Running -> Ready : yield() 함수
		<2> 상태이동은 메소드나 스케쥴러로 가능
		<3> 소멸상태(Terminated) : run(){}가 수행완료되면 자동으로 소멸상태로 이동되고 다시 살아날 수 없음
	6) 우선순위 (Priority)
		<1> Ready 상태의 쓰레드 중에서 우선적으로 CPU에 할당(점유)되는 쓰레드를 판별하기위한 Level값 
		
		<2> 범위 : 1(Min)~10(Max), 처음만들면 5(Normal)
		
	7)  주요 메소드
		<1> sleep(시간);
			Running -> Waiting
		<2> yield();    
			Running -> Ready
		<3> join()
			join하는 순간 부모 쓰레드가 Waiting 상태가 되고 자식 쓰레드가 끝나면 다시 Running 상태가 됨    
			
	8) 동기화 (synchronized)

		<1> 하나의 이상의 쓰레드가 어떤 연산에 동시에 접근했을 때
			그 연산에 대한 값의 무결성(결함X)을 보장하기 위해서 수행 영역안에 Lock을 걸어주는 것

			-데이터베이스에서 무결성 유지를 알아서하기 때문에 많이 사용하지는 않음 

		<2> 비유 : 화장실 문고리 , 임계구역

		<3> 예
			
			i++;
																	극단적인 예
			#CPU 연산 단계#				정상	쓰레드1	쓰레드2			무결성X	쓰레드1	쓰레드2
			1>현재 i값을 읽음							i=0		i=1							i=0		i=0
			2>i값을 증가 시킴							i=0		i=1							i=0		i=0
			3>증가된 값을 i에 저장					i=1		i=2							i=1		i=1

			=> 쓰레드가 여러개일때 순서가 겹칠 수 가있다. 
			=> 1번쓰레드가 읽고 i값을 증가시킬때 2번쓰레드가 읽어버리면 0으로 인식하고 결과값을 1을 출력함

		<4> 방법
			synchronized 제한자를 메소드나 어떤 영역(블럭)에 적용해주면
			그 영역에 대해서 동기화 처리가 됨  => 블럭안에 쓰레드는 하나만 들어감

			ex1 ) synchronized void m1(){} 
				
			ex2 ) void m2(){
					//동기화 블럭
					{
						synchronized(this){
							//동기화 로직
					}}
				}



(98) 자료구조
	1) 단순구조(기본형)
		-정수
		-실수
		-문자
		-문자열

	2) 선형구조
		-순차(선형)리스트
		-연결 리스트
		-스택
		-큐
		-데크

	3) 비선형구조
		-트리
		-그래프

	4)파일구조
		-순차파일 : 자기테이프
		-색인파일 : 하드디스크
		-직접파일 : 해싱


(99) 메모리 스택, 힙
	1)정적 메모리 스택(Stack) 영역

		<1> 스택 영역에는 기본타입 변수가 할당되고 변수의 실제 값이 저장

		<2> 메모리에 정적으로 할당되고 컴파일 된다.

		<3> 객체 안의 메소드의 작업이 종료되면 할당되었던 메모리 공간은 반환되어 비워집니다.

	2)동적 메모리 힙(Heap) 영역

		<1> 힙 영역에는 객체와 배열이 생성됩니다. 그리고 참조타입(배열, 클래스, 인터페이스 등) 들의 주소를 저장합니다.

		<2> 기본타입 변수들과는 다르게 크기가 정해져 있지 않습니다.

		<3> 프로그램 실행시 메모리에 동적으로 할당됩니다.

		<4> '참조하는 변수가 없으면' 자바의 가비지 컬렉터가 제거합니다.  => 궁금했던거





					
