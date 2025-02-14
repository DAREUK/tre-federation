> DARE UK Federated Architecture Blueprint  v2.2
----

# Appendix B. Usage patterns

How well does this architecture model existing patterns of inter-TRE communication and federation?

This second version has been guided by work ongoing through 2023 and by interactions with key stakeholders and service operators through the UK TRE community . 

Below we map published information about other patterns of TRE federation against the architecture picture in 
[Chapter 4](../4_Infrastructure_Layer/4_1_Introduction.md).

## “Classic” TRE inter-operation

This model is an amalgamation of many current TREs which feature virtual desktop access to project environments and access to approved datasets.

Features:
 * Data pooling model.
 * Isolated research projects.

Elements:
 * TRE “a” (left), acting purely as a data provider.
 * TRE “b” (right), acting as both a data provider and analytics service provider.
 * Index service, providing linkage spines.
 * Software service, providing packages and other software components for the analytical project environments.

[![](../assets/images/federation-2-Classic_TRE_Federation_v2.0.jpg)](../assets/images/federation-2-Classic_TRE_Federation_v2.0.jpg)


## Francis Crick Institute federation model

Reference: 
 * The Francis Crick Institute, Trusted Research Environments – federating data to 
   complete research [[55]](../References.md#ref-55).

Features:
 * TRE federation realised dynamically on a per-project basis.
 * Separation of project analytics from data sources.
 * Direct query model.

Elements:
 * TRE “c” (upper right), acting purely as an analytical project environment, presenting a view of remote data to project members.
 * SDE “b” (lower right) (“secure data environment”, a “static data TRE” in [[1]](../References.md#ref-1)), acting purely as a data provider with a remote presentation of data to TRE “c”.
 * SDE “a” (left), acting purely as a data provider with a remote presentation of data to TRE “c”.
 * Other project-specific SDEs (not illustrated in full).
 * Federation between these elements on a per-project basis.

[![](../assets/images/federation-2-Crick_TRE_Federation_v2.0.jpg)](../assets/images/federation-2-Crick_TRE_Federation_v2.0.jpg)


## OpenSAFELY

Reference:
 * OpenSAFELY, The OpenSAFELY Secure Analytics Platform [[28]](../References.md#ref-28) and particularly https://docs.opensafely.org/images/c4-container.svg 

Features:
 * Indirect query model.
 * Researcher code and job development via local development tools (OpenSAFELY command line interface) and public repositories (notably GitHub, OpenCodelists).
 * Job submission from outside TRE environments.

Elements:
 * Job Server (upper right), acting as the point of interaction between researchers and TREs.
 * Secure environment “a” (left), acting as a data provider and job handler.
 * Secure environment “b” (right), acting as a data provider and job handler.
 * GitHub (lower right), acting as a software service.

[![](../assets/images/federation-2-OpenSAFELY_TRE_Federation_v2.0.jpg)](../assets/images/federation-2-OpenSAFELY_TRE_Federation_v2.0.jpg)


## TELEPORT federation with pop-up TREs

Reference:
 * C. Orton, et al. TELEPORT: Connecting Researchers to Big Data at Light Speed [[29]](../References.md#ref-29).

Features:
 * Direct query model using polystore presentation.
 * Dynamically-provisioned pop-up TREs with keep-alive sync to “mutually approved” state.
 * GitOps synchronisation between participating TREs.

Elements:
 * TRE “a” (left), acting as both data provider with remote data presentation, and potential provider of analytical project environments. 
 * TRE “b” (right), acting as both data provider with remote data presentation, and potential provider of analytical project environments. 
 * Package repo (upper left), providing software components for dynamic provisioning of project environments to mutually approved state.
 * Continual policy sync between TREs “a” and “b”.

[![](../assets/images/federation-2-TELEPORT_TRE_Federation_v2.0.jpg)](../assets/images/federation-2-TELEPORT_TRE_Federation_v2.0.jpg)


## TRE-FX federation with stand-alone job submission

References:
 * T. Giles, et al. TRE-FX: Delivering a Federated Network of Trusted Research Environments to Enable Safe Data Analytics [[27]](../References.md#ref-27).
 * T. Giles, et al, [TRE-FX primary implementation report](https://docs.google.com/document/d/1FxrwXoYjx5aUI3MQyrnHs7xigvATJMEn/)

Features:
 * Indirect query model.
 * Researcher code and job development via local development tools (Bitfount, DataSHIELD) and public repositories (notably WorkflowHub and DockerHub).
 * Standardised packaging methods for exchanged digital objects.
 * Job submission from outside TRE environments.
 * Single registry of projects and users.

Elements:
 * Secure environment “a” (left), acting as both a data host and job handler.
 * Secure environment “b” (right), acting as both a data host and job handler.
 * Submission layer (upper right), acting as both a job submission service and a common lookup-registry for projects, users and data.
 * WorkflowHub and DockerHub, acting as software services for researcher-developed artifacts.

[![](../assets/images/federation-2-TRE-FX_Ext_TRE_Federation_v2.0.jpg)](../assets/images/federation-2-TRE-FX_Ext_TRE_Federation_v2.0.jpg)


## TRE-FX federation with TRE-hosted job submission

References:
 * T. Giles, et al. TRE-FX: Delivering a Federated Network of Trusted Research Environments to Enable Safe Data Analytics [[27]](../References.md#ref-27).
 * T. Giles, et al, [TRE-FX primary implementation report](https://docs.google.com/document/d/1FxrwXoYjx5aUI3MQyrnHs7xigvATJMEn/)

Features:
 * Indirect query model.
 * Researcher code and job development via local development tools (Bitfount, DataSHIELD) and public repositories (notably WorkflowHub and DockerHub).
 * Standardised packaging methods for exchanged digital objects.
 * Job submission from inside TRE project environments.
 * Single registry of projects and users.

Elements:
 * Secure environment “a” (left), acting as both a data host and job handler.
 * Secure environment “b” (right), acting as an analytical project environment, a data host and job handler.
 * Submission layer (upper right), acting as both a job submission service and a common lookup-registry for projects, users and data.
 * WorkflowHub and DockerHub, acting as software services for researcher-developed artifacts.

[![](../assets/images/federation-2-TRE-FX_Int_TRE_Federation_v2.0.jpg)](../assets/images/federation-2-TRE-FX_Int_TRE_Federation_v2.0.jpg)


