# SOC-Lab-Documentation
Joshua Sartains SOC Repository for logging anmd proofs

# SOC.lab — Security Operations Center Lab Documentation and Infrastructure Project

SOC.lab is a segmented, virtualization-backed Security Operations Center environment designed to model real-world security engineering, detection operations, endpoint response, and infrastructure control.

This repository serves as the **central project record** for the full SOC.lab build, including:

- low-level topology documentation
- infrastructure and security architecture
- formal Standard Operating Procedures (SOPs)
- deployment standards
- integration workflows
- operational guidance for monitoring, response, and maintenance

This is not just a tool collection. It is a documented SOC environment built to show how identity, networking, virtualization, endpoint security, SIEM, SOAR, and operational process work together as one system.


## Project Purpose

The purpose of SOC.lab is to build and document a functional SOC environment that demonstrates:

- security-focused systems engineering
- segmented network architecture
- centralized monitoring and endpoint response
- formal operations documentation
- practical security workflow design
- portfolio-grade infrastructure and cybersecurity capability

The project is designed to bridge the gap between isolated classroom exercises and real operational thinking.


## Repository Scope

This repository contains the working documentation and architecture for the SOC.lab environment.

It includes:

- the low-level SOC topology
- infrastructure deployment SOPs
- integration SOPs
- network segmentation documentation
- SIEM and SOAR workflow design documentation
- endpoint security deployment guidance
- operational maintenance procedures

This repository is intended to function as the **authoritative documentation baseline** for the SOC.lab project.


## Environment Overview

SOC.lab is built around a hybrid internal architecture using virtualization, segmentation, centralized monitoring, and endpoint response.

### Core Components

- **Hyper-V**
  - primary virtualization platform
  - hosts core infrastructure and security workloads

- **Active Directory**
  - identity and authentication authority
  - supports domain services, access control, and policy enforcement

- **RDS / Thin Client Access**
  - centralized analyst and user access model
  - reduces endpoint sprawl and improves operational consistency

- **OPNsense**
  - central firewall, routing, and segmentation enforcement point
  - controls traffic between SOC network zones

- **Wazuh**
  - SIEM and log analysis platform
  - supports detection engineering, alerting, and MITRE ATT&CK-aligned monitoring

- **OpenEDR**
  - endpoint investigation and response platform
  - supports threat handling, containment, and endpoint-level visibility

- **Splunk SOAR**
  - workflow and automation design layer
  - supports enrichment, triage acceleration, and controlled containment logic

- **Tenable**
  - vulnerability and exposure context source
  - used to improve prioritization and response logic

- **Microsoft Intune**
  - primary device governance and policy control platform
  - used for stronger endpoint management and baseline control

---

## Architecture Model

The environment is built using segmented SOC network zones to separate functions, reduce lateral movement risk, and improve control boundaries.

### Segment Examples

- **SOC-MGMT**
  - management and administrative traffic

- **SOC-LAN**
  - internal analyst and workstation traffic

- **SOC-SIEM**
  - monitoring, logging, and security analytics systems

- **SOC-SERVER**
  - internal server workloads and service infrastructure

- **SOC-LAB**
  - controlled research, testing, and validation zone

- **SOC-USER**
  - thin-client or user-side operational path

- **SOC-WAN**
  - upstream connectivity path

This segmentation model is enforced through firewall policy, virtualization design, and controlled routing.


## Topology

A low-level SOC topology is included as part of this project and documents the relationship between:

- thin clients
- RDS infrastructure
- Active Directory
- Hyper-V
- switching fabric
- OPNsense firewall
- Wazuh
- OpenEDR
- internal server systems
- WAN/internet path
- physical support components such as power/network dependencies

The topology is used as the architectural reference point for the SOP set and should be updated whenever major infrastructure changes occur.


## Documentation Set

This repository is centered around the SOP library for SOC.lab.

### Current SOP Coverage

The project documentation includes SOPs for:

- Hyper-V host installation and setup
- Hyper-V network and interface reconfiguration
- Active Directory administration
- RDS thin-client deployment and Intune registration
- OPNsense deployment for segmented SOC infrastructure
- VLAN segmentation with router-on-a-stick and ACL isolation
- Wazuh security monitoring platform installation
- SIEM MITRE ATT&CK integration rule set implementation
- Splunk SOAR automated workflow design
- OpenEDR setup and integration

Additional SOPs are expected to be added as the environment matures.


## Operational Philosophy

SOC.lab is designed around the idea that security infrastructure should be:

- segmented
- observable
- controllable
- documented
- testable
- supportable by other operators

The project places strong emphasis on turning infrastructure into something that can be handed to another engineer or analyst without depending entirely on tribal knowledge.


## Detection and Monitoring Philosophy

The monitoring stack is designed around layered visibility.

### Wazuh Role

Wazuh serves as the primary SIEM layer for:

- centralized logging
- rule tuning
- security event monitoring
- ATT&CK-aligned detection workflows
- cross-source correlation support

### OpenEDR Role

OpenEDR serves as a fast endpoint investigation and response layer for:

- endpoint-related alerts
- analyst response actions
- process-level response
- endpoint-specific visibility
- case and investigation support

### Intune Role

Intune remains the stronger platform for:

- endpoint policy
- device control
- management baselines
- administrative configuration authority

### SOAR Role

Splunk SOAR is used as a workflow design and orchestration layer for:

- enrichment
- analyst acceleration
- controlled containment
- case support
- vulnerability-informed prioritization through Tenable context


## Response Model

SOC.lab uses a layered response approach rather than uncontrolled automation.

### Workflow Model

1. detect
2. enrich
3. validate
4. prioritize
5. contain if justified
6. document
7. review and tune

This allows automation to support analysts without blindly replacing analyst judgment.


## Validation Approach

The environment is validated through controlled functional testing rather than installation alone.

Validation examples include:

- agent check-in testing
- SIEM ingestion validation
- endpoint response testing
- firewall segmentation verification
- Active Directory access validation
- RDS functional testing
- SOAR enrichment workflow testing
- vulnerability-context prioritization
- 1:1 control validation on test servers

This project treats validation as part of engineering, not as an afterthought.
