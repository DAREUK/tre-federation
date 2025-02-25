> DARE UK Federated Architecture Blueprint  v2.2
----

# Chapter 4 Federated architecture: infrastructure layer
## Structured data objects

Participants in the Federation communicate by exchanging structured data objects over a common data exchange layer. The common data exchange layer provides the required technical security controls for exchange between Participants (see [Security Server](4_6_SDRI_Core_Services.md)) but additional security controls may be applied to certain types of objects. 

Certain object types are closely associated with certain interface service types (see [Interface Types](4_4_Interface_Types.md)) and are produced and consumed by those interface services. Others are associated with Federation security control and are produced and consumed by underpinning security services.

The contents of structured data objects will depend on the particular interface services that produce or consume them.
The Federation requires that all objects to be exchanged between Participants MUST be packaged in a standard way.

### Data Extract Object

Data Extract Objects are datasets or subsets of datasets that have been approved by a Data Controller for specific uses within the Federation. Data Extract Objects will typically contain sensitive data, often de-identified but individual-level personal data. Data Extract Objects are exchanged by [TRE](4_3_1_TRE.md)s via [Data Egress and Data Ingress]](4_4_Interface_Types.md#data-ingress-and-data-egress) interface services. Use of Data Ingress and Egress interface services must be restricted to TRE Governance actors in roles of Data Manager.

Data Extract Objects are designated “SDC Red” in the architecture, meaning that, were they to be offered as candidates for release to the outside world, they would attract the most stringent statistical disclosure checks and would likely fail them. We reiterate, however, that the SDRI Federation is, by design, a closed environment and Data Extract Objects are only ever exchanged between TREs. Nevertheless, exchange of Data Extract Objects will require approvals from Data Controllers (in their roles as Data Custodians) to be in place, and MUST be overseen by TRE Governance Data Managers.

### Index Object

Index Objects are exchanged by TRE Data Managers and [Index](4_3_2_Index_Service.md) Services via [Index](4_4_Interface_Types.md#index) interface services. Index Objects do not contain sensitive data but could be said to contain “sensitive metadata”. Indexing individuals means that Index Objects will contain lists of personal identifiers and their exchange must be governed accordingly.

Index Objects are needed for certain kinds of data linkage. See [Data Linkage](../5_Data_Layer/5_5_Data_Interoperability.md) for a fuller treatment. 

### Query Object

Query Objects encapsulate direct queries and are produced and consumed by the 
[Query (direct)](4_4_Interface_Types.md#query-direct) interface type.
Direct queries can originate from Project Members working in Project Environments within a TRE, or from [Discovery Services](4_3_3_Discovery_Service.md) external to any TRE. In both cases they are targeted at one or more data resources remote from the calling service (i.e., hosted by another TRE). 

Where a query originates from a Project Member the Query Object MUST contain enough information for the receiving TRE to be able to make the necessary authorisation decisions. This information includes, but is not limited to:
 * Project Identity, in a form recognisable by the receiving TRE, indicating the project context this query is in;
 * Project Member Identity, in a form recognisable by the receiving TRE, indicating who submitted the query;
 * The target Dataset or Data Extract, in a form recognisable by the receiving TRE.

Where a query originates from a [Discovery Service](4_3_3_Discovery_Service.md) without an obvious Project context, how it is handled becomes a governance question to be codified in the Federation rulebook.

Query Objects are exchanged by [Query (direct)](4_4_Interface_Types.md#query-direct) interface services. Query Objects contain the full executable query for the remote data resource (e.g., as an SQL statement) and are not expected to contain sensitive data. In the architecture they are designated “SDC green”, meaning no form of output control is necessary before they can leave their originating environment.

A significant caveat to this last point arises where Query Objects might encapsulate partially trained deep neural networks in a federated machine learning setting, in which case they would be extremely likely to be sensitive at certain stages.
Again, though, we reiterate that Query Objects are exchanged between Federation Participants and not with the “outside world”. Thus, like all other structured data objects described here, their confidentiality, integrity and traceability are guaranteed by the secure data exchange layer common to all Federation Participants.

Note that we use “query” in a broad sense to encompass both the trivial (a microservice API call) and the complex (an encapsulated SQL script). In all cases, though, everything the receiving TRE needs to execute the query and create an appropriate response is encapsulated in the Query Object.

### Job Request Object

Job Request Objects encapsulate indirect queries and are produced and consumed by the
[Query (indirect)](4_4_Interface_Types.md#query-indirect) interface type.
Indirect queries originate from Job Submission components, originated either by Project Members working in Project Environments within a TRE, or from Job Submission Services external to any TRE. In both cases they are targeted at one or more data resources remote from the calling service (i.e., hosted by another TRE). 

As with direct queries, where the job request originates from a Project Member the Job Request Object MUST contain enough information for the receiving TRE to be able to make the necessary authorisation decisions. This information includes, but is not limited to:
 * Project Identity, in a form recognisable by the receiving TRE, indicating the project context this query is in;
 * Project Member Identity, in a form recognisable by the receiving TRE, indicating who submitted the query;
 * The target Dataset or Data Extract, in a form recognisable by the receiving TRE.

Where a job request originates from a Discovery Service without an obvious Project context, how it is handled becomes a governance question to be codified in the Federation rulebook.

Job Request Objects are exchanged by [Query (indirect)](4_4_Interface_Types.md#query-indirect) interface services. Job Request Objects do not contain executable payloads but instead contain “pointers” to executable artifacts held in external repositories (e.g., the URL of a CWL workflow). 

As with Query Objects, Job Request Objects are not expected to contain sensitive data and are designated “SDC green”, meaning no form of output control is necessary before they can leave their originating environment.

### Job Payload Artifact

Job Payload Artifacts encapsulate the executable artifacts referenced in Job Request Objects – the workflows, containerised applications or scripts prepared by Researchers in their role as Job Submitters and deposited in Internet-hosted repositories of some kind.

The artifacts themselves are retrieved from their repositories by [Software Services](4_4_5_Software_Service.md) which then package them into Job Payload Artifacts and return them to the requesting TREs via the [Software](4_4_Interface_Types.md#software) interface.

Job Payload Artifacts MUST be subject to a receiving TRE’s Job Approval process and MUST encapsulate sufficient information to enable the receiving TRE to assess their safety, in terms of the acceptability of their risk of execution. Because of these requirements it is possible, if not likely, that Job Payload Artifacts will be retrieved by TRE operations ahead of time, subjected to Job Approval and, if approved, cached locally within the TRE’s Artifact Cache in readiness for matching indirect queries. It is thus not safe to assume there is a synchronous connection between receipt of a Job Request and retrieval of a Job Payload.

### Response Object

Response Objects encapsulate the “answers” to queries submitted to TREs and are produced and consumed by the Response interface type.

Response Objects SHOULD have the same encapsulation structure for direct queries and indirect queries.

Response Objects may well contain data of high sensitivity: a direct query equivalent to “SELECT * FROM Person_table” will result in a Response Object equivalent to a Data Extract Object, for instance. In the architecture they are designated “SDC amber” but what level of oversight would be needed before a Response Object can leave its environment will depend on the context in which it was created. There are two scenarios we should consider. 

 1. Response Objects created in response to queries from an approved Project cannot, by definition, include data not already authorised for use by the Project Members. In this case Response Objects will either be returned to a Project Environment within a TRE, or to a secure Job Submission Service with an Output Control process in place. In neither sub-case is onward dissemination to the “outside world” possible without passing the Project’s approved disclosure control.
 2. Response Objects created in response to queries from a Discovery Service do not have an equivalent Project context, and are destined, by construction, to be disseminated to the “outside world” (this is a Discovery Service, after all). They must be handled differently, almost certainly handed directly to the Discovery Service’s Output Control process.

### Environment Software Artifact

Environment Software Artifacts encapsulate software artifacts used to construct Project Environments and are exchanged by Software interfaces.

In constructing and configuring Project Environments, TREs, rather than “downloading from source”, SHOULD request software artifacts from a Software Service. Not only does this provide an audit trail (the Software Service is a Federation Participant with a Security Server) but it also enables the Software Service to augment the software artifact with additional metadata and encapsulate everything in the Environment Software Artifact object.

### Project Sync Object

Project Sync Objects encapsulate information about required Project-Environment configuration state and are produced and consumed by Sync interface types.


----

| [< Interface types](4_4_Interface_Types.md) | - | [SDRI core services >](4_6_SDRI_Core_Services.md) |
| ---- | ---- | ---- |


