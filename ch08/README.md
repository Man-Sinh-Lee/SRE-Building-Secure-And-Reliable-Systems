Here is a summary of **Chapter 8: Design for Resilience** from *Building Secure and Reliable Systems*:

### 1. Design Principles for Resilience
Resilience refers to a system's ability to withstand disruptions and recover from them. Key principles include:
- **Independent Resilience at Each Layer**: Each layer of a system should have its own resilience features to avoid a single point of failure.
- **Prioritization of Features**: Critical features are prioritized for preservation during high load, while nonessential features are throttled or disabled.
- **Compartmentalization**: Systems should be divided into functional units to prevent cascading failures.
- **Redundancy**: Localized failures are mitigated with redundant systems, and global failures have alternative defenses.

### 2. Defense in Depth
This concept ensures multiple layers of protection. A famous analogy used is the **Trojan Horse**, where deeper inspections and multiple layers of defense could have prevented the compromise of Troy. Google’s use of **App Engine** demonstrates defense in depth through sandboxing, allowing attackers' actions to be contained before they cause broader damage.

### 3. Controlling Degradation
When failures happen, systems should degrade gracefully rather than collapse entirely. Strategies include:
- **Disabling Noncritical Features**: Systems should prioritize core functions under load and disable or throttle nonessential tasks.
- **Load-Shedding**: If under extreme load, systems should automatically reduce resource usage by limiting requests from less important sources.

### 4. Controlling the Blast Radius
To minimize the impact of failures, systems should be compartmentalized to ensure problems are contained within specific areas. Key tactics include:
- **Role Separation**: Different jobs should run as distinct roles to limit the damage an adversary can do if they compromise one service.
- **Location Separation**: Services running in different locations provide resilience by limiting the scope of attacks or failures.

### 5. Failure Domains and Redundancies
Systems should have **failure domains**, where failures are isolated and managed within specific boundaries. Redundancy across domains ensures that, if one component fails, others can take over, maintaining system availability.

### 6. Continuous Validation
Validation involves consistently testing systems to ensure that resilience mechanisms function properly. This includes testing automated responses and failure-handling strategies, ensuring that they activate as designed during incidents.

### 7. Practical Advice: Where to Begin
Smaller organizations should focus on degradation controls, blast radius management, and failure domain segmentation. As the system grows, investing in continuous validation is key to maintaining and improving resilience. 

This chapter emphasizes how resilient systems can withstand failures by using compartmentalization, redundancy, and validation strategies to prevent full-scale breakdowns.