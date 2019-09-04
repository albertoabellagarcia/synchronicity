# Privacy Object

## Description

The PrivacyObject entity represents an IoT device (a sensor typically) with the information about the privacy directly linked to this IoT device.
Several attributes are used to describe the IoT device in the context of the privacy.
Notably, an attribute provides the location of the IoT device and two others give more information about the exact position.
An attribute is also used to decribe the IoT device and a second attribute gives the purpose of the IoT sensor.
Other attributes are very focused on the privacy and GDPR with the aim to categorize the information associated to the IoT device.

## Data Model

A JSON Schema corresponding to this data model can be found
[here](../schema.json).

-   `id` : Unique identifier of the entity.

-   `type` : It must be equal to `PrivacyObject`.

-   `refDevice` : Device linked to this PrivacyObject entity.

    -   Attribute type: List of reference to entity(ies) of type
        [Device](https://github.com/Fiware/dataModels/blob/master/specs/Device/Device/doc/spec.md)
    -   Optional

-   `name` : Name of the PrivacyObject entity.

    -   Attribute Type: [String](http://schema.org/String)
	-   Optional

-   `location`: Coordinates of the PrivacyObject entity. A `Point` represents the latitude and the longitude of this entity.

    -   Attribute Type: `geo:json`
	-   Normative References: [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
	-   Mandatory

-   `isIndoor`: Flag to indicate if the entity is installed indoor or outdoor.

    -   Attribute Type: [Boolean](http://schema.org/Boolean)
	-   Optional

-   `floor`: The floor where the device is installed.

    -   Attribute Type: [Number](http://schema.org/Number)
	-   Optional

-   `description` : Description in American English. For another language, the description attribute can be used followed by the underline symbol and the corresponding language tag. More information is available here: [i18N](https://github.com/FIWARE/dataModels/blob/master/specs/guidelines.md#internationalization-i18n)

    -   Attribute type: [String](http://schema.org/String)
    -   Optional

-   `user` : Identifier of an anonymous user. This identifier is in fact a unique URN which can be used to recognize anonymously a user.

    -   Attribute Type: [String](http://schema.org/String)
	-   Mandatory
	
-   `purpose` : Purpose in American English. For another language, the purpose attribute can be used followed by the underline symbol and the corresponding language tag. More information is available here: [i18N](https://github.com/FIWARE/dataModels/blob/master/specs/guidelines.md#internationalization-i18n)

    -   Attribute type: [String](http://schema.org/String)
    -   Optional

-   `category` : Category of the entity. It describes the kind of sensors or devices.

    -   Attribute type: [String](http://schema.org/String)
    -   Optional

-   `recipientList` : List containing the recipients. A recipient is the beneficiary using the data generated by a sensor. Each recipient is represented by an URI which allows its unique identification.

    -   Attribute type: Array of [String](http://schema.org/String)
    -   Optional
	
-   `owner` : Owner, generally an organization, responsible for the sensor or for the IoT device. Normally, it is the data controller.

    -   Attribute type: [String](http://schema.org/String)
    -   Optional

-   `isPersonalData` : Flag to indicate if the entity is providing or contains personal data.

    -   Attribute type: [Boolean](http://schema.org/Boolean)
    -   Optional
	
-   `retentionPeriod` : Period of data retention.

    -   Attribute type: [String](http://schema.org/String)
    -   Optional
	
-   `legitimateInterest` : Legitimate interest associated to the entity. This means for which high-level finality the data collection is made.

    -   Attribute type: [String](http://schema.org/String)
    -   Optional
	
-   `crossborderTransfer` : Indication about the crossborder transfer linked to the entity.

    -   Attribute type: [String](http://schema.org/String)
    -   Optional
    
-   `image` : Link (URI) to the picture of the entity.

    -   Attribute type: [String](http://schema.org/String)
    -   Mandatory

**Note**: JSON Schemas only capture the NGSI simplified representation, this
means that to test the JSON schema examples with a
[FIWARE NGSI version 2](http://fiware.github.io/specifications/ngsiv2/stable)
API implementation, you need to use the `keyValues` mode (`options=keyValues`).

## Examples

### Normalized Example

Normalized NGSI response

```json
{
    "id": "urn:ngsi-ld:PrivacyObject:1044_parking",
    "type": "PrivacyObject",
    "refDevice": {
        "type": "Relationship",
        "value": "1044_parking"
    },
    "name": {
        "value": "1004_parking"
    },
    "location": {
        "type": "geo:json",
        "value": {
            "type": "Point",
            "coordinates": [46.18311, 6.14132]
        }
    },
    "isIndoor": {
        "value": false
    },
    "floor": {
        "value": 0
    },
    "description": {
        "value": "Electromagnetic and ultrasonic sensor"
    },
    "description_fr": {
        "value": "Capteur électromagnétique et à ultrasons"
    },
    "user": {
        "value": "urn:ngsi-ld:User:abcdef"
    },
    "purpose": {
        "value": "Detecting the presence of a vehicle on a parking slot."
    },
    "purpose_fr": {
        "value": "Détecter la présence d'un véhicule sur une place de parc."
    },
    "category": {
        "value": "Parking sensor"
    },
    "recipientList": {
        "value": ["urn:ngsi-ld:User:CommunalAdministration", "urn:ngsi-ld:User:Motorists"]
    },
    "owner": {
        "value": "City of Carouge"
    },
    "isPersonalData": {
        "value": false
    },
    "retentionPeriod": {
        "value": "< 1 month"
    },
    "legitimateInterest": {
        "value": "Facilitate and understand parking habits"
    },
    "crossborderTransfer": {
        "value": "None"
    },
    "image": {
        "value": "http://www.example.com/device1.jpg"
    }
}
```

### key-value pairs Example

Sample uses simplified representation for data consumers `?options=keyValues`

```json
{
    "id": "urn:ngsi-ld:PrivacyObject:1044_parking",
    "type": "PrivacyObject",
    "refDevice": "Device:1044_parking",
    "name": "1004_parking",
    "location": {
        "type": "Point",
        "coordinates": [46.18311, 6.14132]
    },
    "isIndoor": false,
    "floor": 0,
    "description": "Electromagnetic and ultrasonic sensor",
    "description_fr": "Capteur électromagnétique et à ultrasons",
    "user": "urn:ngsi-ld:User:abcdef",
    "purpose": "Detecting the presence of a vehicle on a parking slot.",
    "purpose_fr": "Détecter la présence d'un véhicule sur une place de parc.",
    "category": "Parking sensor",
    "recipientList": ["urn:ngsi-ld:User:CommunalAdministration", "urn:ngsi-ld:User:Motorists"],
    "owner": "City of Carouge",
    "isPersonalData": false,
    "retentionPeriod": "< 1 month",
    "legitimateInterest": "Facilitate and understand parking habits",
    "crossborderTransfer": "None",
    "image": "http://www.example.com/device1.jpg"
}

```

## Test it with a real service

## Open Issues