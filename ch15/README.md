Chapter 15 of "Building Secure and Reliable Systems" focuses on **Investigating Systems** and provides strategies for debugging, investigating security incidents, and ensuring the security of logs and access during these processes. Below is a summary of the main sections:

### 1. **From Debugging to Investigation**
   - **Example: Temporary Files**: Debugging starts with identifying system issues, like the example of a Spanner database running out of storage due to an accumulation of small temporary files.
   - **What to Do When You’re Stuck**: Debugging complex issues often requires improving the observability of systems through better logging, monitoring tools, or tracing (e.g., using Dapper or Zipkin). If stuck, engineers should focus on refining their debugging methods and consulting relevant documentation.
   - **Collaborative Debugging: A Way to Teach**: Collaborative debugging exercises such as “Wheel of Misfortune” are useful for training teams to troubleshoot together and learn new techniques in a real-time environment.
   - **How Security Investigations and Debugging Differ**: Security investigations differ from regular debugging. Debugging focuses on code behavior, while security investigations also assess whether malicious actions are involved. Investigators often look for irregularities in logs and system behavior that may signal compromise.

### 2. **Collect Appropriate and Useful Logs**
   - **Design Your Logging to Be Immutable**: Logs should be immutable to prevent tampering, ensuring that log entries are difficult to alter and that alterations leave an audit trail. Using centralized logging systems increases the difficulty for attackers to erase traces of their activity.
   - **Take Privacy into Consideration**: Logging must balance security with privacy, ensuring that unnecessary sensitive data is anonymized or encrypted. Consulting privacy specialists is recommended when designing logging systems.
   - **Determine Which Security Logs to Retain**: Organizations should decide which logs are essential for investigations without overwhelming the system with unnecessary data. Logs should be retained for sufficient time, as compromises often go undetected for long periods.
   - **Budget for Logging**: Storing and analyzing large volumes of logs can be costly, so organizations should allocate resources accordingly.

### 3. **Robust, Secure Debugging Access**
   - **Reliability**: Debugging systems need to remain functional and secure even during outages or attacks. For example, responders may require emergency credentials during incidents, but such access should trigger alerts and audits to prevent misuse.
   - **Security**: Debugging access must be carefully controlled, especially when it involves sensitive user data. Systems should be designed to allow debugging without revealing unnecessary information. Data encryption during analysis, particularly for sensitive metadata, is crucial.

The chapter emphasizes the importance of balancing debugging needs with security concerns, encouraging best practices like immutable logging, privacy safeguards, and collaborative approaches to complex problem-solving.