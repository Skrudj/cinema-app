# Cinema-app
## Shortly about app
This is a simple back end logic of CRUD app that emulates how the cinema app works. 
I've made it to understand the work of frameworks and figure out how to work with them. I've implemented many 
endpoints, understood how Dtos, Daos, Services work. Also understood how to configure framework with annotations.  
It's done using the hibernate and spring frameworks.

## Features
<ul>
    <li>Authentication and password encryption using Spring Security</li>
    <li>Role based authorization using custom roles</li>
    <li>Access to endpoints according to role</li>
    <li>Managing entities like adding movies, movie sessions, searching available movie sessions, making orders and searching orders history</li>
</ul>

## Project structure
<ul>
    <li><code>config</code>: configuration classes for spring;</li>
    <li><code>controller</code>: controller classes that handle all http requests;</li>
    <li><code>dao</code>: all data access objects that are responsible for communicating with database;</li>
    <li><code>dto</code>: all data transfer objects that are made for handling requests and responses with frontend;</li>
    <li><code>exception</code>: contains custom exceptions;</li>
    <li><code>lib</code>: contains custom annotations and their logic for validating email and password;</li>
    <li><code>model</code>: all models that represents entities from database;</li>
    <li><code>service</code>: all classes that represents service layer and contains some business logic;</li>
    <li><code>mapper</code>: all mappers that are responsible for mapping models to responses and mapping requests to models;</li>
    <li><code>util</code>: contains static variable for date-time pattern for searching available session in movie session controller;</li>
</ul>

## Startup
<ul>
    <li>Clone this repo to yours environment;</li>
    <li>Configure db.properties in resources;</li>
    <li>Build project with <code>mvn compile</code>;</li>
    <li>Configure tomcat or other servlet container and deploy <code>spring-security-part-2-1.0-SNAPSHOT.war</code>;</li>
    <li>Enjoy with functionality of app. Easy to test with Postman. Here is map of endpoints:
        <ul>
            <li><code>POST /register</code> - create new user, (non-authenticated);</li>
            <li><code>GET /cinema-halls, /movies, /movie-sessions/available</code> - get list of corresponding entities (USER, ADMIN)</li>
            <li><code>POST /cinema-halls, /movies, /movie/sessions</code> - create corresponding entity (ADMIN)</li>
            <li><code>PUT /movie-sessions/{id}</code> - update info about sessions (ADMIN)</li>
            <li><code>DELETE /movie-sessions/{id}</code> - delete movie session (ADMIN)</li>
            <li><code>GET /orders</code> - get history of currently authenticated user (USER)</li>
            <li><code>GET /shopping-carts/by-user</code> - get info about shopping cart of currently authenticated user (USER)</li>
            <li><code>POST /orders/complete</code> - complete order of currently authenticated user (USER)</li>
            <li><code>PUT /shopping-carts/movie-sessions</code> - add ticket for currently authenticated user (USER)</li>
            <li><code>GET /users/by-email</code> - find info about user by his email (ADMIN)</li>
        </ul>
    </li>
    <li>Pre-built accounts:
        <ul>
            <li><code>admin</code> - login: <code>admin@i.ua</code>, password: <code>admin12345</code></li>
            <li><code>user</code> - login: <code>user@i.ua</code>, password: <code>user12345</code></li>
        </ul>
    </li>
</ul>

## Stack of technologies
<ul>
    <li>Java <code>17</code></li>
    <li>Maven <code>4.0.0</code></li>
    <li>Spring <code>5.3.20</code></li>
    <li>Spring security <code>5.6.10</code></li>    
    <li>Hibernate <code>5.6.14.Final</code></li>
    <li>Hibernate validator <code>6.1.6.Final</code></li>
    <li>MySQL Connector <code>8.0.22</code></li>    
    <li>Javax Servlets <code>4.0.1</code></li>
    <li>Javax Annotations <code>1.3.2</code></li>
    <li>Tomcat <code>9.0.73</code></li>
</ul>