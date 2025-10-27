# Microservices & DevOps - 27 Oct Notes

### What are Microservices?
Instead of one big "monolith" app, we break it into small, independent services. Each service does one specific thing (like payments or login).

**Main Benefits:**
- **Scaling:** Only scale the parts that need it.
- **Tech Choice:** Use different languages/tools for different services.
- **Fast Speed:** Update one service without breaking the whole thing.

---

### Core Components
- **API Gateway:** The single entry point. It handles routing, security (login), and limits how many requests come in.
- **Service Registry:** A list that keeps track of which services are running and where they are.
- **DNS:** Turns names (example.com) into IP addresses so computers can find each other.
- **Load Balancer:** Distributes traffic evenly so no single server gets overwhelmed.

---

### Communication & Databases
- **Synchronous:** Service A waits for Service B to reply (like a phone call).
- **Asynchronous:** Service A sends a message and moves on (like an email). Uses "Message Brokers" like Kafka.
- **SQL vs NoSQL:**
  - **SQL:** Good for structured data and complex stuff (MySQL, Postgre).
  - **NoSQL:** Good for speed and huge amounts of flexible data (MongoDB).
- **Database per Service:** Each service should have its own database to keep things independent.

---

### Logging & Management
- **External Logs:** Since microservices run in containers that can disappear, we send all logs to one central place (ELK stack, CloudWatch).
- **12-Factor Apps:** A set of best practices to make apps scale well in the cloud (keep config separate, stay stateless, etc.).

---

### DevOps & CI/CD
DevOps is about making Development and Operations work together to ship code faster and better.
- **CI (Continuous Integration):** Automatically testing and merging code many times a day.
- **CD (Continuous Deployment):** Automatically sending that code to the live app.

**Next Topics:** Docker and Kubernetes (for running these services in containers).
