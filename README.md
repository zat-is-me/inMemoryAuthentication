# InMemory Authentication Using username and password
This application is build on Spring Boot 3.2.3


1. Create SecurityFilterChain Bean in Config class and implement filtration to secure the end points in this bean.

        @Bean
        SecurityFilterChain defaultSecurityFilterChain(HttpSecurity httpSecurity) throws Exception {
        
          httpSecurity.csrf(csrf -> csrf.disable())
                       .authorizeHttpRequests(auth -> auth
                            .requestMatchers("/api/v1/register").permitAll()
                            .requestMatchers("/api/v1/myAccount").authenticated())
                       .httpBasic(withDefaults());
           
                 return httpSecurity.build();
           }

1. Create InMemoryUserDetailsManager bean

     
     @Bean
     public InMemoryUserDetailsManager userDetailsService() {
          UserDetails user = User.withUsername("ahmed")
          .username("ahmed")
          .password("password")
          .authorities("read")
          .build();
          return new InMemoryUserDetailsManager(admin, user);
     }`

2. Then create PasswordEncoder bean


     @Bean
     public PasswordEncoder passwordEncoder() {
          return NoOpPasswordEncoder.getInstance();
      }     


Linkedin Profile:
     https://www.linkedin.com/in/tatekahmed/   
    
