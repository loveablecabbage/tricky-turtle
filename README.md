## Objective
The goal of Project Tricky Turtle is to develop and demonstrate a proof of concept for a double reverse proxy system using Traefik, facilitated by a Tailscale VPN overlay. This system aims to securely route traffic from a public-facing service to a private server.

## Project Assumptions

### Endpoint (CLIENT)
- The CLIENT operates with a public DHCP address.
- Routing for the CLIENT is managed by their Internet Service Provider (ISP).
- The CLIENT uses ISP-provided public DNS, acquired through the standard DHCP process.

### Traefik Cloud Service (T1-RP01)
- T1-RP01 is hosted on a Virtual Private Server (VPS) by a public provider examples being a Digital Ocean or Linode service provider.
- This service uses a static public IP address.

### Traefik Local Service (T2-RP01)
- T2-RP01 is hosted on a private server with a static private IP address.
- This server is behind a firewall/router, which is assigned a public DHCP address.
- Network Address Translation (NAT) is utilized, specifically Port Address Translation (PAT), also known as NAT-PAT or NAT-Overload.

### Tailscale VPN overlay (TS-VPN)
- A tailscale VPN overlay has been configured between T1-RP01 and T2-RP01.
- ?
- ?
  
## IP Addressing Guidelines

### General Policies
All actual IP addresses have been sanitized to ensure privacy and security.
Where feasible, network addresses have been simplified to a /24 subnet for consistency and simplicity.
Any networks that cannot be simplified to a /24 subnet will be clearly annotated, and a detailed explanation will be provided.

#### Sanitized IP Address Scheme
All sanitized IP addresses are categorized as follows:

### Public Addresses
- Supernet: 10.0.0.0/8
- Example subnet: 10.1.1.0/24
- Example IP address: 10.1.1.1/24
- Usage: Designated as public addresses in the context of this project.

### VPN Addresses
- Supernet: 172.16.0.0/12
- Example subnet: 172.16.1.0/24
- Example IP address: 172.16.1.1/24
- Usage: Assigned to VPN addresses to ensure secure communication over Virtual Private Networks.

### Private Addresses
- Supernet: 192.168.0.0/16
- Example IP address: 192.168.1.1/24
- Usage: Reserved for private network addresses, typically used within local area networks (LANs) such as in households or small office environments.

By following these guidelines, we ensure that our IP addressing scheme is both secure and straightforward, facilitating easier network management and troubleshooting. Any deviations from these simplifications will be explicitly noted and justified.
