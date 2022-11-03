## Math 클래스

### Math 클래스

- 수학관련 static 메서드의 집합

### Math 클래스의 메서드

- round() - 소수 첫째 자리에서 **반올림**
    
    ```java
    // 원하는 소수점 아래 세 번째 자리에서 반올림하기
    1. 원래 값에 100을 곱한다.
    90.7552 * 100 -> 9075.52
    
    2. 위의 결과에 Math.round()를 사용한다.
    Math.round(9075.52) -> 9076
    
    3. 위의 결과를 다시 100.0으로 나눈다.
    9076 / 100.0 -> 90.76
    9076 / 100 -> 90
    ```
    
- abs() - 주어진 값의 **절대값**을 반환
    
    ```java
    static double abs(double a)
    static float abs(float f)
    static int abs(int f)
    static long abs(long f)
    
    int i = Math.abs(-10);
    double d = Math.abs(-10.0);
    
    // 결과
    i = 10
    d = 10.0
    ```
    
- ceil() - 주어진 값을 **올림**하여 반환
    
    ```java
    static double ceil(double a)
    
    double d = Math.ceil(10.1);
    double d2 = Math.ceil(-10.1);
    double d3 = Math.ceil(10.000015);
    
    // 결과
    d = 11.0
    d2 = -10.0
    d3 = 11.0
    ```
    
- floor() - 주어진 값을 **버림**하여 반환
    
    ```java
    static double floor(double a)
    
    double d = Math.floor(10.8);
    double d2 = Math.floor(-10.8);
    
    // 결과
    d = 10.0
    d2 = -11.0 // 버림 이기 때문에 더 작은숫자로 바뀜
    ```
    
- max() - 주어진 **두 값을 비교**하여 **큰 쪽**을 반환
    
    ```java
    static double max(double a, double b)
    static float max(float a, float b)
    static int max(int a, int b)
    static long max(long a, long b)
    
    double d = Math.max(9.5, 9.50001);
    double d2 = Math.max(0, -1);
    
    // 결과
    d = 9.50001
    i = 0
    ```
    
- min() - 주어진 **두 값을 비교**하여 **작은 쪽**을 반환
    
    ```java
    static double min(double a, double b)
    static float min(float a, float b)
    static int min(int a, int b)
    static long min(long a, long b)
    
    double d = Math.min(9.5, 9.50001);
    double d2 = Math.min(0, -1);
    
    // 결과
    d = 9.5
    i = -1
    ```
    
- random() - **0.0~1.0 범위의 임의의 double 값을 반환**(1.0은 범위에 포함되지 않음)
    
    ```java
    double d = Math.random();
    int i = (int)(Math.random()*10)+1
    
    // 결과
    0.0 <= d < 1.0
    1 <= i < 11
    ```
    
- rint() - 주어진 double 값과 **가장 가까운 정수값**을 double 형으로 반환.
            단, 두 정수의 정가운데 있는 값(1.5, 2.5, 3.5 등) 은 짝수를 반환
    
    ```java
    double d = Math.rint(1.2);
    double d2 = Math.rint(2.6);
    double d3 = Math.rint(3.5);
    double d4 = Math.rint(4.5);
    
    // 결과
    d = 1.0
    d2 = 3.0
    d3 = 4.0
    d4 = 4.0
    ```
    
- round() - 소수점 첫째자리에서 **반올림**한 정수값(long)을 반환
                 두 정수의 정가운데 있는 값은 항상 큰 정수를 반환
    
    ```java
    long l = Math.round(1.2);
    long l2 = Math.round(2.6);
    long l3 = Math.round(3.5);
    long l4 = Math.round(4.5);
    
    double d = 90.7552;
    double d2 = Math.round(d*100)/100.0;
    
    // 결과
    l = 1
    l2 = 3
    l3 = 4
    l4 = 5
    
    d = 90.7552
    d2 = 90.76
    ```
    

## Wrapper 클래스

- 8개의 기본형을 객체로 다뤄야 할 때 사용하는 클래스
- 내부적으로 기본형(primitive type) 변수를 가지고 있다
    
    ```java
    public final class Integer extends Number implements Comparable {
    	...
    	private int value;
    }
    ```
    
- equals()와 toString()이 오버라이딩 되어 있어서 사용시 주소값이 아닌 객체가 가지고있는 값을 비교한다.

| 기본형 | 래퍼클래스 | 생성자 | 예시 |
| --- | --- | --- | --- |
| boolean | Boolean | Boolean(boolean value)
Boolean(String s) | Boolean b = new Boolean(true);
Boolean b2 = new Boolean(”true”); |
| char | Character | Character(char value) | Character c = new Character(’a’); |
| byte | Byte | Byte(byte value)
Byte(String s) | Byte b = new Byte(10);
Byte b2 = new Byte(”10”); |
| short | Short | Short(short value)
Short(String s) | Short s = new Short(10);
Short s2 = new Short(”10”); |
| int  | Integer | Integer(int value)
Integer(String s) | Integer i = new Integer(100);
Integer i2 = new Integer(”100”); |
| long | Long | Long(long value)
Long(String s) | Long l = new Long(100);
Long l2 = new Long(”100”); |
| float | Float | Float(double value)
Float(float value)
Float(String s) | Float f = new Float(1.0);
Float f2 = new Float(1.0f);
Float f3 = new Float(”1.0f”); |
| double | Double | Double(double value)
Double(String s) | Double d = new Double(1.0);
Double d2 = new Double(”1.0”); |

