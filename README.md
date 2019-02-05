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
| PointOfInterest | [Beach](https://github.com/Fiware/dataModels/blob/master/specs/PointOfInterest/Beach/doc/spec.md) | A harmonised geographic description of a beach | FIWARE | Under discussion |
| PointOfInterest | [Museum](https://github.com/Fiware/dataModels/blob/master/specs/PointOfInterest/Museum/doc/spec.md) | A harmonised geographic description of a museum | FIWARE | Under discussion |
| Transportation | [BikeHireDockingStation](https://github.com/Fiware/dataModels/blob/master/specs/Transportation/Bike/BikeHireDockingStation/doc/spec.md) | A bike hire docking station where subscribed users can hire and return a bike. | FIWARE | Approved |
| Transportation | [TrafficFlowObserved](https://github.com/Fiware/dataModels/blob/master/specs/Transportation/TrafficFlowObserved/doc/spec.md) | An observation of traffic flow conditions at a certain place and time. | FIWARE | Approved |
| Transportation | [EVChargingStation](./Transportation/EVChargingStation/doc/spec.md) | A public charging station supplying energy to electrical vehicles. | Developed by SynchroniCity | Under discussion |
| Transportation | [CrowdFlowObserved](./Transportation/CrowdFlowObserved/doc/spec.md) | An observation of people movement at a certain place and time. | Developed by Synchronicity | Under discussion |
| Transportation | [Vehicle](https://github.com/Fiware/dataModels/blob/master/specs/Transportation/Vehicle/Vehicle/doc/spec.md) | Real time tracking of the vehicles that are used for public transportation (buses, trains, etc.)  | FIWARE | Approved |
| Transportation | SAN Bus Datamodels | Static information about BUS | Developed by SynchroniCity | Under Discussion |
| Transportation | Car Sharing Stations | Information about car sharing stations | Developed by SynchroniCity | Under discussion |
| Transportation | Restricted Areas | Description of restricted areas | Developed by SynchroniCity | Under discussion |
| Weather | [WeatherObserved](https://github.com/Fiware/dataModels/blob/master/specs/Weather/WeatherObserved/doc/spec.md) | An observation of weather conditions at a certain place and time. | GSMA - Extended by FIWARE | Approved |
| Weather | [WeatherForecast](https://github.com/Fiware/dataModels/blob/master/specs/Weather/WeatherForecast/doc/spec.md) | Harmonised description of a Weather Forecast.   | GSMA - Extended by FIWARE | Approved |
| Urban Mobility | [Urban Mobility](./UrbanMobility)  | The General Transit Feed Specification (GTFS) defines a common format for public transportation schedules and associated geographic information. | GTFS - NGSI mapping developed by SynchroniCity | Under discussion |
| Urban Mobility | [ArrivalEstimation](./UrbanMobility/ArrivalEstimation/doc/spec.md) | It captures the estimated arrival time of a public transport vehicle reaching a particular stop, whilst the vehicle is servicing a particular route. | Developed by SynchroniCity | Under discussion |
| Urban Mobility | People counting |   | Developed by SynchroniCity | Under discussion |
| Urban Mobility | Cycle counting |   | Developed by SynchroniCity | Under discussion |
| Events | [Event](https://schema.org/Event) | Events happening in the city  | schema.org | Under discussion |
| Parking | [ParkingSpot](https://github.com/Fiware/dataModels/blob/master/specs/Parking/ParkingSpot/doc/spec.md) | An individual, usually monitored, parking spot/parking lot  | FIWARE | Approved |
| Parking | [OffStreetParking](https://github.com/Fiware/dataModels/blob/master/specs/Parking/OffStreetParking/doc/spec.md) | An offstreet parking site with explicit entries and exits  | FIWARE | Approved |
| Parking | [OnStreetParking](https://github.com/Fiware/dataModels/blob/master/specs/Parking/OnStreetParking/doc/spec.md) | An on street, free entry (but might be metered) parking zone which contains at least one or more adjacent parking spots  | FIWARE | Approved |
| Parks &amp; Gardens | [GreenspaceRecord](https://github.com/Fiware/dataModels/blob/master/specs/ParksAndGardens/GreenspaceRecord/doc/spec.md) | Harmonised description of the conditions recorded on a particular area or point inside a greenspace (flower bed, garden, etc.)  | FIWARE | Approved |
| Waste Management | [WasteContainer](https://github.com/Fiware/dataModels/blob/master/specs/WasteManagement/WasteContainer/doc/spec.md) | Waste Containers  | FIWARE | Approved |
| Waste Management | [WasteContainerModel](https://github.com/Fiware/dataModels/blob/master/specs/WasteManagement/WasteContainerModel/doc/spec.md) | Static properties of a waste container (big belly)  | FIWARE | Approved |


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

