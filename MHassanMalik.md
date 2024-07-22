# INFO


The Strangler Pattern is a software development strategy for gradually replacing an old system with a new one without having to stop or disrupt the operation of the old system. Think of it like slowly growing a new plant around an old tree until the new plant eventually replaces the old tree.

Here's a simplified breakdown of how it works:

1. **Identify a Small Part of the Old System**: Find a specific part of the old system that you want to replace first. This part could be a specific function, service, or module.

2. **Create the New Replacement**: Build the new version of this small part using modern technology, best practices, or whatever improvements you want to implement.

3. **Redirect Traffic**: Change your system so that all requests for that specific part are handled by the new version instead of the old one.

4. **Repeat**: Continue this process for other parts of the old system. Gradually, more and more of the old system is replaced by the new system.

5. **Complete the Transition**: Eventually, the old system will be fully replaced by the new system, and you can retire the old system entirely.

### Example

Imagine you have an old website that customers use. Instead of rebuilding the entire website from scratch and launching it all at once, you would:

1. **Replace the Homepage**: First, create a new homepage and redirect users to this new homepage.
2. **Update the Product Page**: Next, build a new product page and direct users to the new product page.
3. **Continue Updating Sections**: Keep updating and redirecting other sections like the checkout page, user profile, etc.
4. **Fully Transition**: Once every part of the old website is replaced with the new website, the old website can be completely shut down.

By using the Strangler Pattern, you reduce risk because you're not making a big change all at once. You can test each new part individually, ensuring it works well before moving on to the next part.





## Monolithic Architecture
Single Unit: A monolithic application is built as a single, large unit. All the parts of the application (like the user interface, business logic, and data access) are interconnected and dependent on each other.

Tightly Coupled: All the components are tightly linked. If you need to make a change in one part of the application, it often affects other parts.

Deployment: You deploy the entire application at once. Even a small change requires redeploying the whole application.

Scalability: Scaling a monolithic application can be challenging because you have to scale the entire application, not just the parts that need more resources.

Microservice Architecture
Multiple Units: A microservice application is built as a collection of small, independent services. Each service focuses on a specific business function and operates on its own.

Loosely Coupled: The services are loosely linked. Each service can be developed, deployed, and scaled independently of the others.

Deployment: You can deploy each microservice independently. This means a change in one service doesn't require redeploying the entire application.

Scalability: You can scale specific services that need more resources




## Microservice anti-patterns
 are common mistakes or poor practices that can undermine the benefits of using microservices. Here are some microservice anti-patterns explained in simple terms:

### 1. **Service Silos**

- **Problem**: Teams develop their microservices in isolation, without proper communication or integration with other teams.
- **Impact**: Leads to duplication of effort, inconsistent data, and difficulty in integrating different services.

### 2. **Distributed Monolith**

- **Problem**: The microservices are technically separate but are tightly coupled, meaning changes in one service often require changes in others.
- **Impact**: Reduces the benefits of microservices, making it hard to develop, deploy, and scale services independently.

### 3. **Nanoservices**

- **Problem**: Breaking down services too much into very small, fine-grained services that are too granular.
- **Impact**: Increases the complexity of managing, monitoring, and deploying many tiny services, leading to inefficiencies.

### 4. **Shared Database**

- **Problem**: Multiple microservices share a single database schema or tables.
- **Impact**: Creates strong coupling between services, making it hard to change the database schema without affecting multiple services.

### 5. **Smart Endpoints, Dumb Pipes**

- **Problem**: Using overly complex messaging and orchestration systems instead of simple communication mechanisms.
- **Impact**: Introduces unnecessary complexity and reduces the independence of microservices.

### 6. **Reinventing the Wheel**

- **Problem**: Each microservice team independently solves common problems like logging, monitoring, and configuration management.
- **Impact**: Leads to inconsistency and wasted effort across the organization.

### 7. **Ignoring Domain-Driven Design (DDD)**

- **Problem**: Not following domain-driven design principles when defining microservices.
- **Impact**: Results in poorly defined boundaries and services that do not align well with business functions.

### Example Scenario

Imagine you are building an online store with microservices:

- **Service Silos**: One team builds the product catalog service, another builds the user service, but they don't communicate. Both teams create their own user profile features, leading to duplication and inconsistency.

- **Distributed Monolith**: The product catalog service and the order processing service are separate, but any change in product details requires changes in the order processing code as well.

- **Nanoservices**: Instead of one service handling the payment process, you have separate services for credit card validation, payment processing, and receipt generation, making the system overly complex.

- **Shared Database**: All services access a single database, so changing the database schema for the product catalog affects the user service and order processing service.

- **Smart Endpoints, Dumb Pipes**: Using a complex messaging system to coordinate actions between services when simpler RESTful APIs would suffice.

- **Reinventing the Wheel**: Each service team builds its own logging system instead of using a centralized logging service.

- **Ignoring DDD**: Defining services around technical layers (like data access) instead of business domains (like inventory management).

### Summary

Microservice anti-patterns are practices that can lead to inefficiencies, complexity, and reduced benefits when using microservices. Avoiding these anti-patterns helps ensure you get the full advantages of a microservice architecture.