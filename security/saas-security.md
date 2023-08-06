# Security in SaaS

## Potential Risks and Threats

- Access risk
    - SaaS apps are always on that is why anyone can reach them on internet
    - Credential stuffing & password spraying are common attacks
- Misconfiguration risk
    - Too many administrators
    - Lack of visibility into SaaS security settings and changes
- Shadow SaaS
    - deployed application in the same cloud account as the main SaaS application
    - the deployed service was done without the security approval

## Evaluation of SaaS Security (SANDPIT)

* **S** - Scalability and Resiliency
    * Provider's ability to scale and recover from failure
* **A** - Access Control
    * Who has access to the app?
    * Authentication and Authorization
* **N** - Network and Boundary Controls
    * North-South traffic
        * ingress and egress controls
        * control traffic in and out of the network
    * East-West traffic
        * segmentation
        * Understanding how data isolated or commingled
* **D** - Data Protection
    * Encryption
    * Managed certificates and keys
    * Use unique keys for each instance
* **P** - Privacy
    * The infrastructure should be compliant with any laws are important for your business
* **I** - Incident Response
    * When something is happened, the monitoring tools should be able to detect it and show to customers when and what
      happened
* **T** - Third-Party Attestation
    * Annual assessment and report of cloud service provider
    * Conducted by an external auditor (e.g. SOC2)

## Links

* [LinkedIn Learning - Securing SaaS](https://www.linkedin.com/learning-login/share?forceAccount=false&redirect=https%3A%2F%2Fwww.linkedin.com%2Flearning%2Fsecuring-software-as-a-service-saas%3Ftrk%3Dshare_ent_url%26shareId%3D8fj613EJQMmPlYGFLCd%252B9A%253D%253D)