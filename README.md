#Proman

## 개발 기간

- 9월 14일 (수) ~12월 15일 (일)
- 10월 31일 (수) 중간고사
- 12월 11일 (수) 기말고사

## 개발 환경
- Spring_Boot
- visual studio code

## 작성한 주요 코드 소개

### config

#### SecurityCofig.java
````package com.example.demo.config;

 import org.springframework.context.annotation.Bean;
 import org.springframework.context.annotation.Configuration;
 import org.springframework.security.config.annotation.web.builders.HttpSecurity;
 import org.springframework.security.config.annotation.web.configuration.EnableWebSecurity;
 import org.springframework.security.crypto.bcrypt.BCryptPasswordEncoder;
 import org.springframework.security.crypto.password.PasswordEncoder;
 import org.springframework.security.web.SecurityFilterChain;

 @Configuration // 스프링 설정 클래스 지정, 등록된 Bean 생성 시점
 @EnableWebSecurity // 스프링 보안 활성화

 public class SecurityConfig { // 스프링에서 보안 관리 클래스

    @Bean // 명시적 의존성 주입 : Autowired와 다름
// 5.7버전 이전 WebSecurityConfigurerAdapter 사용
public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {
    http
    .headers(headers -> headers
    .addHeaderWriter((request, response) -> {
        response.setHeader("X-XSS-Protection", "1; mode=block"); // XSS-Protection 헤더설정
    })
    )
    // .csrf(withDefaults())
    .csrf(csrf -> csrf.disable())
    .sessionManagement(session -> session
    .invalidSessionUrl("/session-expired") // 세션만료시이동페이지
    .maximumSessions(1) // 사용자별세션최대수
    .maxSessionsPreventsLogin(true) // 동시세션제한
    );
    // 설정을 비워둠
    return http.build(); // 필터 체인을 통해 보안설정(HttpSecurity)을 반환
}
@Bean // 암호화 설정
public PasswordEncoder passwordEncoder() {
return new BCryptPasswordEncoder(); // 비밀번호 암호화 저장
}    
}







