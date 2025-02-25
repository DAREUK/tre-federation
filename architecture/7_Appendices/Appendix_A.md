**[DARE UK Federated Architecture Blueprint](../)**      v2.2

----

# Appendix A. A comparison of contemporary federated data architectures

Annex III of the _Recommendation Report_ for the EU Smart Middleware Platform 
(SiMPl) [[23]](../References.md#ref-23) compares the concepts defined in the SiMPl architecture 
with those defined in the GAIA-X framework [[21]](../References.md#ref-21). The table
below extends this idea to include the concepts defined in this document and the equivalents from both
the IDSA reference architecture model (version 3.) [[22]](../References.md#ref-22) 
and the X-Road architecture [[17]](../References.md#ref-17).


| DARE UK | GAIA-X | SiMPl | IDSA | X-Road | Notes |
| ------- | ------ | ----- | ---- | ------ | ----- |
| Participant | Participant | Organisation that deploys an SMP Agent | Core Participant (also Intermediary) | Organization | |
| Federation Services | Federator | Data Space governance| Intermediaries, especially Clearing House, Identity Provider and Vocabulary Provider | Central Services & Trust Services| | 
| Security Server | Sovereign Data Exchange | SMP Agent | IDS Connector | Security Server | The GAIA-X mapping is imprecise.  It factors out a number of functions that are encapsulated in the other four models.| 
| TRE | Consumer or Service instance |  Composite of Application Provider and Infrastructure Provider |  Service Provider; Composite of Data Consumer and Data Provider |   Service Consumer Information System |   A DARE UK TRE has no direct equivalent but is a specialized example of a generic data consuming service.| 
| Data Provider / Data Custodian | Provider | Data Provider | Data Provider | Service Provider Information System | | 
| Researcher (User) | End User | End user | Data User | Data Requestor| | 
| Discovery Service | Catalogue | Data catalogue | Broker Service Provider | Service Provider Information System | A catalogue or discovery service in X-Road would be a specialised kind of Information System hosted by a Service Provider.| 
| Index Service; Software Service | Consumer or Service instance | Composite of Application Provider and Infrastructure  Provider | Service Provider | Service Provider Information System | All DARE UK services can be modelled the same way in terms of their interaction with the federation structure. | 


