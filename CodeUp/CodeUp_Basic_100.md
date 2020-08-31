전체 풀이보다는 '아, 이런게 있었지'같은게 나올때 한번씩 쓰려고 합니다.
후반가면 더 많이 나올거같기도 하고...

------------------------------------------------------

# CodeUP 기본100제(JAVA)

### String출력시 작은따옴표 밑 큰따옴표 출력
```
:: 스트링 자체에서 위의 특수문자입력을 위해서는 백슬래시를 붙여줘야 합니다.
:: Java를 기준으로, 아래와 같이 작성합니다.
```
```Java
    System.out.pringln("\'HelloWorld\'");
```
```
:: Java에서는 Javascript에서 사용되는 백틱을 이용한 문자열은 지원하지 않았습니다.(버전에 따라 다를수도 있지만, 제 이클립스에서 안되었습니다)
:: 마찬가지로 백슬래시 출력을 위해서는 백슬래시를 붙여줘야 합니다.
```
```Java
	System.out.println("\"C:\\Download\\hello.java\"");
```

### 유니코드 출력
```
:: 유니코드를 출력하는 방법은 백슬래시와 u를 입력하고, 코드표를 참조하여 해당 특수문자를 표현합니다.
```
```java
		System.out.println("\u250C\u252C\u2510");
		System.out.println("\u251C\u253C\u2524");
		System.out.println("\u2514\u2534\u2518");
```

### 실수 출력(반올림)
```
:: 소수점 n번째자리에서 반올림 하여 출력 --> String.Format이용합니다.
:: %.2f라면 소수점 세번째 자리에서 반올림하여, 두번째자리수까지 출력합니다.
```
```java
    Scanner sc = new Scanner(System.in);
    float a = sc.nextFloat();
	System.out.println(String.format("%.2f", a));
```

### split
```
:: 평소에 아무생각없이 사용했던 String의 함수였는데 "."문자로 split이 되지않아서 찾아보게 되었습니다.
:: 파라미터이름으로 regex라고 되어있어서 정규표현식이겠구나 생각은 햇었는데 기존에 "."을 문자 자체로 인식하기 위해서는 "\."으로 알고있었습니다.
:: 아래와 같이 "\\."으로 작성해야 인식됩니다.
```
```java
    Scanner sc = new Scanner(System.in);
    String temp = sc.nextLine();
    String arr[] = temp.split("\\.");
```

### join
```
:: 단순히 2020.08.31이라는 문자열을 31-08-2014로 바꾸는 문제였습니다.
:: 그냥 split으로 나눠서 하나하나 String을 +연산하면 될거같긴한데 join을 써보자, 라고 생각했습니다.
:: 사용법은 String.join("넣을 구분자", "넣을 문자열 1", "넣을 문자열 2" ...)입니다.
```
```java
    String str = sc.nextLine();
	String arr[]  = str.split("\\.");
	String res = String.join("-", arr[2],arr[1],arr[0]);
```

### unsignedInt 
```
:: 일반적으로 C에서 사용하던것처럼 unsignedInt를 java에서는 사용할 수 없습니다.
:: 대신에 long을 사용하여 표현이 가능하지만 음수부분역시 포함되게 됩니다.
:: int	-2147483648 ~ 2147483647
:: long	-9223372036854775808 ~ 9223372036854775807
:: C언어의 longlong int와 동일한 범위.
:: 하지만 Java8에 들어서면서 unsignedInt를 사용할 수 있는 메서드가 추가되었다고 하며 방법은 아래와 같습니다.
```
```java
		String str = sc.nextLine();//unsignedInt범위의 값
		int vInt = Integer.parseUnsignedInt(str);
		System.out.println(vInt);//-1
		String sInt = Integer.toUnsignedString(vInt);
		System.out.println(sInt);//unsignedInt값.
```

### Format
```
:: %d: 정수
:: %f: 실수
:: %o: 8진수
:: %x: 16진수_____%X로 사용할 경우 대문자로 표기됨.
```

### 10진수, 2진수, 8진수, 16진수 변환
```
:: JAVA에서는 Integer클래스를 통해 진법변환을 쉽게 할 수 있습니다.
:: 10진수에서 변환. 
```
```java
    Scanner sc = new Scanner(System.in);
    String insert = sc.nextLine();
    String binNum = Integer.toBinaryString(insert);
    String octNum = Integer.toOctalString(insert);
    String hexNum = Integer.toHexString(insert);
```
```
:: 2진수, 8진수, 16진수에서 변환.
```
```java
    Scanner sc = new Scanner(System.in);
    String insert = sc.nextLine();
    int binNum = Integer.valueOf(insert, 2);
	int octNum = Integer.valueOf(insert, 8);
    int hexNum = Integer.valueOf(insert, 16);
```
```
:: 예를들어 16진수를 받아 8진수로 만든다면 아래와 같이 작성할 수 있습니다.
```
```java
    int hexNum = Integer.valueOf(insert, 16);
	String octNum = Integer.toOctalString(hexNum);
```
