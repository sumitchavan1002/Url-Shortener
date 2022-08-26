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

# Setting up Redis
## Configure Redis
We need to define the configuration in order to store our JSON object in redis. Each url entry will be defined as :

{

    "key": 123,
    
    "url": "www.abc.url"
    
    "created_at": "2021-08-10T23:59:59Z"
    
}

![Screenshot (47)](https://user-images.githubusercontent.com/58344010/186830304-ee6605d1-2e47-4d54-9b4d-fc3669fdd0f3.png)



# Testing using Postman
Now let’s get to the part where we will validate above code. I’ll be using Postman as a HTTP client to test the application. 
However, you can decide to use any other client that you are comfortable with.

![Screenshot (46)](https://user-images.githubusercontent.com/58344010/186829486-64f8d2dc-c05d-45a7-8033-797b6cf03e6d.png)


