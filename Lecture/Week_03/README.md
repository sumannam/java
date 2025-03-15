
# 자바 프로그램 구성 요소

- [IntelliJ](../../Utils/IntelliJ.md)에서 프로젝트를 생성하면 아래와 같이 기본 소스가 생성된다.
```Java
public class Main {
    public static void main(String[] args) {
        System.out.printf("Hello and welcome!");
        for (int i = 1; i <= 5; i++) {
            System.out.println("i = " + i);
        }
    }
}
```

## #클래스 

- 클래스(class)는 자바와 같은 객체 지향 언어의 기본적인 빌딩 블록
- 클래스들이 모여서 하나의 자바 프로그램
- 자바에서 소스 파일 이름은 항상 public이 붙은 클래스의 이름과 동일해야 함

> [!NOTE] 참고
자바에서는 소스 파일 이름과 클래스 이름이 상당한 관련이 있다. 일단 하나의 소스 파일 안에는 하나의 클래스만 있는 것이 바람직하다. 하지만 하나의 소스 파일에는 여러 개의 클래스가 들어 있을 수 있다. 
> - 소스 안에 public 클래스가 하나 있다면 반드시 소스 파일의 이름은 public 클래스의 이름과 일치하여야 한다(단, 다른 클래스는 public 클래스가 아니어야 한다) .
> - 만약 하나의 소스 파일 안에 public 클래스가 없다면, 소스 파일 안에 포함된 어떤 클래스의 이름으로 하여도 상관없다.
> - 하나의 소스 파일 안에 public 클래스가 2개 이상 있으면 컴파일 오류가 발생한다.
> 


## #메소드 

- 메소드(method)는 특정한 작업을 수행하는 코드의 묶음
- 메소드는 클래스 안에 정의된 함수



```mermaid
flowchart LR
input["입력(Input)"] --> method["메소드(Method)"] --> output["출력(Output)"]

```


```Java
public class Main {
    public static void main(String[] args) {
        문장1
        문장2
        문장N
        }
    }
}
```

- `public`: 누구나 호출 가능"이라는 접근 제어자
- `static`: 정적 메소드이다"를 나타내는 키워드
- `void`: 결과값을 반환하지 않음"을 의미하는 반환 타입
- `main`: 메소드 이름
- `String[] args`: 외부에서 주어지는 데이터를 받는 매개 변수
- 하나의 메소드 안 에는 여러 개의 문장이 포함

### #문장

- 사용자가 컴퓨터에게 작업을 지시하는 단위
- 문장은 프로그램을 이루는 가장 기초적인 단위

```Java
		...
		sum = x + y;
		...
```

### #주석

- 소스 코드가 하는 일을 설명하는 설명글
- 프로그램의 실행 결과에 영향이 없음

```Java
		/* 
			text1
			text2		
		*/
		// 여러 줄을 주석 처리할 때 사용
		
		// text
		//에서 줄의 끝까지 주석(한 줄 주석)
		
```


# 기본 규칙

## 식별자 규칙

- 알파벳 문자와 숫자, 밑줄 문자 _로 이루어진다. 한글 이름도 가능하다.
- 첫 번째 문자는 반드시 알파벳 또는 밑줄 문자 _이여야 한다. 숫자로 시작할 수 없다.
- %, &, # 와 같은 특수 문자는 사용할 수 없다. 단 $와 ‘_’은 가능하다.
- 대문자와 소문자를 구별하여 서로 다른 것으로 취급한다. 따라서 변수 index와 Index, INDEX은 모두 서로 다른 변수이다.
- 자바 언어 키워드(if, while, true, false, null,...)와 똑같은 이름은 허용되지 않는다.

### 자바 키워드

- abstract
- assert 
- boolean 
- break 
- byte 
- case 
- catch 
- char 
- class 
- const* 
- continue 
- default 
- do 
- double 
- else 
- enum 
- extends 
- final 
- finally 
- float 
- for 
- goto* 
- if 
- implements 
- import 
- instance of 
- int 
- interface 
- long 
- native 
- new 
- package 
- private 
- protected 
- public 
- return 
- short 
- static 
- strictfp 
- super 
- switch 
- synchronized 
- this 
- throw 
- throws 
- transient 
- try 
- void 
- volatile 
- while

## 기본 데이터 타입

**데이터 타입**은 크게 두 가지로 나뉩니다:

- **기초형(Primitive Type)**: 실제 값이 직접 저장됩니다.
    - 정수형: byte, short, int, long
    - 실수형: float, double
    - 논리형: boolean
    - 문자형: char
- **참조형(Reference Type)**: 실제 객체를 가리키는 주소값이 저장됩니다.
    - 클래스(Class)
    - 인터페이스(Interface)
    - 배열(Array)


| 자료형     | 설명      | 크기(바이트) | 범위                                         |
| ------- | ------- | ------- | ------------------------------------------ |
| byte    | 부호있는 정수 | 1바이트    | -128에서 127                                 |
| short   | 부호있는 정수 | 2바이트    | -32768에서 32767                             |
| int     | 부호있는 정수 | 4바이트    | -2147483648에서 2147483647(20억 정도)           |
| long    | 부호있는 정수 | 8바이트    | -9223372036854775808에서 9223372036854775807 |
| float   | 부동소수점형  | 4바이트    | 약 ± 3.4028347 × 10¹³⁸(유효숫자 6-7개 정도)        |
| double  | 부동소수점형  | 8바이트    | 약 ± 1.7976931 × 10³⁰⁸(유효숫자 15개 정도)         |
| char    | 문자형     | 2바이트    | \u0000에서 \uFFFF                            |
| boolean | 논리형     | 1비트     | NA                                         |

