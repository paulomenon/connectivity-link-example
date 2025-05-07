This project is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).

# Connectivity Link Example Reference

This repository offers configuration examples for deploying and managing **Red Hat Connectivity Link (RHCL)** within OpenShift. It illustrates the setup and organization of Gateway API resources—including Gateways, HTTPRoutes, RateLimitPolicies, AuthPolicies, and DNSPolicies—for both internal and external API gateways. The provided generic examples aim to facilitate understanding of the configuration.

## Repository Structure

The project is structured by functional areas to reflect common RHCL use cases:

```
connectivity_link/
├── auth_policy/       # Example AuthPolicy configurations
├── dns/               # DNSPolicy examples for multi-cluster load balancing
├── gateways/          # Gateway and HTTPRoute resources (internal & external)
├── ratelimit/         # RateLimitPolicy examples
└── service/           # Sample services and backend references
```

Each folder contains one or more Kubernetes YAML manifests defining Gateway API resources according to best practices.

## Use Cases Demonstrated

- Internal vs. external gateway routing  
- Namespace-based domain segregation  
- BGP/MetalLB IP advertisement integration  
- TLS termination with F5 and Envoy  
- Rate limiting, authentication, and DNS policies via Kuadrant  
- Deployment across multiple or single OpenShift clusters  

## Prerequisites

- OpenShift Container Platform 4.14 or later  
- Red Hat Connectivity Link Operator installed  
- Kuadrant Operator for advanced Gateway APIs  
- MetalLB configured (BGP or Layer 2 mode)  
- F5 LoadBalancer for TLS termination (optional but recommended)  

## Getting Started

1. Clone this repository:
   ```bash
   git clone https://github.com/paulomenon/connectivity-link-example.git
   cd connectivity-link-example
   ```

2. Apply sample configurations:
   ```bash
   oc apply -f connectivity_link/gateways/
   oc apply -f connectivity_link/auth_policy/
   oc apply -f connectivity_link/ratelimit/
   oc apply -f connectivity_link/dns/
   ```

3. Customize each YAML file to match your specific domain, IP pool, and namespace setup.

## Notes

- These examples are provided for educational and reference purposes.  
- Adapt configuration values (like hostnames, IP pools, and namespaces) to your environment.  
- This repository does not include deployment automation or CI/CD integrations.  


---

Maintained by [@paulomenon](https://github.com/paulomenon). Contributions and suggestions are welcome.


