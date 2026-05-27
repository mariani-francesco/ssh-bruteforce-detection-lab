# Enumeration and Service Discovery Phase

## Objective

The objective of this phase is to identify reachable hosts within the lab environment and enumerate exposed network services on the target system.

This phase focuses on understanding the target’s visible attack surface before simulating authentication-based activity in the next phase.

---

## Target Information

The target system is an Ubuntu Linux machine deployed inside the controlled lab environment.

**Target IP address:** `192.168.142.129`

---

## Service Enumeration

Network service enumeration was performed using Nmap in order to identify open ports and service versions exposed by the target system.

### Command

```bash
nmap -sV 192.168.142.129
```

The `-sV` option enables service version detection, that allow the Nmap command to identify: open ports, service names, and service versions where possible.

---

## Findings

The scan identified one exposed service on the target system:

| Port | State | Service | Version |
|---|---|---|---|
| 22/tcp | Open | SSH | OpenSSH 9.6p1 Ubuntu |

The presence of SSH indicates that remote login functionality is available on the target system.

---

## Security Assessment

The target system exposes an SSH service over the network.

While SSH is a legitimate remote administration service, it represents a common attack surface when exposed to untrusted networks. If weak credentials, password authentication, or insufficient access controls are present, the service may be targeted for unauthorized login attempts or brute-force activity.

The discovered SSH service was selected as the focus of the next phase, where credential-based authentication attempts will be simulated in a controlled environment.

---

## Conclusion

The enumeration phase confirmed that the target host is reachable and exposes SSH on port `22/tcp`.

This finding provides the technical basis for the next phase of the lab, where authentication activity against the SSH service will be generated and analyzed.
