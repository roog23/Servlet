# Servlet
Servlet 정리
Servlet
=
웹 기반의 요청에 대한 동적인 처리가 가능한 하나의 클래스   
클라이언트의 요청을 처리하고, 결과를 반환하는 Servlet 클래스의 구현 규칙을 지킨 자바 웹 프로그래밍   
자바 코드 속에 HTML 코드가 들어가는 형태

Servlet 특징
-
>1. 클라이언트의 요청에 대해 동적으로 작동하는 웹 어플리케이션 컴포넌트   
>2. html을 사용하여 요청에 응답    
>3. java thread를 이용하여 동작   
>4. MVC 패턴에서 Controller로 이용   
>5. HTTP 프로토콜 서비스를 지원하는 javax.servlet.http.HttpSevlet클래스를 상속   
>6. UDP보다 처리 속도가 느림   
>7. HTML 변경시 Servlet을 재 컴파일해야하는 단점이 존재   

Servlet 동작
-
<img width="410" alt="Servlet" src="https://user-images.githubusercontent.com/64243394/106106778-63571f80-6189-11eb-9d3d-ce4bcdee8c38.png">

1. 클라이언트가 URL을 입력하면 HTTP Request가 Servlet Container로 전송   
2. 요청을 받은 Servlet Container는 HttpServletRequest, HttpServletResponse 객체를 생성   
3. web.xml을 기반으로 클라이언트가 요청한 URL이 어느 서블릿에 대한 요청인지 찾음   
4. 해당 서블릿에서 sevice 메소드를 호출한 후 클라이언트 GET,POST여부에 따라 doGet(), doPost() 를 호출   
5. doGet(), doPost() 메소드는 동적 페이지를 생성한 후 HttpServletResponse 객체에 응답을 보냄   
6. 응답이 끝나면 HttpServletRequest, HttpServletResponse 객체를 소멸   

Servlet Container
=
서블릿을 관리해주는 컨테이너    
클라이언트의 요청을 받아주고 응답할 수 있게 웹 서버와 소켓으로 통신   

Servlet Container 역할
-
>1. 웹 서버와 통신 지원   
>2. 서블릿 생명주기 관리   
>3. 멀티쓰레드 지원 및 관리   
>4. 선언적인 보안 관리   

Servlet 생명주기
-
<img width="358" alt="Servlet lifetime" src="https://user-images.githubusercontent.com/64243394/106108622-d95c8600-618b-11eb-9ad5-76e5e0c5fdf9.png">

1. 초기화 단계
>init() - 서블릿 요청 시 처음 한번만 호출   
>서블릿 생성 시 초기화 작업을 주로 수행   
2. 작업 단계
>service() - 서블릿 요청 시 매번 호출 (반복)   
>실제로 클라이언트가 요청하는 작업을 수행   
3. 종료 단계
>destroy() - 서블릿 기능을 수행하고 메모리에서 소멸시킬 때 한번만 호출   
>서블릿의 마무리 작업을 주로 수행   
