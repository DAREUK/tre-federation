> DARE UK Federated Architecture Blueprint  v2.2
----

# Chapter 4 Federated architecture: infrastructure layer
## Related concepts

### Projects

The Project is a key concept in the use of the SDRI Federation. A Project defines a context for an approved research activity, including the Project Members involved, information about the data they are authorised to use, the TRE that hosts it, its duration and so on. A Project defines an authorisation context which provides a key piece of information for overall SDRI governance (cf. [Chapter 6](../6_Organisational_Layer/6_1_Introduction.md)).

All Projects MUST be registered with the Federation’s Registry services. An example of the kind of metadata required in a Project’s Registry entry is offered in the section on [Project metadata](../5_Data_Layer/).

Simple Projects, typical of most current projects across the UK TRE landscape, will follow the data pooling pattern of access ([Chapter 2](../2_Strategic_Case/2_2_The_Federation_Challenge.md)). They involve one TRE with a Research Analytics Zone (the host), a number of TREs acting as data providers and, potentially, a trusted third-party Index Service.

More complex Projects will follow the federated analytics pattern ([Chapter 2](../2_Strategic_Case/2_2_The_Federation_Challenge.md)) and involve direct and indirect queries across multiple TREs with Query Management Zones capable of processing incoming query objects. For the purposes of governance and authorisation context, one TRE MUST be designated as the “host” or “instigator” of the Project.

The most complex Projects will potentially require a mix of data pooling—perhaps in an initial exploratory or development phase—and federated analytics—a “full production run” across remote data. For such Projects, one TRE should be designated as the host for the data pooling phases and, by construction, the “host” for the Project overall. This complex pattern anticipates large-scale federated machine learning across complex datasets (such as medical image stores). 

### Federation identities

Many elements of the SDRI Federation will have an identity and a number of attributes that can be used by system components and other system actors to reason about them. For example, a research user could have an identity and an associated list of active projects of which they were a member. Taken together, this information could be used by a remote data provider to decide whether or not to allow a query from that user to run in a particular project context.

These “Federation identities” must be unique within the Federation but do not necessarily need to have meaning outside the Federation. For the user example, the user’s Federation identity could be implemented as an SSO Token, for instance. This is further discussed below.

Implementation details are not dealt with here, but the table illustrates some of the required identities and some possible attributes for them. Attributes like this should be captured and recorded in metadata (cf. [Section 5.2](../5_Data_Layer/5_2_Federation_Metadata.md)).

| Identity type	| Example attributes | 
| ------------- | ------------------ | 
| Participant	| Name; List of interfaces supported; List of capabilities accessible to the Federation; etc.| 
| Researcher / Project Member	| Name; Home institution (organisation vouching for their bona fides); Home TRE (TRE vouching for their access to the Federation); List of projects they are currently associated with (“currently” requires each membership be time-bound); etc.| 
| Project	| Name; List of current members (using their Federation identities; again, “current” requires these be time-bound); List of datasets associated with the project; Agreed disclsure control strategy; etc.| 
| Dataset	| Name; Data controller; Home service (Federation identity of the service regarded as the canonical source for this dataset); etc.| 
| Data Extract	| Name; Data controller; creation criteria (e.g., cohort definition); etc.| 
| Linkage Spine	| Identity of associated project; List of identities of associated datasets; etc.| 

### Authentication and authorization

The authentication of Researchers’ identities and their subsequent authorisation to access Projects, Datasets and other Federation resources are split into two stages. This two-tier approach is not uncommon in large-scale federated environments (cf., for example, Appendix III of the Architecture Vision of the proposed EU Smart Middleware Platform [23]). To support a rich ecosystem of participants deploying different technology stacks, it is also necessary.

The sequence of events runs like this.
 1. Two TREs establish a trust relationship, brokered by the Federation Services and using the Federation’s foundational trust services. This “server to server” trust relationship is a standard approach to securing services across the Internet and is typically implemented using X.509 certificates and a public key encryption infrastructure. (We do not cover the details here.) At a foundational level, this is what joining the Federation as a Participant means.
 2. A Researcher then authenticates themself to “their” TRE using the TRE’s locally preferred authentication mechanism. This may be Microsoft Active Directory, Linux LDAP/X509, OpenID Connect or a number of other technologies. The TRE may support more than one authentication mechanism for different kinds of user identity (federated identity management).
 3. The authenticated Researcher’s local identity is mapped onto an internal Federation identity using a common format which all participants in the Federation agree to support. Attributes associated with this identity can then be used by other Federation participants to reason about the Researcher, to make, for instance, authorisation decisions about granting the Researcher access to Projects, Datasets or other resources (single sign-on).

This division also helps enforce the principle of “no TRE, no data”: Researchers access Datasets only through TREs, never directly. It also follows from “start from where we are” and “a standards-based ecosystem”, allowing TREs to continue to serve their user communities in the best way while providing common back-office connections to federated resources.






