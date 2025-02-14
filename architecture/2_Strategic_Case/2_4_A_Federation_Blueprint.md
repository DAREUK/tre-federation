# DARE UK Federated Architecture Blueprint - Part 2 (Strategic Case)

## A federation blueprint

In the rest of this blueprint we describe a UK-wide federation of sensitive data research infrastructure—
the SDRI Federation, or simply “the Federation”—built on common standards, with a small number of
registry and coordination services, designed to support a wide, rich ecosystem of TREs and other services.
The Federation is designed to be trustworthy, with a common set of low-level security protocols and
standards for secure data exchange, on top of which is built a rich set of application protocols and
standards to support different analytical use-cases—federated analytics, data pooling, federated machine
learning or something else. It starts from where we are—an existing ecosystem of largely independent
TREs—and builds on the ideas of federation touched on in the 2020 Health Data Research Alliance Green
Paper on TREs [[6]](../References.md#ref-6) and expanded in a companion paper 
from 2021 [[7]](../References.md#ref-7).

The low-level protocols and standards would define, at a purely technical level, what it means to join the
Federation—chapter one of its “rulebook”, if you will. Other rules of engagement should, in time, come to
supplement the technical—should participants require certain levels of formal accreditation before they
can join the Federation, for instance? Development of the Federation rulebook beyond the purely
technical is fundamentally a question of governance and we only touch on it here where it has a direct
bearing on the technical blueprint. How the Federation should be managed and run are decisions to be
taken by the broadest stakeholder community.

The organisation of the Federation could be designed in a number of ways. A key requirement is that the
Federation organisation and overseeing authority, any registry services and the low-level data exchange
protocols must be designed to ensure that all members of the Federation can trust one another and that,
once a Participant has joined, they enjoy the same levels of trust as all other Participants. This is our
definition of _trustworthy_. Note that this statement applies to _service Participants_ in the Federation, not to
researchers or projects or access to sensitive datasets. Governance for approving projects, encapsulating
data and researchers in authorised contexts, requires the same rigour in approval and access management
as it does today. The organisation of the Federation is a new concept, not a replacement for existing data
governance approaches.

### Scope

In the following chapters we divide the SDRI Federation into three layers and consider each in turn. Each
layer underpins each subsequent one.

1. Infrastructure. The lowest level we discuss, infrastructure considers the services and functionality
    necessary to realise the Federation, rather than network hardware or any particular technology.
2. Data. The infrastructure layer can exist perfectly well without data but would be uninteresting. The
    mechanisms by which data are discovered, linked and made accessible are considered within the data
    layer.
3. Organisational. The highest level considered here, we use “organisation” to refer to oversight of the
    Federation infrastructure, its operational model and the definition of the “rulebook” for service
    onboarding, technical standards and change management.

Most of the focus of this blueprint is on the infrastructure layer. Some discussion of data standards and
technical governance is essential to set the infrastructure in context, but detailed treatments of these two
topics are out of scope of this document.


### Design principles

DARE UK’s approach to the design and build of a federated network for research with sensitive data
follows a number of principles, closely aligned with the SATRE principles.

1. Public trust first, last and always. The strongest design voice should come from the “public
   persona”. (SATRE: Maintaining public trust.)
2. No TRE, no data. Reinforcing a recommendation from the Goldacre Review [[33]](../References.md#ref-33), 
   require that any and all analysis of sensitive data take place within a TRE, and design accordingly.
   (SATRE: Maintaining public trust.)
3. Start from where we are. Much of the service ecosystem already exists. Our blueprint must arise
   through co-design with existing and emerging practitioners.
4. Five Safes are better than one. Secure infrastructure is only one aspect of a TRE. Adopt the Five
   Safes framework [[34]](../References.md#ref-34) as a guiding principle. 
   Processes and governance are as important as infrastructure, and infrastructure choices 
   should reflect this. (SATRE: Maintaining public trust.)
5. Separation of concerns. Different system actors have very different “security clearances”. Their
   interactions should be segregated from one another as far as possible.
6. An open-standards-based ecosystem. We seek a rich ecosystem of varied services interoperating
   through agreed standards. (SATRE: Standardisation.)
7. Be as FAIR as possible. Findability, accessibility, interoperability and reusability are excellent
   qualities to maintain even in a sensitive data environment [[37]](../References.md#ref-37). (SATRE: Usability.)
8. The “IETF principle” [[38]](../References.md#ref-38): rough consensus and running code 
   over rigid specifications and monolithic stacks. Nucleate advances in small groups and grow outwards.
9. Open source first. Seek as often as possible to avoid proprietary lock-in. Strictly, the scope of this
   principle is that of the networked components defining the federation core. Beyond this core
   scope, “open standards” (principle 6) is the better arbiter. (SATRE: Standardisation.)
10. Low barriers. Strive to reduce barriers for researchers and for data providers. (SATRE: Usability.)
11. Observability. Human initiated and automated processes resulting in change within the TRE
    network should be observable. (SATRE: Observability.)


