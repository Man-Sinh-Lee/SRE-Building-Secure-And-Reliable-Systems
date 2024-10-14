Here is a summary of **Chapter 3: Case Study: Safe Proxies** from *Building Secure and Reliable Systems*:

### 1. Safe Proxies in Production Environments
Safe proxies at Google are designed to improve security and reliability by controlling and auditing access to production systems. These proxies serve as intermediaries that enforce access policies and provide a mechanism for logging actions. Instead of directly accessing production servers via SSH, engineers issue commands through these proxies, ensuring that all administrative actions are audited and subject to controls like multi-party authorization (MPA). This helps prevent human errors and malicious actions in a production environment.

The system introduces several benefits:
- **Centralized Logging and Auditing**: Every administrative action is logged, allowing for full traceability.
- **Access Control**: Proxies enforce fine-grained access policies, ensuring only authorized personnel can execute sensitive commands.
- **Rate Limiting**: Changes such as server restarts are rate-limited to reduce the blast radius of potential mistakes.
- **Compatibility**: The proxy system can interact with both Google’s proprietary systems and third-party closed-source systems, enhancing flexibility without requiring system modifications.

### 2. Google Tool Proxy
Google’s **Tool Proxy** is an internal mechanism that allows engineers to run administrative commands indirectly, ensuring commands are logged, access is controlled, and sensitive actions are subject to additional approval steps. This proxy is part of Google’s broader **Zero Touch Prod** initiative, which aims to minimize human interaction with production systems to reduce errors. Engineers interact with production servers by issuing commands through the proxy, which then executes them according to predefined policies.

For example, running a command like `$ tool-proxy-cli --proxy_address admin-proxy borg kill` would initiate the following steps:
1. The proxy logs the command and checks the policy.
2. It verifies if the user is authorized to execute the command.
3. For sensitive actions, multi-party authorization (MPA) is required before execution.
4. The command is executed, and the results are logged.

This approach prevents direct access to production systems, further reducing risks of outages or security breaches caused by human errors.

In conclusion, safe proxies at Google enable secure and reliable production environments by providing structured access control, logging, and multi-party approval mechanisms, which help mitigate risks from both malicious and accidental actions.