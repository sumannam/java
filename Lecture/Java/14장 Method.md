
## 🎯 자바 메소드란?

> **메소드(method)**란?  
> 👉 어떤 일을 처리하기 위해 **미리 정해놓은 코드 덩어리**이다.
> 필요할 때 **이름을 부르면 실행**된다.


## 🧱 메소드의 구성

## 기본 구조

자바에서 메소드는 기본 구조는 아래와 같다.

```
반환타입 메소드이름(매개변수) {
    실행할 코드들;
    return 결과값;
}
```


## 예시

```java
public int add(int a, int b) {
    int sum = a + b;
    return sum;
}
```

| 요소               | 설명                               |
| ---------------- | -------------------------------- |
| `public`         | 접근 제어자: 다른 클래스에서 이 메소드를 쓸 수 있게 함 |
| `int`            | 반환 타입: `int`형 숫자를 결과로 돌려줌        |
| `add`            | 메소드 이름: 호출할 때 이 이름을 씀            |
| `(int a, int b)` | 매개변수: 메소드가 사용할 입력 값              |
| `return sum;`    | 결과를 돌려주는 코드                      |

## 메소드 구조

```java
[접근제어자] [반환타입] [메소드이름](매개변수들) {
    // 메소드가 실행할 코드
    return 반환값;
}
```

|구성 요소|설명|예시|
|---|---|---|
|**접근제어자**|메소드를 어디서 사용할 수 있는지 결정해요. 보통 `public`을 많이 씁니다.|`public`, `private` 등|
|**반환타입**|메소드가 **결과로 돌려주는 값의 자료형**이에요. 아무것도 안 돌려주면 `void`라고 써요.|`int`, `double`, `String`, `void`|
|**메소드 이름**|메소드의 이름이에요. 이 이름으로 메소드를 "부릅니다" (호출).|`calculateArea`, `printName`|
|**매개변수(Parameter)**|메소드가 사용할 **입력값**이에요. 0개, 1개, 여러 개 가능해요.|`(int x, int y)`, `(double r)`|
|**return문**|메소드가 **결과값을 돌려주는 코드**예요. `return` 뒤에는 반환할 값이 옵니다.|`return x + y;`|

## 메소드 이름

## ✅ 자바 메소드 이름 짓는 방법 (Naming Convention)

자바에서는 **정해진 규칙(관례)**에 따라 메소드 이름을 짓는 것이 좋다.

### 📌 기본 규칙

| 규칙                 | 설명                          | 예시                                    |
| ------------------ | --------------------------- | ------------------------------------- |
| ✅ **소문자로 시작**      | 메소드 이름은 소문자로 시작해야 해요        | `printName`                           |
| ✅ **단어가 바뀔 때 대문자** | 단어가 두 개 이상일 때는 **앞글자만 대문자** | `calculateArea`, `getStudentName`     |
| ❌ **띄어쓰기 금지**      | 띄어쓰기 대신 **단어 연결 시 대문자**     | `sendMessage` (O), `send message` (X) |
| ✅ **의미 있는 이름 사용**  | 기능을 잘 설명하는 이름을 짓기           | `saveData`, `deleteUser`, `findMax`   |

### ✅ 추천 형식: **동사 + 명사** (Verb + Noun)

메소드는 "동작"이기 때문에 보통 **동사로 시작**한다.
그 다음에는 **대상이 되는 명사**를 붙이면 아주 자연스럽고 읽기 쉽다.

|패턴|예시|의미|
|---|---|---|
|`get + 명사`|`getName()`|이름을 가져온다|
|`set + 명사`|`setAge(int age)`|나이를 설정한다|
|`calculate + 명사`|`calculateArea()`|넓이를 계산한다|
|`print + 명사`|`printResult()`|결과를 출력한다|
|`find + 명사`|`findMax()`|최댓값을 찾는다|
|`is + 형용사`|`isEmpty()`|비었는지 확인 (반환값은 보통 `boolean`)|

### ❌ 나쁜 예시

|잘못된 이름|문제점|
|---|---|
|`doIt()`|무엇을 하는지 전혀 알 수 없음|
|`a1()`|이름이 너무 짧아서 의미 없음|
|`calculator()`|명사만 있고 동작이 없음 (메소드보다 변수 이|


### 메소드 이름 규칙 정리

- 소문자로 시작하고 단어가 바뀌면 대문자 (camelCase)

- 메소드는 보통 동사로 시작

- 동사 + 명사 형태가 가장 직관적

- 의미 있는 이름을 지어야 유지보수와 협업이 쉬움


## 📌 매개변수(Parameter)란?

- 메소드를 실행할 때 **외부에서 값을 전달받는 변수**이다.

- 예를 들어 `calculateArea(5.0)`에서 `5.0`은 반지름이고, 이 값이 `radius`에 들어간다.


```java
public static int square(int num) {
    return num * num;
}

// 호출 예시
int result = square(4);  // num에 4가 들어가고, 16을 반환함
```

---

## 📌 return이란?

- 메소드 안에서 계산한 **결과값을 돌려주는 키워드**예요.
    
- return을 쓰면 메소드 실행이 끝나고, 결과를 호출한 곳으로 보냅니다.
    
- `void`인 경우에는 return을 안 써도 됩니다 (혹은 `return;`만 씀).
    

### 예: `int`를 반환하는 경우


```
public static int add(int a, int b) {
    return a + b;
}
```

### 예: 반환값이 없는 경우 (`void`)

```java
public static void sayHello() {
    System.out.println("안녕하세요!");
    // return 생략 가능
}
```

## 🧠 정리

|용어|설명|
|---|---|
|매개변수|메소드에 **입력으로 전달하는 값**|
|반환타입|메소드가 **돌려주는 값의 자료형**|
|return|메소드 실행 결과를 **밖으로 전달**하는 키워드|
|void|**반환할 값이 없는 경우** 사용하는 반환 타입|