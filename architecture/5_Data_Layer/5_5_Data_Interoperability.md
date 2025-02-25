> DARE UK Federated Architecture Blueprint  v2.2
----

# Chapter 5 Federated architecture: data layer
## Data interoperability

So far within the architecture we have recognised the fundamental importance of data interoperability in the form of data linkage but our treatment has been deliberately naïve. There are multiple levels on which to consider data interoperability and most of these are out of the scope of a federated architecture. Nevertheless we note them here and may expand on them in future iterations.

### Syntactic interoperability

The most straightforward level of interoperability is syntactic or schema-level: are the datasets to be connected the same shape in at least one of their dimensions? In the horizontally and vertically partitioned dataspace we introduced in [Section 2.2](../2_Strategic_Case/2_2_The_Federation_Challenge.md) there are two strong assumptions:
 * EITHER the datasets have the same set of data subjects in the same order (e.g., different sets of attributes about the same group of people, ordered the same way);
 * OR the datasets have the same set of attributes in the same order (e.g., the same set of attributes about two different groups of people).

Connecting datasets by these criteria is reasonably straightforward; relational databases are very good at exactly this kind of thing. Even differences in the ordering are easy to manage, by sorting, for example. We may need to define rules to handle gaps in the resulting dataset (either common rules or context-specific ones) but again, this is a well-understood area.

It is feasible to imagine an Index Service which could automate the linkage of two datasets under these conditions.

### Terminological interoperability

Simple syntactic joining becomes harder when two datasets are probably interoperable but have been put together with slightly different terms. For example:
 * Surname; Christian Name; Age;
 * Given Name; Family Name; Age;
 * Nom; Prénom; Age.

Human experience tells us that these three datasets most likely record the same information (even with the transposition of name parts and dual languages in play). An equivalent level of experience for an automated service could be created using terminology bases, in much the same way that computer-assisted translation tools work today. (The proposed EU Smart Middleware Platform architecture includes just such a vocabulary service [[23]](../References.md#ref-23).)

By introducing one or more terminology services, it is feasible to imagine an Index Service which could automate the linkage of two datasets under these conditions.

### Semantic interoperability

By far the most complex level of interoperability is semantic: two data items may have the same name but the way they were recorded might be very different. Different people, in different contexts, under different time pressures, might record nominally identical data items in subtly different ways which make them non-interoperable in ways almost impossible for an automated system to identify.

Another semantic variant arises in linkage between two or more datasets which each contain a number of data elements that, either alone or combined, mean nearly the same thing. Here, human intervention can harmonise the datasets, perhaps by introducing a new, common element, constructed differently in different datasets but which is nevertheless equivalent between them. Whether this kind of harmonisation could be achieved outside the TRE, working purely with dataset schemas and terminology sets (cf. [Section 5.4](5_4_Data_Accessibility.md)), is likely to be highly case dependent.

It is difficult to imagine a scenario in which an Index Service could automate the linkage of two datasets under these 
conditions.

### Data linkage
With the caveats noted above we have introduced a model of data linkage within the federated architecture which can, in principle, be automated (at least to some extent). Our model makes three design assumptions:
 * Linkage between Data Extracts for a Project is done using a common linkage spine, which may be created explicitly for the Project or may be persistent.
 * Linkage spines are created and maintained by Indexing Services which are trusted third-parties (“TTPs”) independent of TREs or a Project’s information governance.
 * Identifiers used in the linkage spines are transformed as part of the linkage process into Project-specific identifiers. Such identifiers have no meaning outside the Project and thus cannot be used, by themselves, to link to anything else.

Linkage spines are exchanged between Federation Participants as structured documents.

----

| [< Data accessibility](5_4_Data_Accessibility.md) | - | [Data reusability >](5_6_Data_Reusability.md) |
| ---- | ---- | ---- |


