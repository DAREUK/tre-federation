> DARE UK Federated Architecture Blueprint  v2.2
----

# Chapter 5 Federated architecture: data layer
## Data findability

The Federation “content metadata” records introduced in the previous section are examples of the types of information that need to be captured and recorded in the Registry services of the Federation, but are largely useless in helping researchers find what data might actually be available to support their research within the Federation. As described in Section 3.1 Rachel’s Journey this data discovery needs to happen outside the Federation, before a researcher has even defined the project they might ultimately propose.

A consequence of this is that data findability, or discovery, is not a core use-case for the SDRI Federation. The Federation does, however, have a role to play in supporting data discovery where it can—maintaining a record of what datasets from which providers are available in which TRE with what linkages available—and ensuring that such information can be accessed usefully in standard ways from outside the Federation without compromising its secure perimeter.

The Federation architecture as proposed does permit the exposure, via query interfaces, of metadata from the Federation to the public Internet. By this statement we mean there is nothing proposed in the architecture that renders this impossible. Whether and in what form it might be realised is currently left as a question of governance and of implementation. Possible approaches to exposing public metadata from controlled environments can be found in the GA4GH Beacon work [51] and in the HDR-UK CO-CONNECT work [52].


### Discovery metadata

The [ELIXIR Ontology Lookup Service](https://www.ebi.ac.uk/ols/ontologies) hosts 280 life-science ontologies. 
The NHS list of [approved national information standards](https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections ) counts 90 standards and twice as many collections, while the NHS Data Model and Dictionary describes over 2,750 data elements. 
The [INSPIRE Technical Guidelines](https://inspire.ec.europa.eu/documents/inspire-metadata-implementing-rules-technical-guidelines-based-en-iso-19115-and-en-iso-1) on metadata implementation for geospatial data run to 99 pages.

Harmonising data discovery in such a landscape is simply intractable. The best we can hope for across a federation of data resources and analysis environments is to adopt common basic discovery metadata which is aligned with metadata standards used by the likely largest sensitive data providers. In our terms this means looking at catalogue-level standards mandated within UK Government and health services.

From an architectural perspective the SDRI Federation is an “overlay” on top of Web standards, notably HTTPS, XML and JSON. Hence we favour “Web facing” formats for metadata over internally-oriented standards.

#### Recommended standards

Our three key reference sites for metadata standards are:
 * Central Digital and Data Office: [Open standards for government data and technology](https://www.gov.uk/government/collections/open-standards-for-government-data-and-technology).
 * Department of Health and Social Care: [A guide to good practice for digital and data-driven health technologies](https://www.gov.uk/government/publications/code-of-conduct-for-data-driven-health-and-care-technology/initial-code-of-conduct-for-data-driven-health-and-care-technology#section-10) (particularly section 10).
 * Office for National Statistics: [Data Standards](https://www.ons.gov.uk/aboutus/transparencyandgovernance/datastrategy/datastandards)

There are a number of common themes across these sources. For interoperability and easier linkage we recommend that new, born-digital data aim for compatibility with the standards below—with the caveat that these may change or evolve over time.
 * General discovery metadata:
   - [W3C DCAT data catalogue standard](https://www.w3.org/TR/vocab-dcat-3/) and extended application profiles;
   - [schema.org](https://schema.org/) and its [extensions from DCAT](https://www.w3.org/wiki/WebSchemas/Datasets);
     o schema.org includes definitions for data catalogue and dataset drawn directly from DCAT;
     o the serialisation of schema.org markup into JSON-LD format provides a compact, machine-readable version ideal for data exchange and query results.
   - [CSVW](https://csvw.org/) for CSV files published on the Web;
   - [DCMI Dublin core metadata](https://www.dublincore.org/) where there is no current match in schema.org.
 * Place metadata:
   - [UPRN](https://www.geoplace.co.uk/addresses/uprn/) unique property refence number for addressable locations in the UK;
   - [ETRS89](http://etrs89.ensg.ign.fr/) European terrestrial reference system for locations in Europe;
   - [WGS84](http://earth-info.nga.mil/GandG/update/index.php?action=home) world geodetic system for global locations.
 * Date/time metadata:
   - [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601) for dates and times.
 * Health-related metadata:
   - [OMOP observational medical observations partnership standard](https://ohdsi.github.io/CommonDataModel/) for electronic health records and similar;
     o NB: while the DHSC guidelines cited above recommend NHS use of the HL7 FIHR standard  for data interchange, the HDRA White Paper of 2021 [53] considers both and leans towards OMOP as a more appropriate data model for research use.
   - [DICOM](https://www.dicomstandard.org/) image storage format for medical images.

----

| [< Federation metadata](5_2_Federation_Metadata.md) | - | [Data accessibility >](5_4_Data_Accessibility.md) |
| ---- | ---- | ---- |






