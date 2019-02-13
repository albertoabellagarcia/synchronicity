# GtfsTransitFeedFile

## Description

Provides the Location (URL) of the ZIP file containing a valid GTFS transit feed (See https://developers.google.com/transit/gtfs/reference for further info). This is intended to manage GTFS static data through NGSI.

## Data Model

+ `id`: Entity Id
    + It shall be `urn:ngsi-ld:GtfsTransitFeedFile:<Reference_Zone>:<Publisher_Name>`.
    	+ `Reference_Zone`: [recommended] represents the City or the Area covered by the provided feed, e.g. SANTANDER for the feeds covering Santander City
		+ `Publisher_Name`: [recommended] contains the full name of the organization that publishes the feed. This may be the same as one of the agency_name values in agency.txt and SHOULD be equal to the `feed_publisher_name` field on `feed_info.txt` file (when present).

+ `type`: Entity Type 
    + It shall be equal to `GtfsTransitFeedFile`

+ `description`: describes what kind of information can be found in the feed file (service, public/private, type, coverage, etc.)
	+ Attribute type: [Text](https://schema.org/Text)
	+ Optional

+ `publisher`: identifies the entity publishing the transit feed file
	+ Attribute type: StructuredValue
		+ `name`: defines the name of the Publisher entity. It SHOULD be the same as `feed_publisher_name` in `feed_info.txt` if exists.
			+ Attribute type: [Text](https://schema.org/Text)
			+ Mandatory if publisher attribute is present and no publisherURL is provided
		+ `publisherURL`: specifies the publisher entity’s URL
			+ Attribute type: Text representing a URL
			+ Mandatory if publisher attribute is present and no name is provided
	+ Optional

+ `source`: A text containing the original source of the GTFS data, i.e. where the original GTFS data was/is hosted (e.g. the URL of the portal publishing the GTFS data needed to generate the feed file on this context entity)
	+ Attribute type: [Text](https://schema.org/Text)
	+ Optional

+ `dateCreated` : Entity's creation timestamp.
    + Attribute type: [DateTime](https://schema.org/DateTime)
    + Read-Only. Automatically generated.

+ `dateModified` : Last update timestamp of this Entity.
    + Attribute type: [DateTime](https://schema.org/DateTime)
    + Mandatory. Automatically generated if not provided by the “update” action.

+ `version`: points out to the file’s version included in this entity
	+ Attribute type: StructuredValue
		+ `id`: file version descriptor
			+ Attribute type: [Text](https://schema.org/Text)
			+ Mandatory if version attribute is present
		+ `dateReleased`: version release date
			+ Attribute type: [DateTime](https://schema.org/DateTime)
			+ Mandatory if version attribute is present
	+ Optional

+ `referenceZone`: identifies the city/area covered by the service in the feed file
	+ Attribute type: [Text](https://schema.org/Text)
	+ Optional

+ `startDate`: points out the date this feed comes into effect. This SHOULD coincide with start_date in feed_info.txt (if exists).
	+ Attribute type: [DateTime](https://schema.org/DateTime)
	+ Mandatory

+ `endDate`: points out the date this feed expires. This SHOULD coincide with end_date in feed_info.txt (if exists).
	+ Attribute type: [DateTime](https://schema.org/DateTime)
	+ Mandatory

+ `feedFileURL`: according GTFS recommendations, a GTFS feed is composed by a set of defined text files compiled in a ZIP file. This attribute contains the URL where this ZIP can be located to be downloaded. To avoid [Orion Context Broker forbidden characters](https://fiware-orion.readthedocs.io/en/master/user/forbidden_characters/index.html), this URL will be shared as an encoded URL. A metadata attribute will indicate the encoding mechanism used.
	+ Attribute type: encodedURL
	+ Attribute metadata:
		+ encoding: encoding mechanism to encode original URL (useful to decode the URL) 
			+ type: [Text](https://schema.org/Text)  
	+ Mandatory

+ `feedFileContent`: according to GTFS recommendations, a GTFS feed is composed by a set of defined text files compiled in a ZIP file. This attribute lists the txt files stored in the ZIP pointed by feedFileURL.
	+ Attribute type: Array (list) of [Text](https://schema.org/Text) . Array listing all txt files included in this file version
	+ Optional



### Example of use 1 (Normalized Format)

```json
{
	"id": "urn:ngsi-ld:GtfsTransitFeedFile:santander:TUS",
	"type": "GtfsTransitFeedFile",
	"description": {
		"type": "Text",
		"value": "Santander City Urban Transportation Service GTFS Feed File"
	},
	"publisher": {
		"type": "StructuredValue",
		"value": {
			"name": "S.M.T.U. SANTANDER",
			"publisherURL": "http://www.tusantander.es"
		}
	},
	"source": {
		"type": "Text",
		"value": "http://datos.santander.es"
	},
	"dateCreated": {
		"type": "DateTime",
		"value": "2018-08-11T15:00:05.00Z"
	},
	"dateModified": {
		"type": "DateTime",
		"value": "2018-10-10T00:00:05.00Z"
	},
	"version": {
		"type": "StructuredValue",
		"value": {
			"id": "TUS_Programacion_v1.1",
			"dateReleased": "2018-10-10T00:00:00.00Z"
		}
	},
	"referenceZone": {
		"type": "Text",
		"value": "Santander Municipality - 39075"
	},
	"startDate": {
		"type": "DateTime",
		"value": "2018-10-07T06:00:00.00Z"
	},
	"endDate": {
		"type": "DateTime",
		"value": "2019-06-29T23:59:59.00Z"
	},
	"feedFileURL": {
		"type": "encodedURL",
		"value": "http%3A%2F%2Fdatos.santander.es%2FproxyFileCKAN.php%3Fdataset%3D415f8091-64a1-4988-bec1-5117b93a68c5%26resource%3D92f4a4e9-6132-4666-b673-aee4524dee3e%26file%3Dprogramaciongtfs.zip",
		"metadata": {
			"encoding":{
				"value": "encoded JavaScript URL"
			}
		}
	},
	"feedFileContent": {
		"type": "Text",
		"value": [
			"agency.txt",
			"calendar.txt",
			"calendar_dates.txt",
			"routes.txt",
			"shapes.txt",
			"stops_times.txt",
			"stops.txt",
			"trips.txt"
		]
	}
}
```

### Example of use 2  (?options=keyValues simplified representation for data consumers)
```json
{
    "id": "urn:ngsi-ld:GtfsTransitFeedFile:santander:TUS",
    "type": "GtfsTransitFeedFile",
    "dateCreated": "2018-08-11T15:00:05.00Z",
    "dateModified": "2018-10-10T00:00:05.00Z",
    "description": "Santander City Urban Transportation Service GTFS Feed File",
    "endDate": "2019-06-29T23:59:59.00Z",
    "feedFileContent": [
        "agency.txt",
        "calendar.txt",
        "calendar_dates.txt",
        "routes.txt",
        "shapes.txt",
        "stops_times.txt",
        "stops.txt",
        "trips.txt"
    ],
    "feedFileURL": "http%3A%2F%2Fdatos.santander.es%2FproxyFileCKAN.php%3Fdataset%3D415f8091-64a1-4988-bec1-5117b93a68c5%26resource%3D92f4a4e9-6132-4666-b673-aee4524dee3e%26file%3Dprogramaciongtfs.zip",
    "publisher": {
        "name": "S.M.T.U. SANTANDER",
        "publisherURL": "http://www.tusantander.es"
    },
    "referenceZone": "Santander Municipality - 39075",
    "source": "http://datos.santander.es",
    "startDate": "2018-10-07T06:00:00.00Z",
    "version": {
        "id": "TUS_Programacion_v1.1",
        "dateReleased": "2018-10-10T00:00:00.00Z"
    }
}

```


## Open issues
