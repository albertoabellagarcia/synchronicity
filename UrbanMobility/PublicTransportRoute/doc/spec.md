# PublicTransportRoute

## Description

Generic model for public transport route. It adopts some GTFS definitions, but it does not need to be linked to additional GTFS data. A route is a journey, offered by one public transport service, that goes through a set of stops.

## Data Model

+ `id`: Entity Id
  + It shall be `urn:ngsi-ld:PublicTransportRoute:<identifier>`.

+ `type`: Entity Type
  + It shall be equal to `PublicTransportRoute`.

+ `source` : A sequence of characters giving the source of the entity data.
  + Attribute type: [Text](https://schema.org/Text) or [URL](https://schema.org/URL)
  + Optional.

+ `dataProvider` : Specifies the URL to information about the provider of this
  information
  + Attribute type: URL
  + Optional.

+ `dateCreated` : Entity's creation timestamp.
  + Attribute type: [DateTime](https://schema.org/DateTime)
  + Read-Only. Automatically generated.

+ `dateModified` : Last update timestamp of this Entity.
  + Attribute type: [DateTime](https://schema.org/DateTime)
  + Read-Only. Automatically generated.  

+ `routeCode`: ID or code of the route (e.g. ‘5200104000’’)
  + Attribute type: [Text](https://schema.org/Text)
  + Optional.

+ `shortRouteCode`: Shorter form of the ID/code of the route (e.g. ‘5200104000’’)
  + Attribute type: [Text](https://schema.org/Text)
  + Optional.

+ `name`: name of the route
  + Attribute type: [Text](https://schema.org/Text)
  + Mandatory.

+ `transportationType`: Types of public transport using this stop.
  + Attribute type: [Number](https://schema.org/Number)
  + Allowed values: {0, 1, 2, 3, 4, 5, 6, 7} as per the [GTFS](https://developers.google.com/transit/gtfs/reference/#routestxt)
  + Mandatory.

+ `routeColor`: Color assigned to route in hexadecimal.
  + Attribute type: [Color](https://schema.org/color)
  + Optional. 

+ `routeTextColor`: Color assigned to route in text.
  + Attribute type: [Color](https://schema.org/color)
  + Optional. 

+ `routeSegments`: Segments of this route defined by their name and stops.
  + Attribute type: Array of structured values. Each segment contains a name and an array of [PublicTransportStop](https://gitlab.com/synchronicity-iot/synchronicity-data-models/blob/master/UrbanMobility/PublicTransportStop/doc/spec.md).
  + Optional.

+ `schedule`: Working hours of this route.
  + Normative References: [http://schema.org/openingHoursSpecification](https://schema.org/OpeningHoursSpecification)
  + Attribute type: List of OpeningHoursSpecification
  + Optional.

## Examples

### Normalized Example

Normalized NGSI response 

```json
{
  "id": "urn:ngsi-ld:PublicTransportRoute:santander:transport:busLine:N3",
  "type": "PublicTransportRoute",
  "routeCode": {
    "type": "Text",
    "value": "5200103000"
  },
  "shortRouteCode": {
    "type": "Text",
    "value": "N3"
  },
  "name": {
    "type": "Text",
    "value": "PEÑACASTILLO-PLAZA DE ITALIA"
  },
  "transportationType": {
    "type": "Number",
    "value": 3
  },
  "routeSegments": 
  {
    "type": "StructuredValue",
    "value": [
      {
        "segmentName": "PEÑACASTILLO-PLAZA DE ITALIA:1",
        "refPublicTransportStops": [
          "urn:ngsi-ld:PublicTransportStop:santander:transport:busStop:311",
          "urn:ngsi-ld:PublicTransportStop:santander:transport:busStop:129"
        ]
      }, 
      {
        "segmentName": "PEÑACASTILLO-PLAZA DE ITALIA:2",
        "refPublicTransportStops": [
          "urn:ngsi-ld:PublicTransportStop:santander:transport:busStop:130",
          "urn:ngsi-ld:PublicTransportStop:santander:transport:busStop:131"
        ]
      }
    ]
  },
  "schedule":{
    "type": "StructuredValue",
    "value": [
      {
        "validFrom": "2018-01-24",
        "validThrough": "2018-05-25",
        "opens": "09:00",
        "closes": "23:00"
      },
      {
        "dayOfWeek": "Sunday",
        "opens":  "09:00",
        "closes": "14:00"      
      }
    ]
  }  
}
```

### key-value pairs Example

Sample uses simplified representation for data consumers `?options=keyValues`

```json
{
  "id": "urn:ngsi-ld:PublicTransportRoute:santander:transport:busLine:N3",
  "type": "PublicTransportRoute",
  "routeCode": "5200103000",
  "shortRouteCode": "N3",
  "name": "PEÑACASTILLO-PLAZA DE ITALIA ",
  "transportationType": 3,
  "routeSegments": [
    {
      "segmentName": "PEÑACASTILLO-PLAZA DE ITALIA:1",
      "refPublicTransportStops":  [
        "urn:ngsi-ld:PublicTransportStop:santander:transport:busStop:311",
        "urn:ngsi-ld:PublicTransportStop:santander:transport:busStop:129"
      ]
    },
    {
      "segmentName": "PEÑACASTILLO-PLAZA DE ITALIA:2",
      "refPublicTransportStops": [
        "urn:ngsi-ld:PublicTransportStop:santander:transport:busStop:130",
        "urn:ngsi-ld:PublicTransportStop:santander:transport:busStop:131"
      ]
    }
  ],
  "schedule": [
    {
      "validFrom": "2018-01-24",
      "validThrough": "2018-05-25",
      "opens": "09:00",
      "closes": "23:00"
    },
    {
      "dayOfWeek": "Sunday",
      "opens":  "09:00",
      "closes": "14:00"      
    }
  ]  
}
```

## Open issues

  + ``routeSegments`` attribute could be defined as an external entity, so that they can be re-used by several routes, even if they are of different `transportationType`. This will be decided upon feedback from cities and different requirements of different transportation urban services. 
  