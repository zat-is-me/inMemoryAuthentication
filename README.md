# InMemory Authentication Using username and password
This application is build on Spring Boot 3.2.3

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
    
