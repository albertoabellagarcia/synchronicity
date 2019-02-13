# Urban Mobility Data Models

# Introduction

The General Transit Feed Specification (GTFS), also known as GTFS static or static transit,
defines a common format for public transportation schedules and associated geographic information.
GTFS "feeds" let public transit agencies publish their transit data and developers write applications that consume
that data in an interoperable way.

The data models present in this folder represent generic entities involved in urban mobility.

The main entities identified are:

+ [ArrivalEstimation](../ArrivalEstimation/doc/spec.md). Generic arrival estimation of a public transport vehicle to a stop.
+ [GtfsTransitFeedFile](../GtfsTransitFeedFile/doc/spec.md). Pointer to an external GTFS feed file.

In addition, those projects that require explicit NGSI representation of linked GTFS Entities can make use of the following specifications:

+ [GtfsAgency](https://github.com/Fiware/dataModels/tree/master/specs/UrbanMobility/GtfsAgency/doc/spec.md)
+ [GtfsStop](https://github.com/Fiware/dataModels/tree/master/specs/UrbanMobility/GtfsStop/doc/spec.md)
+ [GtfsStation](https://github.com/Fiware/dataModels/tree/master/specs/UrbanMobility/GtfsStation/doc/spec.md)
+ [GtfsAccessPoint](https://github.com/Fiware/dataModels/tree/master/specs/UrbanMobility/GtfsAccessPoint/doc/spec.md)
+ [GtfsRoute](https://github.com/Fiware/dataModels/tree/master/specs/UrbanMobility/GtfsRoute/doc/spec.md)
+ [GtfsTrip](https://github.com/Fiware/dataModels/tree/master/specs/UrbanMobility/GtfsTrip/doc/spec.md)
+ [GtfsStopTime](https://github.com/Fiware/dataModels/tree/master/specs/UrbanMobility/GtfsStopTime/doc/spec.md)
+ [GtfsService](https://github.com/Fiware/dataModels/tree/master/specs/UrbanMobility/GtfsService/doc/spec.md)
+ [GtfsCalendarRule](https://github.com/Fiware/dataModels/tree/master/specs/UrbanMobility/GtfsCalendarRule/doc/spec.md)
+ [GtfsCalendarDateRule](https://github.com/Fiware/dataModels/tree/master/specs/UrbanMobility/GtfsCalendarDateRule/doc/spec.md)
+ [GtfsFrequency](https://github.com/Fiware/dataModels/tree/master/specs/UrbanMobility/GtfsFrequency/doc/spec.md)
+ [GtfsTransferRule](https://github.com/Fiware/dataModels/tree/master/specs/UrbanMobility/GtfsTransferRule/doc/spec.md)
