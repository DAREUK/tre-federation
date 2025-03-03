**[DARE UK Federated Architecture Blueprint](../)**      v2.2

----

# Chapter 4 Federated architecture: infrastructure layer
## 4.4 Interface types

Interface services expose various capabilities for use by other members of the Federation. Note that traffic to and from all interface services route first through the [Security Servers](4_6_SDRI_Core_Services.md#462-security-server) of the host Participant (q.v.).

At this level of the architecture we do not specify the details of individual interface calls but instead classify interface services into a small number of types, each of which will have a defined security context. We leave open the definitions of particular interfaces to promote innovation and expansion within the Federation, while providing an overall framework within which services can be placed. For example, an interface service that moves datasets between TREs MUST NOT be usable by Researcher system actors.

Note also that we use the terms “incoming” and “outgoing” to mean “incoming from another Federation Participant” and “outgoing to another Federation Participant”. Interface services do not connect Federation Participants to the wider Internet.

### 4.4.1 Query (Direct)

The Query (Direct) interface type supports queries between TREs and other Federation services. These interfaces produce and consume [Query Objects](4_5_Structured_Data_Objects.md#453-query-object), where the executable part of the query is fully contained in the object payload.

Query (Direct) interface services MUST connect solely to other Query (Direct) interface services.

### 4.4.2 Query (Indirect)

The Query (Indirect) interface type supports queries between TREs and other Federation services. These interfaces produce and consume [Job Request Objects](4_5_Structured_Data_Objects.md#454-job-request-object), where the executable part of the query is not contained in the object payload itself but is instead hosted in an external repository and only referred to by the Job Request Object.

Query (Indirect) interface services MUST connect solely to other Query (Indirect) interface services.

### 4.4.3 Response

Responses are data generated by the execution of a query across several Federation services, whether direct or indirect. The model of federated queries assumed in the SDRI is entirely asynchronous and so we make a clear distinction between query and response interface types and do not assume a synchronous interaction between them. In practice, implementations of direct queries are very likely to require tight coupling between query and response interfaces (e.g., the coherent representation of remote datasets in a “single pane of glass” within a TRE Project Environment).

Response interface types produce and consume [Response Objects](4_5_Structured_Data_Objects.md#456-response-object).

The invocation of a Response interface service is triggered indirectly by the prior invocation of a Query service. Our working assumption is that, within the network of trust created by the SDRI Federation, responses can be returned safely to a querying entity without the need for IG intervention.

Response interface services MUST connect solely to other Response interface services. 

### 4.4.4 Data Ingress and Data Egress

In contrast to returning query results, Data Ingress and Egress services move complete sensitive Datasets (or large extracts of Datasets) between Federation Participants. This places them in a different security context to query/response interfaces. Data Ingress and Egress services must only be accessible to TRE Governance actors in Data Manager roles.

Data Egress services produce [Data Extract Objects](4_5_Structured_Data_Objects.md#451-data-extract-object), which Data Ingress services can consume.

Data Egress services MUST connect solely to Data Ingress services.

Conversely, Data Ingress services MUST connect solely to Data Egress services.

System actors with Data Manager roles SHALL be able to invoke Data Ingress/Egress services.

System actors without Data Manager roles SHALL NOT be able to invoke Data Ingress/Egress services.

### 4.4.5 Index

Index interface services provide a mechanism for TRE Governance roles and [Index Services](4_3_2_Index_Service.md) to exchange lists of personal identifiers, corresponding lists of depersonalised identifiers and master linkage spines for different Datasets.

Index interface services MUST connect solely to Index interface services.

As with Data Ingress/Egress services, system actors in Data Manager roles SHALL be able to invoke Index services.
System actors not in Data Manager roles SHALL NOT be able to invoke Index services.

### 4.4.6 Software

Software interface services provide a mechanism for TRE Operator roles to download and import approved software from a Federation Software Service. As described under Software Service, this may include environment software such as system components, standard analytics runtimes and packages, or research artifacts developed by Researchers and invoked via indirect queries.

Software interfaces produce and consume objects which encapsulate the approved software artifact.

Software interface services MUST connect solely to Software interface services.

System actors in TRE Operator roles SHALL be able to invoke Software interface services.

System actors not in TRE Operator roles SHALL NOT be able to invoke Software interface services.

### 4.4.7 Sync

Sync interface services provide a mechanism to maintain synchronisation of configuration state for Project Environments between multiple TREs. Details will be quite implementation specific but it is possible to model some general features.

Sync interfaces produce and consume [Project Sync Objects](4_5_Structured_Data_Objects.md#458-project-sync-object) which encapsulate the required configuration state. 

Sync interface services MUST connect solely to Sync interface services.

System actors in TRE Operator roles SHALL be able to invoke Sync services.

System actors not in TRE Operator roles SHALL NOT be able to invoke Sync services.


----

| [< Software Service](4_3_5_Software_Service.md) | - | [Structured data objects >](4_5_Structured_Data_Objects.md) |
| ---- | ---- | ---- |



