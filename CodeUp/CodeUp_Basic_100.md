전체 풀이보다는 '아, 이런게 있었지'같은게 나올때 한번씩 쓰려고 합니다.
후반가면 더 많이 나올거같기도 하고...

------------------------------------------------------

# CodeUP 기본100제

### String출력시 작은따옴표 밑 큰따옴표 출력
:: 스트링 자체에서 위의 특수문자입력을 위해서는 백슬래시를 붙여줘야 합니다.
:: Java를 기준으로, 아래와 같이 작성합니다.
```Java
    System.out.pringln("\'HelloWorld\'");
```
:: Java에서는 Javascript에서 사용되는 백틱을 이용한 문자열은 지원하지 않았습니다.(버전에 따라 다를수도 있지만, 제 이클립스에서 안되었습니다)
:: 마찬가지로 백슬래시 출력을 위해서는 백슬래시를 붙여줘야 합니다.
```Java
	System.out.println("\"C:\\Download\\hello.java\"");
```

### 유니코드 출력
:: 유니코드를 출력하는 방법은 백슬래시와 u를 입력하고, 코드표를 참조하여 해당 특수문자를 표현합니다.
```java
		System.out.println("\u250C\u252C\u2510");
		System.out.println("\u251C\u253C\u2524");
		System.out.println("\u2514\u2534\u2518");
```

### 실수 출력(반올림)
:: 소수점 n번째자리에서 반올림 하여 출력 --> String.Format이용합니다.
:: %.2f라면 소수점 세번째 자리에서 반올림하여, 두번째자리수까지 출력합니다.
```java
    Scanner sc = new Scanner(System.in);
    float a = sc.nextFloat();
	System.out.println(String.format("%.2f", a));
```

### split
:: 평소에 아무생각없이 사용했던 String의 함수였는데 "."문자로 split이 되지않아서 찾아보게 되었습니다.
:: 파라미터이름으로 regex라고 되어있어서 정규표현식이겠구나 생각은 햇었는데 기존에 "."을 문자 자체로 인식하기 위해서는 "\."으로 알고있었습니다.
:: 아래와 같이 "\\."으로 작성해야 인식됩니다.
```java
    Scanner sc = new Scanner(System.in);
    String temp = sc.nextLine();
    String arr[] = temp.split("\\.");
```