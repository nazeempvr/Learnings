# Technical Lead – Interview Q&A

## Questions

1️⃣ [How do you handle underperforming team members?](#1️⃣-how-do-you-handle-underperforming-team-members)

2️⃣ [How do you mentor junior developers?](#2️⃣-how-do-you-mentor-junior-developers)

3️⃣ [How do you conduct code reviews?](#3️⃣-how-do-you-conduct-code-reviews)

4️⃣ [How do you distribute tasks in a sprint?](#4️⃣-how-do-you-distribute-tasks-in-a-sprint)

5️⃣ [How do you handle conflicts within the team?](#5️⃣-how-do-you-handle-conflicts-within-the-team)

6️⃣ [How do you ensure team productivity?](#6️⃣-how-do-you-ensure-team-productivity)

7. [How do you decide between Monolith and Microservices?](#7-how-do-you-decide-between-monolith-and-microservices)
8. [Explain a complex architecture you designed](#8-explain-a-complex-architecture-you-designed)
9. [How do you ensure scalability?](#9-how-do-you-ensure-scalability)
10. [How do you handle performance bottlenecks?](#10-how-do-you-handle-performance-bottlenecks)
11. [How do you design high availability systems?](#11-how-do-you-design-high-availability-systems)
12. [How do you secure a .NET application?](#12-how-do-you-secure-a-net-application)


---

## Answers

---

## 1️⃣ How do you handle underperforming team members?

Answer:

First, I don’t assume performance issues are capability problems. I try to understand the root cause.

I start with a 1:1 conversation to understand whether the issue is:

Skill gap

Clarity issue

Personal issue

Motivation problem

If it’s a skill gap, I:

Provide learning resources

Pair them with a senior member

Break tasks into smaller deliverables

If it’s clarity or ownership issue:

I define clear expectations

Set measurable short-term goals

I monitor progress weekly and give constructive feedback.

If there’s still no improvement after support and clarity, then I escalate appropriately — but always after giving fair opportunity.

👉 My approach is: Support first, correct second, escalate last.

---

## 2️⃣ How do you mentor junior developers?

Answer:

I mentor in three ways:

Technical guidance

Explain architecture decisions

Encourage understanding, not copy-paste coding

Teach debugging techniques

Code review as learning

Instead of just saying “wrong,” I explain why

Share best practices (SOLID, clean code, performance)

Ownership building

Assign small features end-to-end

Let them present solutions in team meetings

I focus on making them independent problem solvers, not dependent coders.

👉 My goal is to make juniors capable of handling modules independently within 6–12 months.

---

## 3️⃣ How do you conduct code reviews?

Answer:

I treat code reviews as quality control + knowledge sharing.

My approach:

Check:

Readability

Naming conventions

SOLID principles

Performance issues

Security concerns

Edge cases

I avoid personal criticism. I focus on:

“How can we improve this?”

“What happens if this fails?”

I ensure:

No business logic in controllers

Proper exception handling

Logging added where needed

No unnecessary DB calls (avoid N+1)

For major changes:

I ask developer to explain logic before approval

👉 Code review is not about finding mistakes.  
It’s about maintaining standards and preventing future production issues.

---

## 4️⃣ How do you distribute tasks in a sprint?

Answer:

I distribute tasks based on:

Complexity

Team member skill level

Learning opportunity

Sprint commitment

My approach:

Critical/complex tasks → Experienced members

Moderate tasks → Mid-level developers

Simple tasks / learning tasks → Juniors

But I don’t always give easy work to juniors — I gradually increase complexity to help growth.

Before sprint starts:

I ensure requirements are clear

Break stories into small tasks

Identify dependencies

During sprint:

Monitor progress in daily standups

Rebalance tasks if needed

👉 My focus is balanced workload + predictable delivery.

---

## 5️⃣ How do you handle conflicts within the team?

Answer:

Conflicts usually arise from:

Technical disagreements

Ownership confusion

Communication gaps

My approach:

I listen to both sides individually.

Bring discussion to facts, not emotions.

If it’s technical disagreement:

We evaluate based on scalability, performance, maintainability.

Sometimes do a quick POC to decide.

If it’s personal misunderstanding:

Clarify expectations

Encourage respectful communication

As a lead, I stay neutral and solution-oriented.

👉 My priority is protecting team harmony and delivery momentum.

---

## 6️⃣ How do you ensure team productivity?

Answer:

I focus on removing blockers rather than pushing people.

Key things I ensure:

Clear requirements before sprint start

No mid-sprint scope changes

Quick resolution of blockers

Proper environment & deployment access

Monitoring sprint burndown daily

I also:

Encourage knowledge sharing sessions

Promote automation (CI/CD, testing)

Reduce unnecessary meetings

👉 Productive teams are created by clarity, stability, and trust — not pressure.

## 7. How do you decide between Monolith and Microservices?

Answer:

I don’t choose microservices by default. I decide based on business complexity, team size, and scalability needs.

I prefer Monolith when:

- Product is in early stage
- Small team (less than 6–8 developers)
- Domain is not complex
- Deployment simplicity is important
- Tight coupling between modules

I prefer Microservices when:

- Large domain with clear bounded contexts
- Multiple teams working independently
- Need independent scaling
- High availability is critical
- Frequent deployments required

### Trade-off Awareness

| Monolith | Microservices |
|----------|--------------|
| Simple deployment | Complex DevOps |
| Easier debugging | Distributed tracing required |
| Faster initial development | Higher infra cost |
| Tight coupling risk | Network latency |

👉 My approach:  
Start with modular monolith. Move to microservices only when business complexity demands it.

---

## 8. Explain a complex architecture you designed

You can align this with your IDP project experience.

Answer (Sample Structured Response):

In one of my projects, we designed a scalable inventory management system with:

- ASP.NET Core Web API
- Azure Cosmos DB
- Azure Functions for background processing
- Azure App Configuration & Key Vault
- CI/CD through Azure DevOps

### Architecture Highlights

- Clean Architecture (Domain, Application, Infrastructure)
- Repository pattern with dependency injection
- Background processing using Azure Functions for async tasks
- Centralized logging & monitoring
- Configuration externalized in Azure App Configuration

### Why this design?

- Separation of concerns
- Easy testing (xUnit + Moq)
- Scalable storage (Cosmos DB)
- Secure secrets management

👉 The goal was scalability, maintainability, and cloud-native design.

---

## 9. How do you ensure scalability?

I consider both horizontal and vertical scaling.

### 1️⃣ Application Level

- Stateless APIs
- Avoid in-memory session
- Async programming
- Caching (Redis)

### 2️⃣ Database Level

- Proper indexing
- Query optimization
- Read replicas if needed
- Partitioning (Cosmos DB)

### 3️⃣ Infrastructure Level

- Auto-scaling in Azure App Services
- Load balancing
- Containerization if required

### 4️⃣ Performance Best Practices

- Use pagination
- Avoid N+1 queries
- Use projections instead of full entity load

👉 Scalability is planned at design time — not added later.

---

## 10. How do you handle performance bottlenecks?

My approach:

### Step 1: Identify

- Application Insights / Datadog / New Relic
- Check CPU, memory, response time
- Slow query logs

### Step 2: Analyze

- Is it DB issue?
- Is it memory pressure?
- Is it thread blocking?
- Is it network latency?

### Step 3: Optimize

- Add caching
- Fix inefficient LINQ queries
- Use async properly
- Reduce object allocations
- Tune GC if necessary

### Step 4: Validate

- Load testing
- Compare before/after metrics

👉 I rely on data, not assumptions.

---

## 11. How do you design high availability systems?

High availability = system continues even if one component fails.

My strategy:

### 1️⃣ Multiple Instances
Deploy application in multiple instances behind load balancer.

### 2️⃣ Health Checks
Enable health endpoints for auto-restart.

### 3️⃣ Database Resilience
- Geo-replication
- Failover groups

### 4️⃣ Retry & Circuit Breaker
Use Polly for transient failures.

### 5️⃣ Graceful Degradation
If one service fails, system should partially work.

### 6️⃣ Monitoring & Alerts
Proactive monitoring reduces downtime.

👉 HA is achieved through redundancy + monitoring + failover.

---

## 12. How do you secure a .NET application?

Security is multi-layered.

### 1️⃣ Authentication & Authorization
- JWT / OAuth2
- Role-based & policy-based authorization

### 2️⃣ Data Protection
- HTTPS only
- Encrypt sensitive data
- Use Azure Key Vault for secrets

### 3️⃣ Secure Coding
- Prevent SQL Injection (use parameterized queries / EF)
- Validate input
- Avoid exposing stack traces

### 4️⃣ API Security
- Rate limiting
- CORS policy configuration
- API Gateway if microservices

### 5️⃣ Infrastructure Security
- Network security groups
- Firewall rules
- Private endpoints

👉 Security is not a feature. It’s a design principle.
