# DSA vs LLD vs HLD - System Design Notes

## 1. What is LLD?

LLD stands for Low-Level Design. It focuses on breaking down a high-level system idea into detailed class structures, interfaces, design patterns, and interactions between modules. It ensures the system is scalable, maintainable, and reusable.

### Real-World Example (Uber-Like App):

Suppose you're building an Uber-like app that handles millions of users.

* **Rohit** knows DSA. He writes a function using Dijkstra's algorithm + Priority Queue to find the nearest driver. The algorithm is fast but the code lacks structure—no classes, no modules.

* **Aditya** knows both DSA and LLD. Before writing code, he designs:



He wraps the Dijkstra logic inside a service, uses Strategy and Singleton patterns, and creates modules that can scale and be reused.

## 2. DSA vs LLD

| Point           | DSA (Data Structures & Algorithms) | LLD (Low Level Design)                       |
| --------------- | ---------------------------------- | -------------------------------------------- |
| Purpose         | Solve problems efficiently         | Implement real-world software                |
| Focus           | Time and space optimization        | Scalability, maintainability, reusability    |
| Examples        | Dijkstra, Binary Search, Heaps     | Class design, Service layer, Design Patterns |
| Used In         | Coding rounds                      | System development, backend/frontend dev     |
| Questions Asked | "How to solve it?"                 | "How to build it?"                           |

## 3. Three Pillars of LLD

### 1. Scalability

Definition: System handles increased load without performance drop.

* Example: Uber with 10 riders worked with if-else blocks. But with 1 million users, Aditya used service layers and queues to scale efficiently.

### 2. Maintainability

Definition: Code is easy to understand, debug, and update.

* Example: Netflix video player split into BufferManager, UIHandler instead of a 2000-line single script.

### 3. Reusability

Definition: Code can be reused across modules without rewriting.

* Example: NotificationService class handles SMS, email, etc., instead of multiple hardcoded scripts.

## 4. What is NOT LLD?

LLD is not about:

* Choosing databases
* Scaling infrastructure
* Deciding API gateways
* Selecting tech stack

These fall under HLD.

## 5. What is HLD?

HLD stands for High-Level Design. It focuses on the architectural structure of the system—how major components interact, technologies used, APIs, databases, microservices, caching, etc.

### Example (Uber):

HLD defines:

* Components: UserService, DriverService, Ride Matching Engine
* Tech: MongoDB, Redis, Kafka
* Flow: User -> API Gateway -> Ride Engine -> Database

LLD defines:

* Class: RideRequest, Rider, Driver
* Methods: requestRide(), assignDriver()
* Patterns: Strategy, Factory, Observer

## 6. How to Identify HLD vs LLD

| What You're Looking At                | HLD or LLD?      |
| ------------------------------------- | ---------------- |
| API Gateway, Microservice diagram     | HLD              |
| Class diagram with fields and methods | LLD              |
| DB selection (MongoDB, MySQL)         | HLD              |
| Design Patterns (Strategy, Singleton) | LLD              |
| Table structure creation              | Mid-layer (Both) |

## 7. How DSA, HLD, and LLD Work Together

### Step-by-Step in Real Application (e.g., Zomato)

### 1. DSA - Logic Layer

* Focus: Efficient algorithms
* Example: Find nearest delivery boy using Dijkstra + Priority Queue

### 2. HLD - Architecture Layer

* Focus: Component interaction
* Example: OrderService, DriverService, Redis for caching

### 3. LLD - Code Design Layer

* Focus: Class structure and patterns
* Example: Order class, DeliveryBoy class, NotificationService with Strategy pattern
