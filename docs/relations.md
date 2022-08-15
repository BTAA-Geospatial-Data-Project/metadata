# Relations and the Collection Model

This document describes the content organization model for the GeoBlacklight application and how to relate records in the BTAA Geoportal.

## Content Organization Model


GeoBlacklight organizes records with a network model rather than with a hierarchical model. It is a flat system whereby every database entry is a "Layer" and uses the same metadata fields. Unlike many digital library applications, it does not have different types of records for entities such as "communities," "collections," or "groups." As a result, it does not present a breadcrumb navigation structure, and all records appear in the same catalog directory with the URL of https:geo.btaa.org/catalog/`ID`.

Instead of a hierarchy, GeoBlacklight relates records via metadata fields. These fields include `Member Of`, `Is Part Of`, `Is Version Of`, `Source`, and a general `Relation`. This flexibility allows records to be presented in several different ways. For example, records can have multiple parent/child/grandchild/sibling relationships. In addition, they can be nested (i.e., a collection can belong to another collection). They can also connect data layers about similar topics or represent different years in a series.

The following diagram illustrates how the BTAA Geoportal organizes records. The connecting arrow lines indicate the name of the relationship. The labels reflect each record's [Resource Class](https://opengeometadata.org/docs/ogm-aardvark/resource-class) (**Collections**, **Websites**, **Datasets**, **Maps**, **Web services**).

![Chart](./images/contentOrganization.png)

## Collections
The BTAA Geoportal interprets the Resource Class, **Collections**, as top-level, custom groupings. These reflect our curation activities and priorities.

Other records are linked to Collections using the `Member Of` field. The ID of the parent record is added to the child record only. View all of the current **Collections** in the geoportal at this link: 
[https://geo.btaa.org/?f%5Bgbl_resourceClass_sm%5D%5B%5D=Collections](https://geo.btaa.org/?f%5Bgbl_resourceClass_sm%5D%5B%5D=Collections)

----------------
## Websites
The BTAA Geoportal uses the Resource Class, **Websites**, to create parent records for data portals, digital libraries, dashboards, and interactive maps. These often start off as standalone records.
Once the items in a website have been indexed, they will have child records.

Individual **Datasets**, **Maps**, or **Web service**s  are linked to the **Website** they came from using the `Is Part Of` field. The ID of the parent record is added to the child record only.

View all of the current **Websites** in the geoportal at this link: [https://geo.btaa.org/?f%5Bgbl_resourceClass_sm%5D%5B%5D=Websites](https://geo.btaa.org/?f%5Bgbl_resourceClass_sm%5D%5B%5D=Websites)

-----------------
## Datasets, Maps, and Web services
The items in this Resource Class represent individual data layers, scanned map files, and/or geospatial web services. (Some items may have multiple Resource Classes attached to the same record.)

This item class is likely to have the most relationships specified in the metadata. A typical **Datasets** record might have the following: 

1. `Member Of` a **Collections** record
2. `Is Part Of` a **Websites** record
3. If the data was digitized from a paper map in the geoportal, it can be linked to the **Maps** record via the `Source` relation
4. a general `Relation` to a research guide or similar dataset


------------------
## Multipart Items
Many items in the geoportal are multipart. There may be individual pages from an atlas, sublayers from a larger project, or datasets broken up into more than one download. In these cases, the `Is Part Of` field is used. 

As a result, these items may have multiple `Is Part Of` relationships- (1) the parent for the multipart items and (2) the original website.






