# PublicTransportStop

## Description

Generic model for a public transport stop. It adopts some GTFS definitions, but it does not need to be linked to additional GTFS data.

## Data Model

+ `id`: Entity Id
  + It shall be `urn:ngsi-ld:PublicTransportStop:<identifier>`

+ `type`: Entity Type
  + It shall be equal to `PublicTransportStop`

+ `source` : A sequence of characters giving the source of the entity data.
  + Attribute type: Text or URL
  + Optional

+ `dataProvider` : Specifies the URL to information about the provider of this 
  information
  + Attribute type: URL
  + Optional

+ `dateCreated` : Entity's creation timestamp.
  + Attribute type: [DateTime](https://schema.org/DateTime)
  + Read-Only. Automatically generated.

+ `dateModified` : Last update timestamp of this Entity.
  + Attribute type: [DateTime](https://schema.org/DateTime)
  + Read-Only. Automatically generated.  

+ `address` : Address of the stop.
  + Normative References: [https://schema.org/address](https://schema.org/address)
  + Mandatory if `location` is not present.

+ `location`: Location of this stop represented by a GeoJSON geometry,
    usually a `Point` or a `Polygon`.
  + Attribute type: `geo:json`.
  + Normative References: [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
  + Mandatory if `address` is not defined.  

+ `stopCode`: Identifier/code of the public transport stop.
  + Attribute type: [Text](https://schema.org/Text).
  + Optional

+ `shortStopCode`: Shorter form of the identifier/code of the public transport stop.
  + Attribute type: [Text](https://schema.org/Text).
  + Optional.

+ `name`: The name of the public transport stop.
  + Attribute type: [Text](https://schema.org/Text).
  + Mandatory.

+ `wheelchairAccessible`: Indicate whether or not this stop is accessible for wheelchairs.
  + Attribute type: [Number](https://schema.org/Number)
  + Allowed values: {0, 1, 2} as per the [GTFS](https://developers.google.com/transit/gtfs/reference/#stopstxt)
  + Optional

+ `transportationType`: Types of public transport using this stop.
  + Attribute type: Array of [Number](https://schema.org/Number)
  + Allowed values: {0, 1, 2, 3, 4, 5, 6, 7} as per the [GTFS](https://developers.google.com/transit/gtfs/reference/#routestxt)
  + Mandatory.

+ `refPublicTransportRoute`: Public transport routes using this stop.
  + Attribute type: Array of [PublicTransportRoute](./PublicTransportRoute/doc/spec.md)
  + Optional

+ `peopleCount`: Estimation of people waiting in the stop.
  + Attribute type: [Number](https://schema.org/Number). Integer, positive.
  + Optional.

+ `refPeopleCountDevice`: Reference to the [Device](https://github.com/Fiware/dataModels/blob/master/specs/Device/Device/doc/spec.md) providing people count estimate.
  + Attribute type: Reference to an entity of type [Device](https://github.com/Fiware/dataModels/blob/master/specs/Device/Device/doc/spec.md).
  + Optional.  

+ `openingHoursSpecification`: Opening hours of this stop.
  + Normative References: [http://schema.org/openingHoursSpecification](https://schema.org/OpeningHoursSpecification)
  + Attribute type: List of OpeningHoursSpecification
  + Optional.  

## Examples

### Normalized Example

Normalized NGSI response 

```json
{
  "id": "urn:ngsi-ld:PublicTransportStop:santander:busStop:463",
  "type": "PublicTransportStop",
  "dateModified": {
    "type": "ISO8601",
    "value": "2018-09-25T08:32:26.00Z"
  },
  "address": {
    "type": "StructuredValue",
    "value": {
      "streetAddress": "C/ La Pereda 14",
      "addressLocality": "Santander",
      "addressRegion": "Cantabria",
      "addressCountry": "Spain"
    }
  },
  "location": {
    "type": "geo:json",
    "value": {
      "type": "Point",
      "coordinates": [-3.804648385,43.478053126]
    }
  },  
  "name": {
    "type": "Text",
    "value": "La Pereda 14"
  },
  "shortStopCode": {
    "type": "Text",
    "value": "463"
  },
  "transportationType": {
    "type": "StructuredValue",
    "value": [3]
  }
}
```

### key-value pairs Example

Sample uses simplified representation for data consumers `?options=keyValues`


```json
{
  "id": "urn:ngsi-ld:PublicTransportStop:santander:busStop:463",
  "type": "PublicTransportStop",
  "dateModified": "2018-09-25T08:32:26.00Z",
  "address": {
      "streetAddress": "C/ La Pereda 14",
      "addressLocality": "Santander",
      "addressRegion": "Cantabria",
      "addressCountry": "Spain"
  },
  "location": {
    "type": "Point",
    "coordinates": [-3.804648385, 43.478053126]
  },
  "name": "La Pereda 14",
  "shortStopCode": "463",
  "transportationType": [3]
}
```

## Open issues
