# **간단한 servlet 구현해보기**

~~~java
// URL에 매핑
@WebServlet("/hello")
// HTTP 요청을 처리
public class HelloServlet extends HttpServlet {

    @Override
    // GET 메서드를 처리
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        response.setContentType("text/html");
        response.getWriter().write("<h1>Hello, Servlet!</h1>");
    }
}
~~~

### Servlet으로 알 수 있었던 점
@WebServlet을 사용해 HTTP 요청, 응답을 직접 다루어야한다는 것을 알았습니다.
~~~text
클라이언트 요청 → Tomcat → Servlet 실행 → 응답 반환

~~~

#### Spring MVC
자동으로 DispatcherServlet을 설정하고 어노테이션을 통해 코드가 간결해집니다.
~~~text
클라이언트 요청 → DispatcherServlet → 컨트롤러 → 서비스 → 응답 반환
~~~
