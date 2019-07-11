# Waste Measurement

## Description

A waste measurement.

## Data Model

A JSON Schema corresponding to this data model can be found
[here](http://fiware.github.io/dataModels/specs/WasteManagement/WasteMeasurement/schema.json).

-   `id` : Unique identifier.

-   `type` : Entity type. It must be equal to `WasteMeasurement`.

-   `source` : A sequence of characters giving the source of the entity data.

    -   Attribute type: Text or URL
    -   Optional

-   `areaServed` : Higher level area to which this waste measurement belongs to. It
    can be used to group waste measurements per district, neighbourhood, etc.
    -   Attribute type: [Text](https://schema.org/Text)
    -   Normative References:
        [https://schema.org/areaServed](https://schema.org/areaServed)
    -   Optional

-   `wasteWeight` : Weight of the waste for the defined neighbourhood (areaServed), 
	expressed in tonnes. 
    -   Attribute type: [Number](http://schema.org/Number)
    -   Attribute metadata:
        -   `timestamp`: Timestamp when the last update of the attribute
            happened.
            -   Type: [DateTime](http://schema.org/DateTime)
        -   `TimeInstant` :
            [Timestamp](https://github.com/telefonicaid/iotagent-node-lib#TimeInstant)
            saved by FIWARE's IoT Agents. Note: This attribute has not been
            harmonized to keep backwards compatibility with current FIWARE
            reference implementations.
            -   Type: [DateTime](https://schema.org/DateTime). There can be
                production environmments where the attribute type is equal to
                the `ISO8601` string. If so, it must be considered as a synonym
                of `DateTime`.
    -   Allowed values: Interval \[0,1\].
	-   Default Unit: Tonnes.
	-   See also: [https://schema.org/weight](https://schema.org/weight)
    -   Optional

-   `recycleWeight` : Weight of the recycled waste for the defined neighbourhood (areaServed), 
	expressed in tonnes. 
    -   Attribute type: [Number](http://schema.org/Number)
    -   Attribute metadata:
        -   `timestamp`: Timestamp when the last update of the attribute
            happened.
            -   Type: [DateTime](http://schema.org/DateTime)
        -   `TimeInstant` :
            [Timestamp](https://github.com/telefonicaid/iotagent-node-lib#TimeInstant)
            saved by FIWARE's IoT Agents. Note: This attribute has not been
            harmonized to keep backwards compatibility with current FIWARE
            reference implementations.
            -   Type: [DateTime](https://schema.org/DateTime). There can be
                production environmments where the attribute type is equal to
                the `ISO8601` string. If so, it must be considered as a synonym
                of `DateTime`.
    -   Allowed values: Interval \[0,1\].
	-   Default Unit: Tonnes.
	-   See also: [https://schema.org/weight](https://schema.org/weight)
    -   Optional

-   `compostWeight` : Weight of the compost waste for the defined neighbourhood (areaServed), 
	expressed in tonnes. 
    -   Attribute type: [Number](http://schema.org/Number)
    -   Attribute metadata:
        -   `timestamp`: Timestamp when the last update of the attribute
            happened.
            -   Type: [DateTime](http://schema.org/DateTime)
        -   `TimeInstant` :
            [Timestamp](https://github.com/telefonicaid/iotagent-node-lib#TimeInstant)
            saved by FIWARE's IoT Agents. Note: This attribute has not been
            harmonized to keep backwards compatibility with current FIWARE
            reference implementations.
            -   Type: [DateTime](https://schema.org/DateTime). There can be
                production environmments where the attribute type is equal to
                the `ISO8601` string. If so, it must be considered as a synonym
                of `DateTime`.
    -   Allowed values: Interval \[0,1\].
	-   Default Unit: Tonnes.
	-   See also: [https://schema.org/weight](https://schema.org/weight)
    -   Optional

-   `dateMeasurement` : Date for which the measurement corresponds.

    -   Attribute Type: [Date](http://schema.org/Date)
    -   Optional

**Note**: JSON Schemas are intended to capture the data type and associated
constraints of the different Attributes, regardless their final representation
format in NGSI(v2, LD).

## Examples

### Normalized Example

Normalized NGSI response

```json
{
  "id": "wastemeasurement:Brooklands",
  "type": "WasteMeasurement",
  "areaServed": {
    "value": "Brooklands"
  },
  "dateMeasurement": {
    "value": "2016-06-21"
  },
  "wasteWeight": {
    "value": 2
  },
  "recycleWeight": {
    "value": 1.5
  },
  "compostWeight": {
    "value": 0.5
  }
}
```

### key-value pairs Example

Sample uses simplified representation for data consumers `?options=keyValues`

```json
{
  "id": "wastemeasurement:Brooklands",
  "type": "WasteMeasurement",
  "areaServed": "Brooklands", 
  "wasteWeight" : 2,
  "recycleWeight" : 1.5,
  "compostWeight" : 0.5,
  "dateMeasurement": "2016-06-21"
}
```

### LD Example

Sample uses the NGSI-LD representation

```json
{
    "id": "urn:ngsi-ld:WasteContainer:wastecontainer:Fleming:12a",
    "type": "WasteContainer",
    "areaServed": {
        "type": "Property",
        "value": "Brooklands"
    },
    "dateMeasurement": {
        "type": "Property",
        "value": {
            "@type": "Date",
            "@value": "2016-06-21"
        }
    },
    "wasteWeight": {
        "type": "Property",
        "value": 2
    },
	"recycleWeight": {
        "type": "Property",
        "value": 1.5
    },
	"compostWeight": {
        "type": "Property",
        "value": 0.5
    },
    "@context": [
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld",
        "https://schema.lab.fiware.org/ld/context"
    ]
}
```

## Test it with real services

## Open issues
