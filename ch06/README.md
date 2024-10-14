**Chapter 6: Design for Understandability** from *Building Secure and Reliable Systems*:

### 1. Why Is Understandability Important?
This section emphasizes that an understandable system reduces the likelihood of introducing security vulnerabilities or operational failures. When systems are complex, engineers are more prone to making mistakes, which can lead to unintended consequences. Understandability is also critical for incident response, where responders must quickly comprehend system behavior to assess and mitigate issues. Additionally, a clear understanding of system invariants helps ensure security and availability assertions remain true, even under malicious or unforeseen conditions.

### 2. Designing Understandable Systems
Complexity is often unavoidable in modern distributed systems, but designing with understandability in mind helps manage that complexity. This section highlights strategies like breaking down systems into smaller, more comprehensible components and centralizing security and reliability responsibilities within frameworks. The aim is to compartmentalize complexity so engineers can reason about the system in smaller, isolated parts.

### 3. System Architecture
This section focuses on using **layers and components** to manage complexity. Each system component should have a well-defined interface, making it easier to reason about individual parts without understanding the entire system. Security boundaries are essential in this architecture, as they enforce trust models and separate parts of the system to minimize risk. Frameworks that enforce consistent policies for security and reliability across the system further enhance understandability.

### 4. Software Design
In this section, the authors advocate for using **application frameworks** that provide service-wide capabilities like authentication, authorization, and monitoring. These frameworks help ensure consistency, reduce ad hoc implementations, and foster understandability. Complex data flows should be visualized and simplified where possible, while APIs must prioritize usability and ensure they are predictable and structured to make system interactions clear.

This chapter stresses that designing systems for understandability is a proactive approach to mitigating risks and ensuring that the security and reliability of a system can be reasoned about effectively.