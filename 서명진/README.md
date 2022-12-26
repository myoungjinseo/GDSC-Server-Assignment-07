# 22-23 Server Assignment 7

스프링 시큐리티 과제

## 주의할 점

1. fork 후 기본 파일들을 건들면 안되용
2. 프로젝트명을 꼭 자기이름으로(ex - 한현수)로 해주세요.
3. PR 보낼 때 설명과 레퍼런스 출처를 적어주세요.

Authenticationfilter = request 인증, 인가 진행해주는 부분
UsernamePasswordAuthenticationToken = 토큰 기반 인증 방식을 처리해주는 부분
AuthesticationManager = 
AuthenticationProvider = authentication을 수행하는 주체
UserDetialService = 인증과 관련된 일을 처리할 때 User의 정보를 가져오는 부분



1.request가 들어오면 이를 Authenticationfilter가 낚아챈다.
2.Authenticationfilter에서는 이를 UsernamePasswordAuthenticationToken에 넘겨주어
3.Authentication 객체로 만든다.
4.이렇게 만들어진 Authentication객체를 AuthenticationManager에 넘겨준다.
5.AuthentciationManager는 AuthenticationProvider를 호출하여 이러한 Authentication을 처리하게 한다.
6.AuthenticationProvider는 UserDetailService를 이용해서 Authentication 처리를 한다.
7.처리하게 되면 AuthenticationToken이 생성되고 이를 AuthenticationProvider에 넘겨준다.
8.AuthenticaitonProvider는 이를 이용해서 User 객체를 만들고 이를 이용해서 Authenticaiton 객체 중 인증이 성공한 Authentcation객체를 생성하고 이를 반환한다.
9.AuthenticaitonManager는 이를 AuthenticationFilter에 넘겨준다.
10.AuthenticationFilter는 이를 SecurityContext에 등록하게 된다.
