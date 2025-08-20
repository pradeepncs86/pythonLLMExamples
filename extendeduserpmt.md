# C4 DSL User Prompt Guidelines

This guide explains how users should structure their input to generate accurate C4 model DSL notation that extends an existing base workspace.

## Base Workspace Context

Your generated architecture will extend an existing **Base Workspace** that contains predefined software systems. When describing your requirements:

1. **Reference existing systems**: If you mention systems that might already exist in the base workspace, the AI will use the existing systems rather than creating duplicates
2. **Extend existing systems**: You can add new containers, components, and functionality to existing base systems
3. **Integrate with existing systems**: Describe how your new components will interact with existing base systems
4. **Follow established patterns**: New elements will follow the same architectural patterns and conventions as the base workspace

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
- Main applications or services (specify if extending existing base systems)
- Technology platforms used
- Deployment units
- Data storage requirements
- Third-party integrations
- **Integration points** with existing base workspace systems

**Example format:**
```
The system consists of:
- Customer-facing web application (React.js frontend) - extends existing Customer Portal system
- New mobile app for iOS and Android
- Enhanced REST API backend (Java Spring Boot) - adds new endpoints to existing User Management API
- Additional product database (PostgreSQL) - integrates with existing Customer Database
- New order processing service (Node.js microservice)
- Uses existing Payment Gateway from base workspace
- Integrates with existing Email Service for notifications
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
- Data flow between systems (including base workspace systems)
- External API dependencies
- Message formats and protocols
- **Specific integration patterns** with existing base systems

**Example format:**
```
Communication flows:
- New web app calls enhanced REST API over HTTPS
- Mobile app syncs with existing User Management API using JSON
- New API queries both new PostgreSQL database and existing Customer Database
- Order service publishes events to existing Message Queue system
- Payment processed via existing Payment Gateway in base workspace
- Notifications sent through existing Notification Service
- New analytics service reads data from existing Data Warehouse
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

### Extending Existing Base System
```
"I need to extend the existing [Base System Name] with [new functionality]. 
The enhancement includes:
- New [container type] using [technology]
- Additional [components/features]
- Integration with existing [base system components]
- New data flows: [describe data flow with existing systems]

Users: [how user experience changes]
Technology: [new tech stack components]"
```

### New System Integrating with Base
```
"I'm building a new [purpose] system that integrates with the existing base workspace.
The new system includes:
- [New containers and technologies]
- Integration points with: [list existing base systems]
- Data exchange: [how data flows between new and existing systems]
- Shared services: [which base services will be used]

Authentication: [how it integrates with existing auth]
Users: [new user types or enhanced existing user experiences]"
```

### Simple Web Application
```
"I'm building a [purpose] web application for [user types]. 
The system uses [frontend technology] for the user interface, 
[backend technology] for the API, and [database] for data storage. 
Users can [list main functions]. 
The application integrates with [external services and existing base systems]."
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
✅ "Integrates with existing Payment Gateway from base workspace via REST API, plus adds new Stripe integration for international payments"

❌ "Uses the user database"
✅ "Reads from existing User Management system in base workspace and adds new user preference data to dedicated PostgreSQL instance"

### Specify User Interactions
❌ "Customers use the system"
✅ "Customers browse product catalog, add items to cart, complete checkout process, and track order status"

## Common Mistakes to Avoid

1. **Too High Level**: "We have a web application" 
   - **Better**: Specify frontend, backend, database, and integration with base systems

2. **Missing Technology**: "API service handles orders"
   - **Better**: "Node.js microservice processes orders using Express framework and integrates with existing Order Management system"

3. **Unclear Boundaries**: "The system does everything"
   - **Better**: Define specific applications, their responsibilities, and how they extend/integrate with base systems

4. **No Base Integration Context**: "Build this architecture in isolation"
   - **Better**: Explain how new components will work with existing base workspace systems

5. **Missing Integration Patterns**: "Somehow connects to existing systems"
   - **Better**: Specify exact integration methods, APIs, data flows, and protocols with base systems

6. **Duplicate System Creation**: "We need a user management system"
   - **Better**: "Extend the existing User Management system with new role-based permissions and social login features"

## Validation Checklist

Before submitting your prompt, ensure you've covered:
- [ ] Business purpose and domain
- [ ] User types and their needs  
- [ ] Main applications/services with technologies
- [ ] Data storage requirements
- [ ] Integration points with existing base workspace systems
- [ ] Specific extension points for base systems (if applicable)
- [ ] Communication protocols and patterns (new and with existing systems)
- [ ] Deployment and infrastructure context (if relevant)
- [ ] Clear distinction between new components and base system integrations

## Base Workspace Integration Examples

### Good Integration Description:
```
"I need to add a real-time chat feature that integrates with the existing User Management 
and Notification systems. The chat service will be a new Node.js WebSocket server that 
authenticates users through the existing Authentication API and sends notifications 
via the existing Email Service. Chat history will be stored in a new MongoDB database, 
but user profiles will continue to be managed by the existing User Management system."
```

### Good Extension Description:
```
"Extend the existing Customer Portal system by adding a new React component for 
subscription management. This will add new REST endpoints to the existing API Gateway 
and create a new Subscription Service (Java Spring Boot) that integrates with the 
existing Payment Gateway and Customer Database. The new service will publish events 
to the existing Event Bus for analytics."
```

Following these guidelines will help generate accurate and comprehensive C4 model DSL that properly represents your software architecture.