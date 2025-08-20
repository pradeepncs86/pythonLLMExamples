# C4 DSL User Prompt Guidelines

This guide explains how users should structure their input to generate accurate C4 model DSL notation.

## Required Information Categories

### 1. System Overview
**What to provide:**
- Business purpose and main functionality
- Target users and stakeholders
- High-level business context
- System boundaries and scope

**Example format:**
```
"We're building an e-commerce platform that allows customers to browse products, 
make purchases, and track orders. The system serves online shoppers, store 
administrators, and customer support staff."
```

### 2. User Types and Actors
**What to provide:**
- Different types of users
- Their roles and responsibilities
- External actors who interact with the system
- User personas or job titles

**Example format:**
```
Users include:
- Customers: Browse products, make purchases, track orders
- Store Administrators: Manage inventory, process orders, view analytics  
- Customer Support: Handle customer inquiries, process returns
- Payment Processor: External system for handling payments
```

### 3. System Components and Applications
**What to provide:**
- Main applications or services
- Technology platforms used
- Deployment units
- Data storage requirements
- Third-party integrations

**Example format:**
```
The system consists of:
- Customer-facing web application (React.js frontend)
- Mobile app for iOS and Android  
- Admin dashboard (Angular frontend)
- REST API backend (Java Spring Boot)
- Product database (PostgreSQL)
- Order processing service (Node.js microservice)
- Payment gateway integration (Stripe API)
- Email notification service (SendGrid)
```

### 4. Internal Structure (Optional)
**What to provide:**
- Major functional modules
- Business logic components  
- Data access layers
- Internal services and utilities

**Example format:**
```
The API backend includes:
- User authentication and authorization
- Product catalog management
- Shopping cart functionality
- Order processing workflow
- Payment integration layer
- Notification service
- Analytics and reporting
```

### 5. Integration and Communication
**What to provide:**
- How components communicate
- Data flow between systems
- External API dependencies
- Message formats and protocols

**Example format:**
```
Communication flows:
- Web app calls REST API over HTTPS
- Mobile app syncs with API using JSON
- API queries PostgreSQL for product data
- Order service publishes events to message queue
- Payment processed via Stripe webhook
- Notifications sent through SendGrid API
```

## Information Format Guidelines

### Technology Specification
Always specify:
- **Programming languages**: Java, JavaScript, Python, C#, etc.
- **Frameworks**: Spring Boot, React, Angular, Django, .NET, etc.
- **Databases**: PostgreSQL, MySQL, MongoDB, Redis, etc.
- **Platforms**: Web browser, iOS, Android, AWS, Azure, etc.
- **Protocols**: HTTP/HTTPS, WebSocket, TCP, MQTT, etc.

### Deployment Information
Include when relevant:
- Cloud platforms (AWS, Azure, GCP)
- Containerization (Docker, Kubernetes)
- Serverless functions (Lambda, Azure Functions)
- CDNs and edge services
- Load balancers and proxies

### Business Context
Provide:
- Industry domain (e-commerce, banking, healthcare, etc.)
- Business processes supported
- Compliance requirements
- Performance characteristics
- Security considerations

## Input Templates by Use Case

### Simple Web Application
```
"I'm building a [purpose] web application for [user types]. 
The system uses [frontend technology] for the user interface, 
[backend technology] for the API, and [database] for data storage. 
Users can [list main functions]. 
The application integrates with [external services]."
```

### Microservices Architecture  
```
"We have a microservices-based [domain] system with the following services:
- [Service 1]: [purpose] using [technology]
- [Service 2]: [purpose] using [technology] 
- [Service 3]: [purpose] using [technology]

Data storage includes [list databases/stores].
Services communicate via [protocols/patterns].
Users access the system through [client applications]."
```

### Mobile + Backend System
```
"The system consists of:
- Mobile apps for [platforms] built with [technology]
- Backend API using [technology stack]
- Database layer with [data stores]
- External integrations: [list services]

User types: [list with roles]
Main workflows: [describe key processes]"
```

### Legacy System Modernization
```
"Current system: [describe existing architecture]
Modernization plan: [describe new components]
Integration approach: [how old/new systems connect]
Migration strategy: [phased approach details]
Technologies: [old vs new tech stacks]"
```

## Quality Guidelines

### Be Specific About Technology
❌ "Uses a database"
✅ "Uses PostgreSQL database for storing user and product data"

❌ "Has a web frontend"  
✅ "React.js single-page application running in web browsers"

### Describe Business Purpose
❌ "User management component"
✅ "User authentication and profile management supporting login, registration, and account settings"

### Include Integration Details
❌ "Connects to payment system"
✅ "Integrates with Stripe payment gateway via REST API using webhooks for transaction status updates"

### Specify User Interactions
❌ "Customers use the system"
✅ "Customers browse product catalog, add items to cart, complete checkout process, and track order status"

## Common Mistakes to Avoid

1. **Too High Level**: "We have a web application" 
   - **Better**: Specify frontend, backend, database, and main functions

2. **Missing Technology**: "API service handles orders"
   - **Better**: "Node.js microservice processes orders using Express framework"

3. **Unclear Boundaries**: "The system does everything"
   - **Better**: Define specific applications and their responsibilities  

4. **No User Context**: "Build this architecture"
   - **Better**: Explain who uses it and for what business purpose

5. **Missing Integrations**: Focus only on internal components
   - **Better**: Include external systems, APIs, and third-party services

## Validation Checklist

Before submitting your prompt, ensure you've covered:
- [ ] Business purpose and domain
- [ ] User types and their needs  
- [ ] Main applications/services with technologies
- [ ] Data storage requirements
- [ ] Integration points and external dependencies
- [ ] Communication protocols and patterns
- [ ] Deployment and infrastructure context (if relevant)

Following these guidelines will help generate accurate and comprehensive C4 model DSL that properly represents your software architecture.