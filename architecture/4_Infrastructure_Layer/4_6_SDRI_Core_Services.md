> DARE UK Federated Architecture Blueprint  v2.2
----

# Chapter 4 Federated architecture: infrastructure layer
## SDRI core services

Core Services are a number of common services that together define the SDRI Federation. They include a set of Federation Services and a number of distributed Security Servers, one per Federation Participant. 

All Core Service MUST be connected in a secure network which is independent of the Federation data exchange network.

### Federation Services

The SDRI’s Federation Services provide the coordinating functions and gatekeeping, registration and discovery services which, taken together, define the SDRI Federation. The lowest level of the Federation layer is agnostic towards both the nature of any exchanged objects and the purposes for which they are exchanged (see [Structured Data Objects](4_5_Structured_Data_Objects.md)).

There is only one set of Federation Services.

Federation Services MUST be highly available.

#### Accounting
Accounting services provide the means to track and record resource use across the Federation. In scenarios where remotely-executed queries may become complex, long-running workflows, a view of what costs are incurred where will become important.

#### Management

Management services provide the necessary tools for the operators of the Federation to maintain and run it to its agreed levels of service.

Management services MUST support mechanisms to ensure Security Servers across the Federation are up-to-date and synchronised with the currently agreed and approved global configuration.

#### Monitoring

Monitoring services include infrastructure monitoring for service availability and general system health and operational monitoring of the data exchange layer to ensure the necessary levels of confidentiality, integrity and auditability are being met.

#### Registry

Registry services record information about the different pieces of the Federation. There are a number of key records that MUST be recorded in the Registry:

 * Federation Participants. Which Participants, defined by their security servers (qv), are part of the Federation. There are five kinds:
   - TREs;
   - Job Submission Services;
   - Software Services;
   - Discovery Services;
   - Index Services.
 * Datasets. Datasets are provided by Data Custodians and made available for use in TREs.
   - See Data topics later. 
 * Projects. In Federation terms Projects provide contexts which encapsulate Researcher users and Datasets into approved pieces of work.
 * Users. Each and every user of the federation must be registered.

#### Trust

Trust services provide the necessary services for securing the foundational data exchange layer of the Federation. These services support the key security requirements of confidentiality, integrity, non-repudiation and availability. Trust services may include timestamping, encryption key management, security certificate management and so on.

In any implementation, trust services may be provided by trusted third-party suppliers.
> For a good discussion of trust services in the context of the UK eIDAS regulation, see the relevant pages at the UK Information Commissioner’s Office, https://ico.org.uk/for-organisations/guide-to-eidas/

### Security Server

Security servers act as the gateways of every Federation Participant and are the only components of the Federation that interact directly with each other and with the other Federation Services. The security features required of a Federation Participant are as far as possible abstracted into the Security Server. In particular the Security Servers provide the agency for the secure data exchange layer and hence are the guarantors of the confidentiality, integrity and auditability of inter-Participant exchanges within the Federation.

Every Federation Participant MUST run a Security Server.

Security Servers MUST operate to an agreed and approved global configuration.

Security Servers MUST support a mechanism to synchronise their configuration with the agreed global configuration.

If control-plane connectivity to Federation Management Services is interrupted, Security Servers MUST be able to continue operating independently.



