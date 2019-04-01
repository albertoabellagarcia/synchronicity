# SynchroniCity Data Models


[![License: MIT](https://img.shields.io/github/license/fiware/dataModels.svg)](https://opensource.org/licenses/MIT)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

This repository contains a set of OASC Shared Data Models for Smart City domains, adopted and developed in the SynchroniCity project. These data models are one of the "Interoperability Points" of the SynchroniCity framework and are a concrete extension of the OASC Minimal Interoperability Mechanisms (MIMs). In particular the repository contains: JSON Schemas and documentation on harmonized datamodels for smart cities, developed jointly with [OASC](http://oascities.org), and other domains. 
Such datasets are exposed through the [SynchroniCity Context Management API](https://synchronicityiot.docs.apiary.io/#reference/context-management-api) based on [FIWARE NGSI version 2](http://fiware.github.io/specifications/ngsiv2/stable) API (query)

The baseline of the OASC SynchroniCity data models is the [FIWARE Data Models catalogue](https://github.com/Fiware/dataModels/) developed by the FIWARE community. Also SynchroniCity project has analysed:

* The IoT Big Data Harmonised Data Models developed by GSMA. 
* The schema.org Data Models developed by the Browser and search engine communities
* Ontologies promoted by the European standards community, particularly [SAREF](http://ontology.tno.nl/saref/). 

Some modifications to the original data models have been performed in order to extend them to fit SynchroniCity cities requirements. Also, completelly new data models have been created to cover specific needs. The data model development is an going process, so please refer to this website for the last version of the SynchroniCity data models.

All the code in this repository is licensed under the MIT License. However each original data source may have a different license.
So before using harmonized data please check carefully each data license.

All the datamodels documented here are offered under a [Creative Commons by Attribution 4.0](https://creativecommons.org/licenses/by/4.0/) License.

## List of SynchroniCity Data Models
The following table shows the list of SynchroniCity data models. For each one is also defined the approval status:
* **Approved**: the data model has been officialy adopted by SynchroniCity and used by the Reference Zones (Cities) of the project
* **Under Discussion**: the data model is under discussion: SynchroniCity partners and external stakeholders can suggest changes or extensions. The data model could be used but cannot be considered stable.


| **Vertical** | **Data Model** | **Description** | **Original Source** | **Approval Status** |
| --- | --- | --- | --- | --- |
| Environment | [AirQualityObserved](https://github.com/Fiware/dataModels/blob/master/specs/Environment/AirQualityObserved/doc/spec.md) | It represents an observation of air quality conditions at a certain place and time | GSMA | Approved |
| Environment | [NoiseLevelObserved](https://github.com/Fiware/dataModels/blob/master/specs/Environment/NoiseLevelObserved/doc/spec.md) | It represents an observation of those parameters that estimate noise pressure levels at a certain place and time | FIWARE | Approved |
| PointOfInterest | [PointOfInterest](https://github.com/Fiware/dataModels/blob/master/specs/PointOfInterest/PointOfInterest/doc/spec.md) | A harmonised geographic description of a Point of Interest | GSMA updated by SynchroniCity | Approved |
| PointOfInterest | [Beach](https://github.com/Fiware/dataModels/blob/master/specs/PointOfInterest/Beach/doc/spec.md) | A harmonised geographic description of a beach | FIWARE | Approved |
| PointOfInterest | [Museum](https://github.com/Fiware/dataModels/blob/master/specs/PointOfInterest/Museum/doc/spec.md) | A harmonised geographic description of a museum | FIWARE | Approved |
| PointOfInterest | [Store](https://gitlab.com/synchronicity-iot/synchronicity-data-models/blob/master/PointOfInterest/Store/doc/spec.md) | A harmonised geographic description of a store | Developed by SynchroniCity | Approved |
| Transportation | [BikeHireDockingStation](https://github.com/Fiware/dataModels/blob/master/specs/Transportation/Bike/BikeHireDockingStation/doc/spec.md) | A bike hire docking station where subscribed users can hire and return a bike. | FIWARE | Approved |
| Transportation | [TrafficFlowObserved](https://github.com/Fiware/dataModels/blob/master/specs/Transportation/TrafficFlowObserved/doc/spec.md) | An observation of traffic flow conditions at a certain place and time. | FIWARE | Approved |
| Transportation | [EVChargingStation](https://gitlab.com/synchronicity-iot/synchronicity-data-models/blob/master/Transportation/EVChargingStation/doc/spec.md) | A public charging station supplying energy to electrical vehicles. | Developed by SynchroniCity | Approved |
| Transportation | [CrowdFlowObserved](https://gitlab.com/synchronicity-iot/synchronicity-data-models/blob/master/Transportation/CrowdFlowObserved/doc/spec.md) | An observation of people movement at a certain place and time. | Developed by Synchronicity | Approved |
| Transportation | [Vehicle](https://github.com/Fiware/dataModels/blob/master/specs/Transportation/Vehicle/Vehicle/doc/spec.md) | Real time tracking of the vehicles that are used for public transportation (buses, trains, etc.)  | FIWARE | Approved |
| Transportation | [CarSharingStation](https://gitlab.com/synchronicity-iot/synchronicity-data-models/blob/master/Transportation/CarSharingStation/doc/spec.md) | A site dedicated to car sharing with either direct access from a road or with suitable and clearly marked access points. | Developed by SynchroniCity | Approved |
| Transportation | [RestrictedTrafficArea](https://gitlab.com/synchronicity-iot/synchronicity-data-models/blob/master/Transportation/RestrictedTrafficArea/doc/spec.md) |An area of a city in which the traffic generated by cars or any other kind of vehicles is subjected to limitation. | Developed by SynchroniCity | Approved |
| Transportation | [Road](https://github.com/Fiware/dataModels/blob/master/specs/Transportation/Road/doc/spec.md) | A harmonised geographic and contextual description of a road. Roads are made up of one or more RoadSegment entities. | FIWARE | Approved |
| Transportation | [RoadSegment](https://github.com/Fiware/dataModels/blob/master/specs/Transportation/RoadSegment/doc/spec.md) | A harmonised geographic and contextual description of a road segment. A collection of road segments are used to describe a Road. | FIWARE | Approved |
| Weather | [WeatherObserved](https://github.com/Fiware/dataModels/blob/master/specs/Weather/WeatherObserved/doc/spec.md) | An observation of weather conditions at a certain place and time. | GSMA - Extended by FIWARE | Approved |
| Weather | [WeatherForecast](https://github.com/Fiware/dataModels/blob/master/specs/Weather/WeatherForecast/doc/spec.md) | Harmonised description of a Weather Forecast.   | GSMA - Extended by FIWARE | Approved |
| Urban Mobility | [GtfsAgency](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsAgency/doc/spec.md) | See https://developers.google.com/transit/gtfs/reference/#agencytxt | Developed by SynchroniCity| Approved |
| Urban Mobility | [GtfsStop](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsStop/doc/spec.md) | See https://developers.google.com/transit/gtfs/reference/#agencytxtSee https://developers.google.com/transit/gtfs/reference/#stopstxt It represents a GTFS stop which location_type shall be equal to 0. | Developed by SynchroniCity| Approved |
| Urban Mobility | [GtfsStation](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsStation/doc/spec.md) | See https://developers.google.com/transit/gtfs/reference/#stopstxt It is a GTFS stop which location_type is equal to 1. | Developed by SynchroniCity| Approved |
| Urban Mobility | [GtfsAccessPoint](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsAccessPoint/doc/spec.md) | See https://developers.google.com/transit/gtfs/reference/#stopstxt It is a GTFS stop which location_type is equal to 2. | Developed by SynchroniCity| Approved |
| Urban Mobility | [GtfsRoute](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsRoute/doc/spec.md) | See https://developers.google.com/transit/gtfs/reference/#routestxt | Developed by SynchroniCity| Approved |
| Urban Mobility | [GtfsTrip](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsTrip/doc/spec.md) | See https://developers.google.com/transit/gtfs/reference/#tripstxt | Developed by SynchroniCity| Approved |
| Urban Mobility | [GtfsShape](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsShape/doc/spec.md) | See https://developers.google.com/transit/gtfs/reference/#shapestxt It represents a GTFS shape. | Developed by SynchroniCity| Approved |
| Urban Mobility | [GtfsStopTime](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsStopTime/doc/spec.md) | See https://developers.google.com/transit/gtfs/reference/#stop_timestxt | Developed by SynchroniCity| Approved |
| Urban Mobility | [GtfsService](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsService/doc/spec.md) | It represents a transportation service which is available for one or more routes at certain dates. | Developed by SynchroniCity| Approved |
| Urban Mobility | [GtfsCalendarRule](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsCalendarRule/doc/spec.md) | See https://developers.google.com/transit/gtfs/reference/#calendartxt | Developed by SynchroniCity| Approved |
| Urban Mobility | [GtfsCalendarDateRule](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsCalendarDateRule/doc/spec.md) | See https://developers.google.com/transit/gtfs/reference/#calendar_datestxt | Developed by SynchroniCity| Approved |
| Urban Mobility | [GtfsFrequency](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsFrequency/doc/spec.md) | See https://developers.google.com/transit/gtfs/reference/#frequenciestxt | Developed by SynchroniCity| Approved |
| Urban Mobility | [GtfsTransferRule](https://github.com/FIWARE/dataModels/blob/master/specs/UrbanMobility/GtfsTransferRule/doc/spec.md) | See https://developers.google.com/transit/gtfs/reference/#transferstxt | Developed by SynchroniCity| Approved |
| Urban Mobility | [ArrivalEstimation](https://gitlab.com/synchronicity-iot/synchronicity-data-models/blob/master/UrbanMobility/ArrivalEstimation/doc/spec.md) | It captures the estimated arrival time of a public transport vehicle reaching a particular stop, whilst the vehicle is servicing a particular route. | Developed by SynchroniCity | Approved |
| Urban Mobility | [GtfsTransitFeedFile](https://gitlab.com/synchronicity-iot/synchronicity-data-models/blob/master/UrbanMobility/GtfsTransitFeedFile/doc/spec.md) | Provides the Location (URL) of the ZIP file containing a valid GTFS transit feed. | Developed by SynchroniCity | Approved |
| Urban Mobility | [PublicTransportRoute](https://gitlab.com/synchronicity-iot/synchronicity-data-models/blob/master/UrbanMobility/PublicTransportRoute/doc/spec.md) | Provides generic model for public transport route. | Developed by SynchroniCity | Approved |
| Urban Mobility | [PublicTransportStop](https://gitlab.com/synchronicity-iot/synchronicity-data-models/blob/master/UrbanMobility/PublicTransportStop/doc/spec.md) | Provides generic model for public transport stop. | Developed by SynchroniCity | Approved |
| Events | [Event](https://schema.org/Event) | Events happening in the city  | schema.org | Under discussion |
| Parking | [ParkingSpot](https://github.com/Fiware/dataModels/blob/master/specs/Parking/ParkingSpot/doc/spec.md) | An individual, usually monitored, parking spot/parking lot  | FIWARE | Approved |
| Parking | [OffStreetParking](https://github.com/Fiware/dataModels/blob/master/specs/Parking/OffStreetParking/doc/spec.md) | An offstreet parking site with explicit entries and exits  | FIWARE | Approved |
| Parking | [OnStreetParking](https://github.com/Fiware/dataModels/blob/master/specs/Parking/OnStreetParking/doc/spec.md) | An on street, free entry (but might be metered) parking zone which contains at least one or more adjacent parking spots  | FIWARE | Approved |
| Parks &amp; Gardens | [Garden](https://github.com/Fiware/dataModels/blob/master/specs/ParksAndGardens/Garden/doc/spec.md) | A distinguishable planned space, usually outdoors, set aside for the display, cultivation, and enjoyment of plants and other forms of nature.  | FIWARE | Approved |
| Parks &amp; Gardens | [GreenspaceRecord](https://github.com/Fiware/dataModels/blob/master/specs/ParksAndGardens/GreenspaceRecord/doc/spec.md) | Harmonised description of the conditions recorded on a particular area or point inside a greenspace (flower bed, garden, etc.)  | FIWARE | Approved |
| Waste Management | [WasteContainer](https://github.com/Fiware/dataModels/blob/master/specs/WasteManagement/WasteContainer/doc/spec.md) | Waste Containers  | FIWARE | Approved |
| Waste Management | [WasteContainerModel](https://github.com/Fiware/dataModels/blob/master/specs/WasteManagement/WasteContainerModel/doc/spec.md) | Static properties of a waste container (big belly)  | FIWARE | Approved |
| Device | [Device](https://github.com/Fiware/dataModels/blob/master/specs/Device/Device/doc/spec.md) | An apparatus (hardware + software + firmware) intended to accomplish a particular task (sensing the environment, actuating, etc.).  | FIWARE | Approved |


## JSON Schemas

We intend to provide a [JSON Schema](http://json-schema.org/) for every harmonized data model. In the future all the
documentation could be generated from a JSON Schema, as it is part of our roadmap. The different JSON Schemas usually
depend on common JSON Schema definitions found at the root directory of this repository. 

There are different online JSON Schema Validators, for instance: [http://jsonschemalint.com/](http://jsonschemalint.com/).
For the development of these schemas the [AJV JSON Schema Validator](https://github.com/epoberezkin/ajv) is being used. For
using it just install it through npm: 

```
    npm install ajv
    npm install ajv-cli
```

A `validate.sh` script is provided for convenience.

**Note**: JSON Schemas only capture the NGSI simplified representation, this means that to test the JSON schema examples with a [FIWARE NGSI version 2](http://fiware.github.io/specifications/ngsiv2/stable) API implementation, you need to use the `keyValues` mode (`options=keyValues`).

# Data models guidelines

SynchroniCity provides a set of [guidelines](./guidelines.md) for defining new data models. Further information can be found in [SynchroniCity Deliverable D2.2](https://synchronicity-iot.eu/wp-content/uploads/2018/05/synchronicity_d2_2_guidelines_for_the_definition_of_oasc_shared_data_models.pdf)


## Entity ID definition guidelines
Despite the Entity ID within any existing Context Entity is originally free text, [NGSI API](http://fiware.github.io/specifications/ngsiv2/stable) provides several features based on this parameter to assist NGSI operations. The following recommendations, which are not mandatory to be SynchroniCity compliant, represents a set of good practices to define entity IDs that improves the context queries, subscritions and discovery actions.

These guidelines are based on the incoming [NGSI-LD](https://www.etsi.org/images/files/ETSIWhitePapers/etsi_wp31_NGSI_API.pdf) standard and are used by several SynchoniCity Reference Zones' instances. According to them, the Entity ID would be a text string composed by several fields separated by colons.
- Three first fields represent the NGSI-LD standard and identifies the entity as a NGSI-LD compliant entity:

 - **`urn`** is always set to "urn" and identies the entity ID as an urn.
 - **`ngsi-ld`** represents an ngsi-ld entity when set to "ngsi-ld".
 - **`entity-Type`** matches the **type** attribute of the entity.


- Next optional fields are proposed by SynchroniCity and are arranged to organise the entities according their deployment and functionaly:
  - **site**  can represent a RZ, City or area that includes several different IoT deployments, services or apps (e.g., Porto, Milano, Santander, Aarhus, Andorra ... ).
  - **service** represents a smart city service/application domain, for example parking, waste management, environmental etc.
  - **group** can be used for grouping assets under the same service and/or provider (so it can be used to identify different IoT providers). It is responsibility of OS sites to maintain proper group keys.
  - **entityName** The Entity​ /​ Device identifier which should be unique at the corresponding **site**, **service** and **group**.

***Entities’ ID definition***

`urn` | `ngsi-ld` | `entity-Type` | **site** | **service** | **group** | **entityName** |
---:|:---:|:---:|:---:|:---:|:---:|:---:|
*urn* | *ngsi-ld* | *OnStreetParking*| *santander* |*parking* | *onStreet* | *StaLuciaEast* 
*urn* | *ngsi-ld* | *ParkingSpot*| *santander* |*parking* | *parkingSpot* | *3601* 
*urn* | *ngsi-ld* | *TrafficFlowObserved*| *santander* |*traffic* | *TrafficFlowObserved* | *1001* 

***Entity IDs examples***

*`"urn:ngsi-ld:OnStreetParking:santander:parking:onStreet:StaLuciaEast"`*

*`"urn:ngsi-ld:ParkingSpot:santander:parking:parkingSpot:3601"`*

*`"urn:ngsi-ld:TrafficFlowObserved:santander:traffic:TrafficFlowObserved:1001"`*


## How to contribute

Contributions should come in the form of pull requests. 

New data models should be added under a folder structured as follows:
  - `NewModel/`
    - `doc/`
      - `spec.md`: A data model description based on the [data model template](datamodel_template.md), e.g. [spec.md of WeatherObserved](/Weather/WeatherObserved/doc/spec.md).
    - `README.md`: A summary file (as an extract from the spec file), e.g. [README.md of WeatherObserved](/Weather/WeatherObserved/README.md)
    - `schema.json`: The JSON Schema definition, e.g. [schema.json of WeatherObserved](/Weather/WeatherObserved/schema.json)
    - `example.json`: One or more JSON example file, e.g. [example.json of WeatherObserved](specs/Weather/WeatherObserved/example.json)

The name of the folder should match the entity type used in the JSON Schema (e.g. `NewModel`). For data models including more entities, a hierarchical folder should be used. The father folder can include common JSON schemas shared among the entities. e.g.:

  - `NewModel/`
    - `doc/`
      - `spec.md`
    - `README.md`
    - `newmodel-schema.json`: the common schema for the different entities.
    - `NewModelEntityOne/`
      - `doc/`
        - `spec.md`
      - `README.md`
      - `schema.json`
      - `example.json`
    - `NewModelEntityTwo/`
      - `doc/`
        - `spec.md`
      - `README.md`
      - `schema.json`
      - `example.json`

## Validator
SynchroniCity developed a tool to validate the data models. Code and documentation can be found here: https://gitlab.com/synchronicity-iot/rz-instance-validator

## Related Projects 

See:
* [FIWARE Data Models](https://www.fiware.org/developers/data-models/)
* [https://github.com/GSMADeveloper/HarmonisedEntityDefinitions](https://github.com/GSMADeveloper/HarmonisedEntityDefinitions)
* [https://github.com/GSMADeveloper/HarmonisedEntityReferences](https://github.com/GSMADeveloper/HarmonisedEntityReferences)
* [schema.org](https://schema.org)

