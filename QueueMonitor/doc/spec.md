# Queue Monitor

## Description
The proposed data model is intended to describe an office counter queue system on a daily run.
The same service can be provided by several offices.
The same office can provide different services.
The same office can have different queue lines with different priority level.
This data model covers the single queue line for a single service provided by a single office.
Ticket numbering should be set up to 0 at the beginning of each service running day.


## Data Model

+ `id` : Unique identifier. 

+ `type` : Entity type. It must be equal to `QueueMonitor`.

+ `dateCreated` : Entity's creation timestamp
    + Attribute type: [DateTime](https://schema.org/DateTime)
    + Read-Only. Automatically generated.

+ `dateModified` : Last update timestamp of this entity
    + Attribute type: [DateTime](https://schema.org/DateTime)
    + Read-Only. Automatically generated.

+ `source` : A sequence of characters giving the source of the entity data.
    + Attribute type: [Text](http://schema.org/Text) or [URL](https://schema.org/URL)
    + Optional

+ `localId` : Unique identifier from the source data set.
    + Attribute type: [Text](http://schema.org/Text)
    + Optional

+ `officeName` : name of the office providing the service.
    + Attribute type: [Text](http://schema.org/Text)
    + Optional

+ `location` : Geolocation of the office desk where the queue is generated represented by a GeoJSON Point.
    + Attribute type: geo:json.
    + Normative References: https://tools.ietf.org/html/rfc7946 
    + Mandatory if `address` is not defined.

+ `address` : Civic address of the office desk where the queue is generated.
    + Normative References: https://schema.org/address 
    + Mandatory if `location` not defined

+ `serviceName` : name of the service provided at the counter.
    + Normative References: https://schema.org/name
    + Mandatory

+ `serviceId` : id of the service provided at the counter. The same service could be provided by many offices
    + Attribute type: [Text](http://schema.org/Text)
    + Optional

+ `description` : description of the service provided at the counter.
    + Attribute type: [Text](http://schema.org/Text)
    + Optional

+ `serviceStatus` : status of the service at timestamp time.
    + Attribute type: [Text](http://schema.org/Text)
    + Allowed values: 
    	+ `Open`, `Suspended`, `Closed`
    + Mandatory

+ `serviceStatusNote` : additional note to the service status
    + Attribute type: [Text](http://schema.org/Text)
    + Example: eg. “service suspended from 11:00am to 14:30pm”
    + Optional

+ `scheduleTime` : scheduled working time of the service.
    + Attribute type: [Text](http://schema.org/Text)
    + Optional

+ `queueLine` : description about the queue line associated to the service. The same office counter could serve different queue lines with different priority level.
    + Attribute type: [Text](http://schema.org/Text)
    + Optional

+ `linePriority` : level of priority of this line at Counter Queue
    + Attribute type: integer
    + Optional

+ `lastTicketIssued` : last ticket number issued or this line at Counter Queue
    + Attribute type: integer
    + Mandatory

+ `lastTicketIssuedLabel` : label associated to the `lastTicketIssued`
    + Attribute type: [Text](http://schema.org/Text)
    + Examples: “A32”, “B41”...
    + Optional

+ `ticketServed` : ticket number currently served by this line at Counter Queue
    + Attribute type: integer
    + Mandatory

+ `ticketServedLabel` : label associated to the currently ticketServed  by this line at Counter Queue 
    + Attribute type: [Text](http://schema.org/Text)
    + Examples: “A32”, “B41”...
    + Optional

+ `ticketsToServe` : tickets left to serve as `ticketIssued` minus `lastTicketServed`
    + Attribute type: integer
    + Optional
