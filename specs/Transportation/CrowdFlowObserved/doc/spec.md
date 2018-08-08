# Crowd Flow Observed

## Description

An observation related to the movement of people at a certain place and time.

## Data Model

+ `id`: Entity id. 
    + It shall be `urn:ngsi-ld:CrowdFlowObserved:<identifier>` being `identifier` a unique identifier. 

+ `type`: Entity type. 
    + It shall be equal to `CrowdFlowObserved`.
    
+ `dateCreated` : Entity's creation timestamp. (`createdAt` in NGSI-LD)
    + Attribute type: [DateTime](https://schema.org/DateTime)
    + Read-Only. Automatically generated. 
 
+ `dateModified` : Last update timestamp of this Entity. (`modifiedAt` in NGSI-LD)
    + Attribute type: [DateTime](https://schema.org/DateTime)
    + Read-Only. Automatically generated.
  
+ `source` : A sequence of characters giving the original source of the Entity data as a URL.
    + Attribute type: [URL](https://schema.org/URL)
    + Mandatory

+ `location` : Location of this crowd flow observation represented by a GeoJSON geometry. 
    + Attribute type: `geo:json`. (`GeoProperty`)
    + Normative References: [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
    + Mandatory if `refRoadSegment` is not present.

+ `address` : Civic address of this crowd flow observation.
    + Normative References: [https://schema.org/address](https://schema.org/address)
    + Optional
    
+ `refRoadSegment` : Concerned road segment on which the observation has been mede.
    + Attribute type: Relationship. Reference to an entity of type [RoadSegment](../../RoadSegment/doc/spec.md).
    + Mandatory if `location` is not present. 

+ `dateObserved` : The date and time of this observation in ISO8601 UTC format.
It can be represented by an specific time instant or by an ISO8601 interval. As a workaround for
the lack of support of Orion Context Broker for datetime intervals, it can be used two separate attributes: `dateObservedFrom`, `dateObservedTo`. 
    + Attribute type: [DateTime](https://schema.org/DateTime) or an ISO8601 interval represented as [Text](https://schema.org/Text). 
    + Mandatory
        
+ `dateObservedFrom` : Observation period start date and time. See `dateObserved`. 
    + Attribute type: TemporalProperty. [DateTime](https://schema.org/DateTime). 
    + Optional
    
+ `dateObservedTo` : Observation period end date and time. See `dateObserved`. 
    + Attribute type: TemporalProperty. [DateTime](https://schema.org/DateTime). 
    + Optional
    
+ `name` : Name given to this observation.
    + Normative References: [https://schema.org/name](https://schema.org/name)
    + Optional

+ `description` : Description of this observation.
    + Normative References: [https://schema.org/description](https://schema.org/description)
    + Optional
    
+ `peopleCount` : Total number of people detected during this observation period.
    + Attribute type: [Number](https://schema.org/Number). Positive integer. 
    + Optional

+ `occupancy` : Fraction of the observation time where a person has been occupying the observed lane.
    + Attribute type: Property. [Number](https://schema.org/Number) between 0 and 1.
    + Optional

+ `averageCrowdSpeed` : Average speed of the crowd transiting during the observation period.
    + Attribute type: Property. [Number](https://schema.org/Number)
    + Default unit: Kilometer per hour (Km/h).
    + Optional
    
+ `congested` : Flags whether there was a crowd congestion during the observation period in the referred lane. The absence of this attribute means no crowd congestion.  
    + Attribute type: Property. [Boolean](https://schema.org/Boolean)
    + Optional
    
+ `averageHeadwayTime` : Average headway time. Headway time is the time elapsed between two consecutive persons.
    + Attribute type: Property. [Number](https://schema.org/Number)
    + Default unit: second (s)
    + Optional
    
+ `direction` : Usual direction of travel in the lane referred by this observation with respect to the city center.
    + Attribute type: Property. [Text](https://schema.org/Text)
    + Allowed values: (`inbound`, `outbound`). 
    + Optional


### Example

```json
{
  "id": "urn:ngsi-ld:CrowdFlowObserved:Manchester_1",
  "type": "CrowdFlowObserved",
  "dateObservedFrom": "2018-08-07T11:10:00",
  "dateObservedTo": "2018-08-07T11:15:00",
  "peopleCount": 100,
  "averageHeadwayTime": 5,
  "congested": false,
  "direction": "inbound"
}
```

### Open issues