## Number 클래스

- 모든 숫자 래퍼 클래스의 조상(추상 클래스)
    
<img width="779" alt="image" src="https://user-images.githubusercontent.com/108970153/199735003-e4dea027-9612-4e2e-9232-c242b99f9a91.png">
    
    - BigInteger : long으로도 다룰 수 없는 큰 범위의 정수일때 사용
    - BigDecimal : double로도 다룰 수 없는 큰 범위의 실수일때 사용
- 객체가 가지고 있는 값을 숫자와 관련된 기본형으로 변환하여 반환하는 메서드들을 정의하고 있다.
    
    ```java
    public abstract class Number implements java.io.Serializable {
    	public abstract int intValue();
    	public abstract long longValue();
    	public abstract float floatValue();
    	public abstract double doubleValue();
    
    	public byte byteValue() {
    		return (byte)intValue();
    	}
    
    	public short shortValue() {
    		return (short)intValue();
    	}
    }
    ```
    

## 문자열을 숫자로 변환하기

- 문자열을 숫자로 변환하는 다양한 방법
    
    
    | 문자열 → 기본형 | 문자열 → 래퍼클래스 |
    | --- | --- |
    | byte b = Byte.parseByte(”100”);
    short s = Short.parseShort(”100”);
    int i = Integer.parseInt(”100”);
    long l = Long.parseLong(”100”);
    float f = Float.parseFloat(”3.14”);
    double d = Double.parseDouble(”3.14”); | Byte b = Byte.valueOf(”100”);
    Short s = Short.valueOf(”100”);
    Integer i = Integer.valueOf(”100”);
    Long l = Long.valueOf(”100”);
    Float f = Float.valueOf(”3.14”);
    Double d = Double.valueOf(”3.14”); |
    
    ```java
    int i = new Integer("100").intValue(); // floatValue(), longValue(), ...
    int i2 = Integer.parseInt("100"); // 주로 이 방법을 많이 사용
    Integer i3 = Integer.valueOf("100");
    ```
    
- n진법의 문자열을 숫자로 변환하는 방법
    
    ```java
    int i4 = Integer.parseInt("100", 2); // 100(2) -> 4
    int i5 = Integer.parseInt("100", 8); // 100(8) -> 64
    int i6 = Integer.parseInt("100", 16); // 100(16) -> 256
    int i7 = Integer.parseInt("FF", 16); // 100(16) -> 255
    // int i8 = Integer.parseInt("FF"); // 기본으로 10진수로 판별해 NumberFormatException발생
    ```
    

## 오토박싱 & 언박싱

- 기본형과 참조형 간의 자동 변환
- JDK 1.5 이전에는 기본형과 참조형간의 연산이 불가능
- 컴파일러가 오토박싱&언박싱을 해주기 때문에 가능해짐
    
    ```java
    int i = 5;
    Integer iObj = new Integer(7);
    
    int sum = i + iObj; // JDK1.5부터 가능
    ```
    
    | 컴파일 전의 코드 | 컴파일 후의 코드 |
    | --- | --- |
    | int i = 5;
    Integer iObj = new Integer(7);
    
    int sum = i + iObj; | int i = 5;
    Integer iObj = new Integer(7);
    
    int sum = i + iObj.intValue(); |
- 기본형의 값을 객체로 자동변환하는 것을 오토박싱, 그 반대는 언박싱
    
    ```java
    ArrayList<Integer> list = new ArrayList<Integer>(); // ArrayList에는 객체만 저장가능
    list.add(10); // 오토박싱. 10 -> new Integer(10)
    // list.add(new Integer(100)); // JDK1.5 이전에는 이렇게 사용했음
    
    int value = list.get(0); // 언박싱. new Integer(10) -> 10
    // int i = list.get(0).intValue(); // intValue()로 Integer를 int로 변환
    ```
    
    ```java
    class Ex9_16 {
    	public static void main(String[] args) {
    		int i = 10;
    
    		// 기본형을 참조형으로 형변환(형변환 생략가능)
    		Integer intg = (Integer)i; // Integer intg = Integer.valueOf(i);
    		Object obj = (Object)i; // Object obj = (Object)Integer.valueOf(i);
    
    		Long lng = 100L; // Long lng = new Long(100L);
    
    		int i2 = intg + 10; // 참조형과 기본형간의 연산 가능
    		long l = intg + lng; // 참조형 간의 덧셈도 가능
    
    		Integer intg2 = new Integer(20);
    		int i3 = (int)intg2; // 참조형을 기본형으로 형변환도 가능(형변환 생략가능)
    	}
    }
    ```
