# Java Study
# `07.07`

✅ 자바는 모든 것이 `클래스 기반에서 동작`해야 한다는 특징을 가진다.

# 개발 환경 세팅

✅ **개발 환경**

: 자바로 프로그램을 만들 수 있는 컴퓨터 환경으로 프로그램 소스를 작성하는 툴, 작성한 소스를 컴파일하는 프로그램 등을 설치하는 것이다.

✅ **버전**

`스탠다드 버전`과 `LTS 버전`을 구분하는 기준은 안정성이다.

개발하는 환경이 새로운 기능이 포함된 최신 버전이면 좋지만, 개발 기간이 수 개월 이상인 경우는 개발 환경의 변화로 인해 문제가 발생할 수 있다. 또한, 새로운 최신 버전의 검증할 시간도 고려해야 한다.

LTS 환경이란 이러한 안정성 등을 고려한 환경을 제공한다. 그렇기 때문에 스탠다드 버전은 최신 기능이 포함된 버전이지만, LTS 버전은 안정성을 주안점을 두고 출시한 최신 버전이라 생각할 수 있다.

(출처: https://wookoa.tistory.com/14)

<br>

## JDK(Java Development Kit)설치

자바 개발 환경으로 자바 프로그램을 만들기 위해서는 무조건 이것을 설치해야 한다.

### 설치 방법

JDK download 검색(https://www.oracle.com/java/technologies/javase-downloads.html)

![image-20210710230310264](README.assets/image-20210710230310264.png)

### 환경 변수 설정

JDK를 설치하면 javac를 바로 사용할 수 있는 것이 아니라 환경 변수를 설정해주어야 정상적으로 CMD(명렬프롬포트)에서  javac를 입력했을 때 정상적으로 기능들이 동작한다.(여기서는 컴파일 시킴)

해당 위치에 있는 javac를 실행시켜라는 환경 변수를 설정

**설정 순서**

환경 변수 → Path에서 새로만들기 - C:\Program Files\Java\jdk-16.0.1\bin(경로) 추가 → 시스템 변수에서 새로 만들기 - 이름: JAVA_HOME, 값: C:\Program Files\Java\jdk-16.0.1(경로에서 \bin 빼고) 추가

확인 방법

**설정 확인**

cmd에 javac 입력 시 명령어 집합이 나오게 되면 환경 변수 설정이 끝난 것이다.

<br>

## 이클립스 설치

eclipse download 검색(https://www.eclipse.org/downloads/)

<br>

## 자바소스와 컴파일

- jdk가 설치된 디렉토리 bin안에 javac.exe와 java.exe가 있다.
- `javac`는 java compiler의 약어로 자바파일을 컴파일할 때 사용하는 것이다.

✅ **컴파일**

: 프로그래머가 작성한 소스코드를 컴퓨터가 이해할 수 있는 말(기계어)로 바꾸는 행위이다. 모든 프로그래밍 언어에는 컴파일러 또는 그와 비슷한 기능을 하는 것들이 있다.

- `자바파일`은 우리가 작성해야 할 자바 프로그램을 말한다.

- 자바 프로그램은 .java라는 확장자를 가진 파일로 저장하게 되고 이렇게 저장되는 파일을 자바파일 또는 자바소스라고 한다.

- 자바로 작성한 파일을 실행하는 단계

  1. 컴파일 단계 : .java파일을 .class로 바꾸어 주는 단계
  2. 실행 단계 : .class파일을 실행시키는 단계

- 예시

  1. 소스코드(MyProgram.java)를 작성한다.

  2. 컴파일러는 자바 소스코드를 이용하여 클래스 파일(MyProgram.class)을 생성한다. 컴파일 된 클래스 파일은 Java VM(Java Virtual Machine)이 인식할 수 있는 바이너리 파일이다.

     ✅ **VM**

     : 휴대전화에서 콘텐츠나 애플리케이션을 단말기 내에서 실행할 수 있는 환경을 제공하는 가상머신의 모바일 운영체제를 말한다.

  3. Java VM(JVM)은 클래스 파일의 바이너리 코드를 해석하여 프로그램을 수행한다.

  4. MyProgram 수행 결과가 컴퓨터에 반영된다.

### 자바의 컴파일한 결과가 exe가 아닌 class인 이유

- C 또는 C++ 등으로 작성된 프로그램은 최종 결과물로  exe프로그램을 만들어 낸다.

- exe파일은 계산기와 같은 유틸리티일수도 게임일 수도 있다. exe프로그램을 실행하기만 하면 프로그램을 실행시켜볼 수 있다.

- C, C++과 같은 언어는 컴파일 된 실행 파일을 모든 운영체제에서 동일하게 사용하는 것이 불가능하다.

  ex) 윈도우에서 컴파일한 프로그램을 리눅스에서 사용 불가능! → 자바의 JVM과 같은 중간 단계의 역할을 수행하는 것이 없기 때문이다.

- C, C++등의 언어에서 만들어진 실행파일은 JVM같은 중간 단계를 거치지 않으므로 빠른 속도로 수행된다. 하지만 운영체제마다 별도의 실행파일을 작성해야 한다는 단점이 있다.

- 자바는 **JVM을 사용하기 때문에 C등의 언어보다 속도가 느리다**. 하지만 **한번 작성한 파일은 어떤 OS에서라도 사용할 수 있다는 장점**이 있다.

**⇒ 한번 작성한 것을 널리 재활용하는 것이 자바의 가장 큰 특징이자 장점 !**

### 실행 오류

**자바 모듈 오류 Error occurred during initialization of boot layer**

오류가 생기는 이유는 프로젝트를 만들 때 module-info.java 생성을 하도록 체크해 놓았기 때문이다. (module-info.java)

해결 방법 : module-info.java 파일을 삭제하면 된다.

참고 사이트 : https://laughcryrepeat.tistory.com/45

<br>

# `07.08`

# 변수

### 상수

-  상수는 메인함수 바깥쪽에 선언

- final은 한번 선언하면 바뀔 수 없다는 의미
- static 하나의 클래스에서 공유하는 어떠한 자원

:heavy_check_mark: 상수는 바뀔 수 없는 값이기 때문에 Final을 사용한다.

### 오버플로우

✔ 각각의 자료형에 따른 변수들은 나태낼 수 있는 숫자의 한계를 가지고 있다.

✔ 정해진 범위내에서만 출력한다.

```java
public class Practice3 {

	final static int INT_MAX = 2147483647;
	
	public static void main(String[] args) {
		
		// 오버플로우
		int a = INT_MAX;
		System.out.println(a+1);
		
	}

}
// System.out.println(a); → 2147483647
// System.out.println(a+1); → -2147483648
```

### 변수 관련 상식

- 변수를 선언하고 `초기화`를 하지 않으면 사용할 수 없다.
- 정수를 나타내는 타입 : short, int, long 등 다양한 타입이 존재

- 정수 변수 안에 실수를 넣게 되면 정수 부분만 저장이 된다.(버림)

:heavy_check_mark: 실수 값을 반올림 할 때는 변수에 0.5를 더한 뒤 정수형으로 형변환을  하면 된다.

```java
public class Practice1 {

	public static void main(String[] args) {
		
		// 정수형에 실수형 넣을 때, 변환 필요!
		double b = 5.5;
		int a = (int) (b + 0.5);
		System.out.println(a);

	}

}
// 6
```

<br>

# 자료형

자료형 : 어떤 프로그램 상에서 표현하고 싶은 데이터의 형태를 정의

### 자료형의 크기

![img](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/8beffc45-5b10-4ed9-a5b5-105f01b7a5c7/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210710%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210710T140527Z&X-Amz-Expires=86400&X-Amz-Signature=b06d70afcdca3ec9772a700886c37ec477b436d7ce889185f31e30a4e989c3de&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

### DataType

원시 자료형과 비원시 자료형으로 나누어짐

- 원시 자료형 : boolean, char, byte, short, int, long, float, double

- 비원시 자료형 : String, Array, etc.(다른 자료형을 엮어서 만듦)

C언어와 차이점은 boolean, String 정도

많이 사용되는 자료형 : String, Array, boolean, char, int, double

### 아스키코드

:heavy_check_mark: println : 출력하고 다음 줄로

:heavy_check_mark: ​print : 출력하고 그 줄에 있음

```java
public class Practice2 {

	public static void main(String[] args) {
		
		// 아스키코드 기반으로 a부터 z까지 출력하는 프로그램
		for(char i = 'a'; i <= 'z'; i++)
		{
			System.out.print(i + " ");
		}

	}

}
// a b c d e f g h i j k l m n o p q r s t u v w x y z
```

컴퓨터 내부적으로 아스키코드를 계산

### 진수 변환(format)

:heavy_check_mark: ​%o : 형식지정자, 10진수 → 8진수로 변환

:heavy_check_mark: ​%x : 형식지정자, 10진수 → 16진수로 변환

:heavy_check_mark: f​ormat은 줄 바꿈을 해주지 않기 때문에 \n을 사용

```java
public class Practice3 {

	public static void main(String[] args) {
		
		// 10진수를 8진수 혹은 16진수로 바꾸어 출력
		int a = 300;
		
		System.out.println("10진수 : " + a);
		System.out.format("8진수 : %o\\n", a);
		System.out.format("16진수 : %x", a);

	}

}
// 10진수 : 300
// 8진수 : 454
// 16진수 : 12c
```

### String의 내부 함수 - substring

```java
public class Practice4 {

	public static void main(String[] args) {
		
		// String의 substring함수 활용
		String name = "Kwanggyo";
		System.out.println(name);
		System.out.println(name.substring(0, 5));
		System.out.println(name.substring(5, 8));
		
	}

}
// Kwanggyo
// Kwang
// gyo
```

### ➕

- 정수를 나타내는 자료형이 많은 이유는 각 자료형이 차지하는 메모리 공간의 크기가 다르기 때문

- 소수점 표기 형식을 지수 형식으로 출력하고 싶다면 %e를 이용

- String은 내부적으로 char로 배열로 되어있다.

- String으로 다룰 수 있는 문자의 크기는 4GB → 몇 억 글자

- String은 비원시적인 자료형이기 때문에 내부적으로 함수를 가질 수 있고 하나의 클래스라고 할 수 있다.

<br>

# 연산자

:heavy_check_mark: ​static은 클래스 전반적으로 사용되는 함수

즉, 메인 메소드에서 함수를 사용하려면 함수에도 static을 붙여줘야 한다.

### 거듭제곱

```java
public class Practice6 {

	public static void main(String[] args) {
		
		// pow를 이용한 거듭제곱 작성
		double a = Math.pow(2.0, 10);
		System.out.println("2의 10제곱은 " + (int) a + "입니다.");

	}

}
// 1024
```

### ➕

- 100 < x < 200 → (100 < x) && (x < 200)

- 같은 표현 : i++, i+=1,  i = i+1

<br>

# `07.09`

# 조건문과 반복문

contains : 어떠한 문자열을 포함하는지 검사하는 함수

### 조건문 예시

```java
public class Practice2 {

	public static void main(String[] args) {
		
		// 점수에 따라 다른 메세지를 출력
		int score = 95;
		
		if(score >= 90)
		{
			System.out.println("A+입니다.");
		}
		else if(score >= 80)
		{
			System.out.println("B+입니다.");
		}
		else if(score >= 70)
		{
			System.out.println("C+입니다.");
		}
		else
		{
			System.out.println("F입니다.");
		}

	}

}
// A+입니다.
```

### String 비교, equals

```java
public class Practice3 {

	public static void main(String[] args) {
		
		// 문자열과 정수형을 조건문으로 활용
		String a = "Man";
		int b = 0;
		
		// 자바는 String을 비교할 때 equal()을 이용
		// 이유 : String은 다른 자료형과 다른 문자열 자료형이기 때문에
		if(a.equals("Man"))
		{
			System.out.println("남자입니다.");
		}
		else
		{
			System.out.println("남자가 아닙니다.");
		}
		
		if(b == 27)
		{
			System.out.println("b는 27입니다.");
		}
		else
		{
			System.out.println("b는 27이 아닙니다.");
		}
		
		// 대소문자를 구분하지 않고 같은지 판단
		if(a.equalsIgnoreCase("man") && (b == 27))
		{
			System.out.println("참입니다.");
		}
		else
		{
			System.out.println("거짓입니다.");
		}
	}

}
// 남자입니다.
// b는 27이 아닙니다.
// 거짓입니다.
```

:heavy_check_mark: equals : String을 비교할 때 사용한다. → String은 다른 자료형과 다른 문자열 자료형이기 때문에

:heavy_check_mark: equalsIgnoreCase : 대소문자를 구분하지 않고 비교

### while문 예시

```java
public class Practice4 {

	public static void main(String[] args)
	{
		// While 1부터 1000까지의 합
		int i = 1, sum = 0;
		while(i <= 1000)
		{
			sum += i++;
		}
		System.out.println("1부터 1000까지의 합은 " + sum + "입니다.");

	}

}
// 1부터 1000까지의 합은 500500입니다.
```

### for문 예시(중첩)

```java
public class Practice5 {

	final static int N = 5;	
	
	public static void main(String[] args) {
		
		// for문 : 초기화 부분, 조건 부분, 연산 부분
		for(int i = N; i > 0; i--)
		{
			for(int j = i; j > 0; j--)
			{ 
				System.out.print("*");
			}
			System.out.println();
		}

	}

}
// *****
// ****
// ***
// **
// *
```

### for문 원 출력 예시

```java
public class Practice6 {

	final static int N = 3;
	
	public static void main(String[] args) {
		
		// for문으로 원 출력하기
		// x^2 + y^2 = r^2
		for(int i = -N; i <= N; i++)
		{
			for(int j = -N; j <= N; j++)
			{
				if(i * i + j * j <= N * N) {
					System.out.print("*");
				}
				else
				{
					System.out.print(" ");
				}
			}
			System.out.println();
		}
	}

}
//    *   
//  ***** 
//  ***** 
// *******
//  ***** 
//  ***** 
//    *
```

### ➕

- 모든 조건문과 반복문에서 왠만하면 괄호 쓰기!

:heavy_check_mark: for(;;), while(true)는 무한 루프로 동작한다.

```java
public class Practice7 {

	public static void main(String[] args) {
		
		// 무한 루프, break
		int cnt = 0;
		
		for(;;)
		{
			System.out.println("출력 " + cnt);
			cnt++;
			if(cnt == 5)
			{
				break;
			}
		}

	}

}
// 출력 0
// 출력 1
// 출력 2
// 출력 3
// 출력 4
```

- 무한 루프는 break로 빠져나올 수 있다.

<br>

# 기본 입출력

입출력 : 사용자와의 상호작용을 하는 것

### Java 입출력

Scanner 클래스를 이용하여 사용자와 상호작용을 할 수 있다.

입력 받은 자료는 내부적으로 어떠한 처리를 한 뒤에 다시 사용자에게 그 값을 반환한다.

입출력을 잘 지원한다는 것 → 사용자 인터페이스가 뛰어나다.

### Scanner class

:heavy_check_mark: import java.util.Scanner;

- 자바에서 제공하는 기본 라이브러리

- 입출력을 가능하게 해주고 사용하려면 import를 해야 한다.

- class → 내부적으로 함수를 가질 수 있다.

:heavy_check_mark: ​`System.in` : 콘솔 창에서 입력하는 데이터

:heavy_check_mark: ​`int i = sc.nextInt()` : sc라는 입출력 함수가 콘솔창에서 입력되는 정수를 받아서 i에 넣어줌

:heavy_check_mark: ​`sc.close()` : 정상적으로 입출력하는 변수가 닫히게 해줌

```java
import java.util.Scanner;

public class Practice1 {

	public static void main(String[] args) {
		
		// 정수를 입력받아 출력
		Scanner sc = new Scanner(System.in);
		System.out.print("정수를 입력하세요 : ");
		int i = sc.nextInt();
		System.out.println("입력된 정수는 " + i + "입니다.");
		sc.close();

	}

}
// 정수를 입력하세요 : 10
// 입력된 정수는 10입니다.
```

### File 입출력

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class Practice2 {

	public static void main(String[] args) {
		
		// File 입출력
		File file = new File("input.txt");
		try {
			Scanner sc = new Scanner(file);
			while(sc.hasNextInt())
			{
				System.out.println(sc.nextInt() * 100);
			}
		} catch (FileNotFoundException e) {
			// 오류 발생 시(file이 없음)
			System.out.println("파일을 읽어오는 도중에 오류가 발생하였습니다.");
		}
		

	}

}
// 10000
// 9000
// 8000
```

:heavy_check_mark: import를 해주고 불러올 수 없는 경우를 위해 try - catch를 import 해준다.

:heavy_check_mark: hasNextInt() : sc가 읽어오고 있는 파일에서 다음으로 읽어올 수 있는 정수가 있는지 확인

- input.txt안의 문자는 띄어쓰기 or 줄 바꿈으로 구분이 되어 있어야 다음으로 읽어올 수 있다.

- 파일을 컨트롤 할 수 있다. → 다른 프로그램도 바꿀 수 있고 다양한 처리가 가능하다.

### ➕

- 주석은 컴파일 단계에서 제거되기 때문에 프로그램의 크기와는 상관이 없다.

:heavy_check_mark: Scanner로 문자열을 입력 받고 싶을 때에는 next() 함수와 nextline() 함수를 활용한다.

<br>

# `07.10`

# 사용자 정의 함수

다양한 동적 웹 애플리케이션을 구현할 때에도 JSP와 같은 자바 기반의 프로그리밍을 할 수 있다. 이 때, 객체지향 프로그래밍의 장점을 살린 MVC 모델을 이용한 구축이 이루어진다.

현실 세계의 다양한 사물을 컴퓨터 내부의 언어로 표현하고 그것을 활용할 수 있다.

### ✅ 객체지향

객체는 일반적으로 말하는 물건을 의미하며 여기서 물건은 단순한 데이터가 아니고 그 데이터의 조작 방법에 대한 정보 또한 포함하고 있어 그것을 대상으로 다루는 수법을 객체지향이라고 한다.

어떠한 사물이 있으면 그 사물에 특징을 살려서 모델링을 할 수 있게 해주고 나아가 객체지향의 프로그래밍 기법을 활용하게 되면 프로그래밍이 아닌 현실 세계에 있는 사물을 다루고 있는 것처럼 느끼게 해줌

### 사용자 정의 함수

- 정해진 특정한 기능을 수행하는 모듈을 의미한다.

- 함수를 적절히 활용하면 하나의 문제를 잘게 분해할 수 있다.
  - ex) 이진 트리 → 삽입, 삭제, 순회 등 다양한 함수의 집합으로 구성, 이것을 메인 함수에서 모두 처리하면 작업의 효율성을 저하 시킬 수 있다.

- 함수는 각각의 모듈로서 쉽게 수정되고 보안될 수 있다.

:heavy_check_mark: 함수를 만들 때에는 반환형, 함수명, 매개변수 순으로 작성한다.

**최대 공약수**

```java
public class Practice1 {

	// 반환형, 함수명, 매개변수
	public static int function(int a, int b, int c) {
		int min;
		if(a > b)
		{
			if(b > c)
			{
				min = c;
			}
			else
			{
				min = b;
			}
		}
		else
		{
			if(a > c)
			{
				min = c;
			}
			else
			{
				min = a;
			}
		}
		for(int i = min; i > 0; i--)
		{
			if(a % i == 0 && b % i == 0 && c % i ==0)
			{
				return i;
			}
		}
		return -1;
	}
	
	public static void main(String[] args) {
		
		// 3개의 정수가 주어졌을 때 최대 공약수
		System.out.println("(300, 200, 150)의 최대 공약수는 " + function(300, 200, 150) + "입니다.");

	}

}
// (300, 200, 150)의 최대 공약수는 50입니다.
```

- 메인 메소드도 하나의 함수 → 종료되면 프로그램이 종료되는 것과 동일하기 때문에 반환형이 없다는 뜻의 `void`를 사용한다.

- `String[] args` : 처음에 콘솔 창에서 프로그래밍 실행할 때 인자 값을 넣어주는 것을 의미

**n번째 약수**

```java
public class Practice1 {

	public static int function(int number, int k) {
		for(int i = 1; i <= number; i++)
		{
			if(number % i == 0)
			{
				k--;
				if(k == 0)
				{
					return i;
				}
			}
		}
		return -1;
	}
	
	public static void main(String[] args) {
		
		// number의 k번째 약수
		int result = function(1000, 10);
		if(result == -1)
		{
			System.out.println("1000의 10번째 약수는 없습니다.");
		}
		else
		{
			System.out.println("1000의 10번째 약수는 "+ result + "입니다.");
		}
	}

}
// 3050의 10번째 약수는 50입니다.
```

- 문자열에서 마지막 단어 추출 예시

:heavy_check_mark: ​`input.charAt()` : input에서 N번째 문자를 하나 뽑아오는 것

:heavy_check_mark: ​`input.length()` : input에서 길이

```java
public class Practice2 {

	public static char function(String input) {
		return input.charAt(input.length() - 1);
	}
	
	public static void main(String[] args) {
		
		// 문자열에서 마지막 단어를 반환하는 함수
		System.out.println("Hello World!의 마지막 단어는 " + function("Hello World!") + "입니다.");

	}

}
// Hello World!의 마지막 단어는 !입니다.
```

**max 값 반환하는 함수**

```java
public class Practice3 {

	public static int max(int a, int b) {
		return (a > b ? a : b);
	}
	
	public static int function(int a, int b, int c) {
		int result = max(a, b);
		result = max(result, c);
		return result;
	}
	
	public static void main(String[] args) {
		
		// max를 이용하여 최댓값을 저장하는 함수
		System.out.println("(123, 789, 456) 중에서 가장 큰 값은 " + function(123, 789, 456) + "입니다.");
	}

}
// (123, 789, 456) 중에서 가장 큰 값은 789입니다.
```

<br>

# 반복 함수와 재귀 함수

- 재귀 함수를 사용하게 되면 특정한 연산이 반복되어 비효율적으로 작동할 수 있다.

​	ex) Fibonacci(50) → 2^50번의 연산

- 이러한 문제 해결을 위해 동적 프로그래밍(DP)이 나온다.

### 예시

**Factorial - 반복 함수**

```java
public class Practice1 {

	public static int factorial(int number) {
		int sum = 1;
		for(int i = 2; i <= number; i++)
		{
			sum *= i;
		}
		return sum;
	}
	
	public static void main(String[] args) {
		
		// 팩토리얼 만들기 - 반복 함수
		System.out.println("5 팩토리얼은 " + factorial(5) + "입니다.");

	}

}
// 5 팩토리얼은 120입니다.
```

**Factorial - 재귀 함수**

```java
public class Practice2 {

	public static int factorial(int number) {
		if(number == 1)
		{
			return 1;
		}
		else
		{
			return number * factorial(number - 1);
		}
	}
	
	public static void main(String[] args) {
		
		// 팩토리얼 만들기 - 재귀 함수
		System.out.println("5 팩토리얼은 " + factorial(5) + "입니다.");
	}

}
// 5 팩토리얼은 120입니다.
```

**Fibonacci - 반복 함수**

```java
public class Practice1 {

	public static int fibonacci(int number) {
		int one = 1;
		int two = 1;
		int result = -1; // 문제 생겼을 경우 반환 값
		if(number == 1)
		{
			return one;
		}
		else if(number == 2)
		{
			return two;
		}
		else
		{
			for(int i = 2; i < number; i++)
			{
				result = one + two;
				one = two;
				two = result;
			}
		}
		return result;
	}
	
	public static void main(String[] args) {
		
		// Fibonacci - 반복 함수 
		System.out.println("피보나치 수열의 10번째 원소는 " + fibonacci(10) + "입니다.");

	}

}
// 피보나치 수열의 10번째 원소는 55입니다.
```

**Fibonacci - 재귀 함수**

```java
public class Practice2 {

	public static int fibonacci(int number) {
		if(number == 1)
		{
			return 1;
		}
		else if(number == 2)
		{
			return 1;
		}
		else
		{
			return fibonacci(number - 1) + fibonacci(number - 2);
		}
	}
	
	public static void main(String[] args) {
		
		// Fibonacci - 재귀 함수 
		System.out.println("피보나치 수열의 10번째 원소는 " + fibonacci(10) + "입니다.");
	}

}
// 피보나치 수열의 10번째 원소는 55입니다.
```

