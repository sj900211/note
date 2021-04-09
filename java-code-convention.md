# Java Code Convention
> Code Convention 이 필요한 이유  
>> - 개발에 소비되는 비용 중 80% 는 유지보수에 쓰여진다.  
>> - 유지보수 개발자와 구축 개발자가 다른 경우가 많다.  
>> - 다른 개발자의 코드를 수정할 때 분석하는 시간이 전체 수정 시간의 80% 를 차지한다.  
>> - 같은 서비스를 개발하는 여러 개발자들이 서로 프로젝트 작성 방법이 다르면 혼란을 줄 수 있다.  
>>
> 위의 이유 외에도 다양한 이유가 존재 한다.  
> 간단하게 요약하자면 개발 **비용 절약**, **유지보수 비용 절약**, **관리 비용 절약** 을 위해서다.  

> **_NOTE_**:
> 이 문서의 예제 코드는 표준이 아니다.  
> 스타일에 관련한 예제이며 코드를 표현하는 예제가 아니다.  
> 예제에서 선택한 선택적 형식 지정은 규칙으로 적용되지 않아야 한다.  
> 
> IDE 는 IntelliJ 를 사용하는 것을 기준으로 작성.  
> 이 문서에 정의되지 않은 항목에 대해서는 다음 링크에서 확인해서 적용한다.  
> [Sun & Oracle Java Code Convention](https://www.oracle.com/java/technologies/javase/codeconventions-contents.html)
> [Google Java Code Convention](https://google.github.io/styleguide/javaguide.html)

## 용어 참고
`class`는 `ordinary class`, `enum class`, `interfacec` 또는 `@interface` 을 의미하기 위해 포괄적으로 사용  
`member` 라는 용어는 중첩 된 클래스, 필드, 메서드 또는 생성자를 의미하기 위해 포괄적으로 사용  
`comment` 이라는 용어는 항상 구현 주석을 의미  
`documentation comments` 이라는 문구를 사용하지 않고 `Javadoc` 이라는 일반적인 용어를 사용  

- ## 들여쓰기
> 들여쓰기는 2 개의 빈 칸 `space` 를 들여쓰기 단위로 사용한다.  
> ``` java
> public void handlerExample() {
> ··System.out.println("Example");
> }
> ```
> 체인 메서드를 사용하는 중에 줄을 나누거나 소괄호 `()` 안에서 줄을 나눌때  
> 또는 문자에서 줄을 나누거나 Statements 중 줄을 나눌때  
> 줄을 나뉜 후 2 번의 들여쓰기 `8 개의 빈칸` 를 사용한다.
> ``` java
> public void handlerExample() {
> ··System.out
> ······.println(
> ··········"Hello"
> ··············+ " "
> ··············+ "World"
> ······);
> }
> ```
- ## 한 줄의 길이
> 피치 못할 사정을 제외한 기본적인 상황에서는  
> 한 줄의 길이는 100 자를 넘지 않는다.  
- ## 줄 나누기 & 띄어 쓰기
> 하나의 식이 한 줄에 들어가지 않는 경우 다음과 같은 규칙에 따라 줄을 나눈다.  
>> - ### Dot `.`
>>> 문자 데이터를 작성할 때에는 `.` 후 줄을 나눈다.  
>>> 체인 메서드를 작성할 때에는 `.` 전 줄을 나눈다.  
>> 문자 데이터를 작성할 때에는 `.` 후 띄어쓴다.  
>>> ``` java
>>> public void handlerExample() {
>>>   System.out
>>>       .println(
>>>           "Hello. "
>>>               + "and"
>>>               + "Welcome"
>>>       );
>>> }
>>> ```
>> - ### Comma `,`
>>> `,` 후 줄을 나눈다.  
>>> `,` 후 한 칸 띄어쓴다.  
>>> ``` java
>>> public void handlerExample(String firstName,
>>>     String middleName, String lastName) {
>>>   System.out
>>>       .println(
>>>           "Hello, "
>>>               + firstName
>>>               + middleName
>>>               + lastName
>>>       );
>>> }
>>> ```
>> - ### Arithmetic & Comparison Operations `+` `-` `*` `/` `%` `==` `!=` `<` `>` `<=` `>=` `&&` `||` `!`
>>> `+` 전 줄을 바꾼다.  
>>> 줄을 바꾸지 않았을 때는 `+` `&&` `||` 전후로 띄어쓴다.  
>>> 줄을 바꾸었을 때는 `+` 후 줄을 나눈다.  
>>> `!` 전후로 띄어쓰지 않는다.
>>> 줄을 바꾸었을 때는  `&&` `||` 전 줄을 나눈다.  
>>> 기본적으로 `-` `*` `/` `%` `==` `!=` `<` `>` `<=` `>=` `!` 사이에는 줄을 나누지 않는다.  
>>> 피치못할 이유가 생겼을 때에는 `-` `*` `/` `%` `=` `==` `!=` `<` `>` `<=` `>=` `!` 전 줄을 나눈다.   
>>> ``` java
>>> public void handlerExample() {
>>>   System.out
>>>       .println(
>>>           "Hello." + "and"
>>>               + "Welcome"
>>>       );
>>> }
>>> ```
>> - ### Semicolon `;`
>>> `;` 후 줄을 바꾼다.  
>>> `;` 후 띄어쓴다.  
>>> ``` java
>>> public void handlerExample(String key) {
>>>   for (int i = 0; i < 10; i++) {
>>>     String count = i + 1;
>>> 
>>>     System.out.println(count);
>>>   }
>>> }
>>> ```
>> - ### Colon `:`
>>> `:` 후 줄을 바꾼다.  
>>> `:` 후 띄어쓴다.  
>>> ``` java
>>> public void handlerExample(String key) {
>>>   switch (key) {
>>>     case "HELLO":
>>>       System.out.println("key: HELLO");
>>>       break;
>>>     default:
>>>       System.out.println("default");
>>>   }
>>> }
>>> ```
>> - ### Double Colon `::`
>>> 메서드 참조에서 `::` 은 줄바꾸기와 띄어쓰기를 하지 않는다.  
>>> ``` java
>>> public void handlerExample(String value) {
>>>   Optional.ofNullable(value)
>>>       .orElseThrow(Exception::new)
>>> }
>>> ```
>> - ### Ternary operator `?` `:`
>>> 삼항식에서 `?` 와 `:` 모두 전 줄을 바꾼다.  
>>> 삼항식에서 `?` 와 `:` 모두 전후로 띄어쓴다.  
>>> ``` java
>>> public void handlerExample(String value) {
>>>   boolean exists = !StringUtils.hasLength(value) ? false : true;
>>>   String result = exists
>>>       ? value
>>>       : "Not Found"
>>> }
>>> ```
>> - ### Statements
>>> Statements 에서 사용되는 `()` 는 전후로 띄어쓴다.  
>>> Statements 에서 사용되는 `(` 전에는 줄을 나누지 않는다.  
>>> Statements 에서 사용되는 `{` 전 띄어쓴다.  
>>> Statements 에서 사용되는 `{` 전에는 줄을 나누지 않는다.  
>>> Statements 에서 사용되는 `}` 전후로 띄어쓰지 않는다.  
>>> Statements 에서 사용되는 `}` 전 줄을 나눈다.  
>>> Statements 사이에 사용되는 `}` 의 경우 후 띄어쓴다.  
>>> Statements 에서 사용되는 `->` 는 전후로 띄어쓴다.  
>>> Statements 에서 사용되는 `->` 후 줄을 나눈다.  
>>> ``` java
>>> public void handlerExample(List<HashMap<String, Integer>> data, Integer multiply) {
>>>   List<Integer> list = data.stream()
>>>       .filter(item -> !isNull(item.get("count")))
>>>       .map(item -> {
>>>         Integer count = item.get("count");
>>>         Integer result = count * multiply;
>>> 
>>>         return result;
>>>       }).collect(Collectors.toList());
>>> 
>>>   int max = list.size();
>>>   int oddSum = 0;
>>>   int evenSum = 0;
>>> 
>>>   for (int i = 0; i < max; i++) {
>>>     if (i % 2 == 0) {
>>>       evenSum += list.get(i);
>>>     } else {
>>>       oddSum += list.get(i);
>>>     }
>>>   }
>>> 
>>>   System.out.println("ODD SUM: " + oddSum);
>>>   System.out.println("EVEN SUM: " + evenSum);
>>> }
>>> ```
>> - ### Method
>>> Method 에서 사용되는 `(` 전에는 띄어쓰지 않는다.  
>>> Method 에서 사용되는 `)` 후에 띄어쓴다.  
>>> Method 에서 사용되는 `{` 전 띄어쓴다.  
>>> Method 에서 사용되는 `{` 전에는 줄을 나누지 않는다.  
>>> Method 에서 사용되는 `}` 전후로 띄어쓰지 않는다.  
>>> Method 에서 사용되는 `}` 전 줄을 나눈다.  
>>> ``` java
>>> public void handlerExample() {
>>>   System.out.println("Example");
>>> }
>>> ```
- ## 배치 & 공백
> - ### Class
>> Class 첫 라인은 공백으로 작성한다.  
>> ``` java
>> public class Example {
>> 
>>   public void handlerExample() {
>>     System.out.println("Example");
>>   }
>> }
>> ```
> - ### Method
>> Method 첫 라인은 공백으로 작성하지 않는다.  
>> ``` java
>> public void handlerExample() {
>>   System.out.println("Example");
>> }
>> ```
> - ### Logic
>> 로직은 크게 세 부분으로 구분할 수 있다.  
>> **_선언_**, **_처리_**, **_반환 또는 결과_**  
>> 각 부분은 공백으로 분리되어 있어야 한다.  
>> 여러 로직이 한 메서드에 있을 경우 로직 사이는 공백으로 분리되어 있어야 한다.  
>> ``` java
>> public Integer handlerExample(Integer value, Integer multiply, Integer division) {
>>   int num = Optional.ofNullable(value).orElse(0);
>> 
>>   if (num == 0) {
>>     return num;
>>   }
>> 
>>   int result = 0;
>> 
>>   if (num < 10) {
>>     result = num * multiply;
>>   } else if (num < 100) {
>>     result = num / division;
>>   } else {
>>     result = num % division;
>>   }
>> 
>>   return result;
>> }
>> ```
- ## 주석
> - ### JavaDocs
>> **_WARNING_**: 이 문서는 IDE 는 IntelliJ 를 사용하는 것을 기준으로 작성되었다.  
>> 그렇기 때문에 IntelliJ 에서 적용하는 방법만 작성한다.
>>
> JavaDocs 은 Template 을 Git 에 공유되어 있으므로 다운받아 적용할 수 있다.  
> 적용 순서는 다음과 같다.  
>> 1. IntelliJ 에서 `JavaDoc` 플러그인을 설치한다.
>> 2. Git 에서 [intellij-javadocs.xml](https://gitlab.emotion.co.kr/emotion-ct1-group/document/convention/blob/master/resources/java-docs/intellij-javadocs.xml) 파일을 다운받는다.
>> 3. 파일을 열고 `{{name}}` 부분을 개발자 본인의 이름으로 치환한다.
>> 4. IntelliJ 프로젝트 안에 있는 `.idea` 디렉토리로 파일을 이동한다.
>>
>> **_NOTE_**: 자동으로 JavaDocs 가 생성되지만 `@implNote` 항목은 직접 작성해야하기 때문에 **잊지말고 꼭 작성해주자.**  
>>
> - ### 구문 주석
>> - #### Block
>>> Block 주석은 메서드 안에서 자료 구조, 알고리즘에 대한 설명을 제공할 때 작성한다.  
>>> Block 주석은 각각의 알고리즘이 시작되기 전에 작성한다.  
>>> ``` java
>>> public void handlerExample(String value) {
>>>   /*
>>>    * parameter 로 넘어온 값이
>>>    * null 일 경우 Exception 을 발생시킨다.
>>>    * 
>>>    * TODO: Exception 종류에 대한 논의 필요
>>>    */
>>>   String result = Optional.ofNullable(value)
>>>       .orElseThrow(Exception::new)
>>> }
>>> ```
>> - #### Single
>>> Block 주석과 의미와 작성방법이 같다.
>>> Single 주석은 뒤따라 오는 코드와 같은 들여쓰기를 해서 작성한다.
>>> 줄을 나누게 되면 Block 주석으로 변경한다.
>>> ``` java
>>> public String handlerExample(String name) {
>>>   /* parameter 로 넘어온 값이 null 일 경우 Exception 을 발생시킨다. */
>>>   String result = Optional.ofNullable(name)
>>>       .orElseThrow(Exception::new)
>>> 
>>>   // result 값 전에 Welcome 문자를 붙여 반환
>>>   return "Welcome " + result;
>>> }
>>> ```
>> - #### Trailing
>>> Trailing 주석은 코드 끝에 작성한다.
>>> 한 줄 코드에 대한 설명을 작성한다.
>>> 줄을 나누게 되면 Block 주석으로 변경한다.
>>> ``` java
>>> public String handlerExample(String name) {
>>>   String result = Optional.ofNullable(name)
>>>       .orElseThrow(Exception::new) /* null 일 경우 Exception 을 발생시킨다. */
>>> 
>>>   return "Welcome " + result; // result 값 전에 Welcome 문자를 붙여 반환
>>> }
>>> ```
- ## Naming Rule
> - ### Package
>> Package 이름은 명사를 사용해서 작성한다.  
>> 하나의 단어로 이름 짓는 것을 기본으로 한다.  
>> 피치못할 이유로 두 단어의 조합으로 이름 지을때는 all lowercase 규칙으로 작성한다.  
>> lower-hypen-case 이나 lower_snake_case 로 작성하지 않는다.
> - ### Class
>> Class 이름은 UpperCamelCase 으로 작성한다.
> - ### Method
>> Method 이름은 lowerCamelCase 로 작성한다.
> - ### Variable
>> Variable 이름은 lowerCamelCase 로 작성한다.  
>> 단 **Constant** `상수` 의 경우 UPPER_SNAKE_CASE 작성한다.
