Chapter 14 of "Building Secure and Reliable Systems" focuses on the complexities of **Deploying Code** securely and reliably. Below is a summary of the key sections:

### 1. **Concepts and Terminology**
   - The chapter begins by defining the **software supply chain**, which includes the steps for writing, building, testing, and deploying software. These steps are typically managed by version control systems, continuous integration (CI), and continuous delivery (CD) pipelines.

### 2. **Threat Model**
   - The threat model focuses on protecting against both **benign insiders** (who may accidentally make mistakes) and **malicious insiders** or **external attackers** who could compromise systems by subverting the software supply chain. Examples include accidental deployments of outdated or vulnerable code or intentional exploitation through compromised accounts.

### 3. **Best Practices**
   - **Require Code Reviews**: Mandatory peer code reviews serve as a security control, ensuring that no single individual can deploy changes without oversight.
   - **Rely on Automation**: Automated systems for building, testing, and deploying code reduce human error and improve consistency.
   - **Verify Artifacts, Not Just People**: Deployment processes should verify that the software being deployed originated from a trusted CI/CD pipeline rather than relying solely on the identity of the person initiating the deployment.
   - **Treat Configuration as Code**: Configuration files should be versioned and reviewed just like application code, to avoid misconfigurations that could affect production environments.

### 4. **Securing Against the Threat Model**
   - The section ties best practices to specific threats, showing how techniques like code reviews, automated testing, and artifact verification can mitigate risks such as accidental vulnerability introduction or the deployment of backdoored binaries.

### 5. **Advanced Mitigation Strategies**
   - **Binary Provenance**: Keeping a record of where a binary originated (i.e., which source repository or build process created it) helps in ensuring that only trusted code is deployed.
   - **Provenance-Based Deployment Policies**: Deployments should be restricted based on the provenance of the code, with specific rules ensuring that only binaries built from trusted sources can be deployed.
   - **Verifiable Builds**: Build systems should be locked down to prevent tampering, ensuring that the build environment is secure and any code signed or deployed has been vetted.
   - **Deployment Choke Points**: Use choke points in deployment pipelines (such as Kubernetes master nodes) to ensure that all deployment requests are properly validated before they are accepted.
   - **Post-Deployment Verification**: Systems should continuously verify that deployed artifacts comply with updated security policies, such as vulnerability scans.

### 6. **Practical Advice**
   - **Take It One Step at a Time**: Gradual improvements to the deployment process, including automation and security controls, are often more practical than attempting a complete overhaul all at once.
   - **Provide Actionable Error Messages**: Ensure error messages in the deployment process are clear and specific, so developers know how to address problems effectively.
   - **Create Unambiguous Policies**: Deployment policies should be clear, with only one policy applying at a time to avoid ambiguity in decision-making.
   - **Include a Deployment Breakglass**: A breakglass mechanism allows emergency changes to bypass normal deployment controls, but these events should trigger alerts and audits to prevent abuse.

### 7. **Securing Against the Threat Model, Revisited**
   - This section revisits the earlier threat model, applying advanced mitigation strategies such as **verifiable builds** and **provenance-based deployment policies** to address complex threats that might not be fully mitigated by basic best practices.

This chapter emphasizes the importance of securing the entire software supply chain, from development through deployment, using a combination of automation, rigorous review processes, and provenance-based verification.