# Spring_mvc_drill

## Servlet 을 통한 request, response

### request 3가지 방식
 * HTML-form
 * request parameter
 * HTTP API

## Servlet, JSP의 MVC 패턴 적용
  * v1: FrontController 객체를 통한 servlet 요청 컨트롤, Controller 분리
  * v2: MyView 객체를 이용한 view 처리 -> MyView 객체의 render()를 통해서 모든 Controller에서 view를 일관되게 처리
  * v3: 
      * servlet(request, response)를 종속성 제거 -> ModelView 객체를 통해 데이터를 전달
      * 반복적인 view 이름 제거 -> 논리 이름만 사용
      * controller 로직의 단순화 -> FrontController의 처리가 늘어남


## Spring MVC framwork 직접 만들기

## Request / Response / @annotation의 이해
### Request
* @RequestMapping: 모든 method의 url 매핑
* @GetMapping: @RequestMapping(method=GET)
* @PostMapping: @RequestMapping(method=POST)
* @PatchMapping: @RequestMapping(method=PATCH)
* @DeleteMapping: @RequestMapping(method=DELETE)
* @RequestParam: Get, Post에 의한 쿼리
   * name option: method 인자와 parameter의 value 일치 시, 생략
   * required option: default=true -> false 설정 시, 요청이 없는 함수의 인자는 null
   * default option: 요청이 null일 경우, 함수의 인자를 default로 채움 -> required에 상관이 없어짐
* @ModelAttribute: paramter -> Object binding
   * not primitive type(int, Interger, String), argument resolver

### Response
* ResponseEntity<>(http message, http status): HTTP header, body 정보를 가지는 객체
   * StringHttpConverter를 통한 HTTP message -> String -> HTTP Message
* @ResponseBody: return value는 view가 아닌 HTTP message를 제공
* @RestController: @Controller + @ResponseBody
* @ResponseStatus: @ResponseBody를 이용한 return시 상태 코드의 부재를 해결 -> 정적인 상태만 제공


# Thymeleaf Basic

## how to import thymeleaf in HTML file
 * <html xmlns:th="http://www.thymeleaf.org">
 * <html xmlns:th="http://w3.thymeleaf.org">
 * <html xmlns:th="http://thymeleaf.org">
 
## th:text vs th:utext
 * thymeleaf use escape text as a default
 * ex: < -> &lt
