# Url-shortener using Spring Boot and Redis.

# Introduction
This project demonstrates the use of Spring Boot 2.0 and Redis to build an URL shortener API popularly known as TinyURL. The application creates and stores a shorter version of original URL in Redis’s in-memory cache. It also provides an interface to obtain original URL in exchange of the shorter URL.


# Architecture
![tiny-url-architecture](https://user-images.githubusercontent.com/58344010/186824026-4987d30e-c0d8-4863-b2d4-d487319a9497.png)



# Bootstrapping application using Spring Initializr
Let’s use Spring Initializr to bootstrap our application. Fill the form as shown below and click on Generate Project to download the project. Here I have included Spring MVC and Spring Data Redis as dependencies.

![Screenshot (44)](https://user-images.githubusercontent.com/58344010/186824348-86541df9-c3cd-4bbb-a9c4-566206da7a10.png)

# Additional Dependencies
In addition to the bootstraped dependencies, you will also need the following.

compile('commons-validator:commons-validator:1.4.0')
compile('com.google.guava:guava:23.0-rc1')

Add them to your project’s build.gradle.
1. common-validator library will be used to validate the input/original URL
2. Google’s guava library will be used to generate a Murmur3 based unique hash key for original URL. This key will be treated as the shorter URL.

