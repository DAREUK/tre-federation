> DARE UK Federated Architecture Blueprint  v2.2
----

# Chapter 4 Federated architecture: infrastructure layer
## 4.2 Actors and roles

We resolve the federation users identified in Chapter 3 into _actors_ and _roles_ in the infrastructure picture. Actors are actual individuals or small teams. Roles capture specific activities or responsibilities taken on by actors.

### 4.2.1 Researcher (actor)

Researchers take on a number of roles within the overall federated system. We use these roles to model their interactions with TREs and other services.

#### 4.2.1.1 Project Member (role)

A Researcher may become an approved and authorised member of one or more Projects (see below), and in that role (and in the context of these Projects) will interact with specially provided project environments within one or more TREs. Access to data within a TRE is granted to a Researcher in their role as a Project Member, on the basis of their individual project authorisations.

#### 4.2.1.2 Job Submitter (role)

(Possibly a sub-role of Project Member.)

In contrast to the direct interaction of a Project Member, the Job Submitter role interacts indirectly with TREs through externally accessible Job Submission and Software services.  

#### 4.2.1.3 Catalogue Searcher (role)

The Catalogue Searcher role interacts with externally accessible data discovery and catalogue services. In this role the Researcher need not be a member of an existing project, and thus may not have approvals to access sensitive data of any sort.

### 4.2.2 Information Governance (actor)

Information Governance is a shorthand for the team of people charged with overseeing a TRE and the research that happens within it. The Information Governance actor takes a number of data-related roles. They may also take the role of TRE Operator, or may delegate it (see below). 

#### 4.2.2.1 Data Manager (role)

This role covers a wide range of data management tasks within a TRE, from curating and maintaining long-term copies of research-ready data, to receiving data extracts from other Data Managers in other TREs, linking them and providing them onwards to research Project Members within the TRE. The Data Manager role will typically work closely with the Data Custodian role (see below).

This role could be further broken down into finer-grained sub-roles. 

#### 4.2.2.2 Output Approver (role)

Output Approvers are responsible for checking any and all research outputs to be released from the TRE to the “outside world” (rather than sent to another TRE).

#### 4.2.2.3 Job Approver (role)

Job Approvers review computational jobs submitted by Researchers (in their roles as Job Submitters) for their safety and suitability to run inside the Job Approver’s TRE. 
file:///C:/Users/RobBaxter/Box/Rob%20Baxter/DAREUK/architecture/4_Infrastructure_Layer/4_3_Participants.md
### 4.2.3 Data Controller (actor)

#### 4.2.3.1 Data Custodian (role)

In the TRE domain, Data Controllers take the role of Data Custodians, releasing data approved for research to projects via TRE Data Managers.

### 4.2.4.TRE Operator (actor)

#### 4.2.4.1 TRE Operator (role)

The TRE Operator runs the TRE technical service day-to-day. This role may be taken by the Information Governance actor, or it may be delegated by them to a different actor (the TRE Operator actor) under their direction.

----

| [< Introduction](4_1_Introduction.md) | - | [Participants >](4_3_Participants.md) |
| ---- | ---- | ---- |



