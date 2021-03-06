## String타입, undefined타입
<br/>

> 문자열 (= String)

- 문자열은 따옴표 안에 들어가있는 데이터.

      var myName = "효니";
      var myAge = '34';
      var myJob = `퍼블리셔`;

      var sentence = "\"너 자신을 알라\" - 소크라테스"; // escape
<br/>      

> 문자열을 조작하는 방법

    a) 문자열 합성
          console.log( "효니" + "님 안녕하세요" );
          var name = "효니";
          name += "님 안녕하세요";
        
          b) 문자열의 길이(=글자수)를 구하기
          문자열변수.length // 도출되는 결과는 Number타입의 데이터
        
      c) 문자열에서 부분문자열을 추출하기
         c-1) 문자열변수.substr( from, length ) 
              문자열변수에 들어있는 전체문자열중에서 from위치부터 시작하여 length길이만큼의 부분문자열을 추출한다.
              from위치는 문자열의 맨 첫글자를 0 으로 쳐서 수를 세어간 위치를 나타낸다.

    
         c-2) 문자열변수.substring( from, to )
              문자열변수에 들어있는 전체문자열중에서 from위치부터 시작하여 (to-1)위치까지의 부분문자열을 추출한다.

    
         c-3) 문자열변수.slice( from, to )
              문자열변수에 들어있는 전체문자열중에서 from위치부터 시작하여 (to-1)위치까지의 부분문자열을 추출한다.
              to위치는 생략할 수 있다. 그 경우, 문자열의 from위치부터 시작하여 문자열의 끝까지를 추출한다.
              to위치가 생략되고, from위치가 음수인 경우, 문자열의 끝에서부터 from갯수만큼의 글자를 추출한다.
    

      d) 문자열에서 부분문자열을 찾아서 시작위치를 구하기
         문자열변수.indexOf( 찾고자하는 부분문자열 )
         만일 전체문자열에서 찾고자하는 부분문자열이 존재하지 않으면 -1 이 도출된다.

    
      e) 문자열에서 부분문자열을 찾아서 다른 문자열로 치환하기
         문자열변수.replace( from, to )
         전체문자열에서 from문자열을 찾아서 to문자열로 치환한 새로운 문자열을 만든다.
         * 전체문자열에서 from문자열이 여러번 등장할 경우, 맨 처음 등장하는 from문자열만 치환된다. *  

<br>

- str_text.replace(/찾을 문자열/gi, "변경할 문자열") 
  <br>

      var test = "가나다라 마바사 가나라마사";
      var result = test.replace( /가/gi, '하');

      console.log(result); // '하나다라 마바사 하나라마사'

      여기서 꼭 알아야 될 점은 나누기(/)표시안에 넣는 텍스트의 따옴표는 없어야 한다는 점입니다. 그리고 뒤의 gi는 다음을 의미합니다.

       g : 전체 모든 문자열을 변경 global
       i : 영문 대소문자를 무시, 모두 일치하는 패턴 검색 ignore

<br>

   * 사용자로부터 문자열을 입력받기
      var name = prompt("이름을 입력하세요");

<br/> 


      
> 묵시적(Implict) 형 변환(Type Casting)


    console.log( 5 + "name" ); // 5name
  
    위와 같이 Number타입 데이터와 String타입 데이터가 +연산자에 섞여서 사용될 경우,
    Number타입의 데이터가 String타입으로 일시적으로 변환되서 결과적으로는 String타입+String타입으로 취급된다.
  
    console.log( 5 * "효니" ); //NaN 
    console.log( 5 * "30" ); //150
  
    +연산자가 아닌 다른 연산자에 Number타입 데이터와 String타입 데이터를 섞어서 사용할 경우,
    NaN이 도출된다. 단, 문자열이 마치 숫자로 취급할 수 있을것처럼 생긴 경우에 한하여 String타입이 Number타입으로 일시적으로 변환되는 형 변환이 일어난다.
  
    // 효니효니효니효니
    // NaN
    // "5효니"

<br/>

>명시적(Explict) 형 변환

     console.log( 10 + "20" ); // 1020

    String타입 데이터를 Number타입 데이터로 형 변환 하고자 할 때, parseInt(문자열) -> 소수점이 없는 정수만 변환 가능
    String타입 데이터를 Number타입 데이터로 형 변환 하고자 할 때, parseFloat(문자열) -> 소수점을 포함한 실수를 변환 가능

    parseInt("3.141592");  ->   3
    parseFloat("3.141592"); ->  3.141592

    Number타입 데이터를 String타입 데이터로 형 변환 하고자 할 때, 변수.toString()


<br/>

 > 특정상수

      Number타입     1 2 1.5 ......
      String타입     "가" "나" ......
      undefined타입  undefined
    
      변수를 만들어놓고 아무 데이터도 대입하지 않으면 기본으로 들어가있는 데이터.
      변수가 비어있음을 나타낼 때 의도적으로 변수에 대입하기도 한다.
    
      null은 변수가 비어있음을 나타낸다는 점에서 undefined와 유사해보이지만, null의 데이터타입은 객체(object)다. 