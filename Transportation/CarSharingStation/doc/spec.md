# Car Sharing Station

## Description

A site dedicated to car sharing with either direct access from a road or with suitable and clearly marked access points.

A data dictionary for
DATEX II terms can be found at [http://datexbrowser.tamtamresearch.com/](http://datexbrowser.tamtamresearch.com/).


## Data Model

+ `id` : Unique identifier. 

+ `type` : Entity type. It must be equal to `CarSharingStation`.

+ `dateCreated` : Entity's creation timestamp
    + Attribute type: [DateTime](https://schema.org/DateTime)
    + Read-Only. Automatically generated.

+ `dateModified` : Last update timestamp of this entity
    + Attribute type: [DateTime](https://schema.org/DateTime)
    + Read-Only. Automatically generated.
+   `source` : A sequence of characters giving the source of the entity data.
    + Attribute type: Text or URL
    + Optional    
+ `name` : Name given to the Car Sharing Station zone.
    + Normative References: [https://schema.org/name](https://schema.org/name)
    + Mandatory
+ `location` : Geolocation of the Car Sharing Station site represented by a GeoJSON (Multi)Polygon.
    + Attribute type: `geo:json`.
    + Normative References: [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
    + Mandatory if `address`is not defined. 
    + 
+ `address` : Registered Car Sharing Station civic address.
    + Normative References: [https://schema.org/address](https://schema.org/address)
    + Mandatory if location not defined
    
+ `description` : Description about the Car Sharing Station. 
    + Normative References: [https://schema.org/description](https://schema.org/description)
    + Optional
    + 
+ `category`: Denotes whether the Car Sharing station has direct access from a road or with suitable and clearly marked access points.
    + Attribute type: [Text](http://schema.org/Text)
    + Allowed values:
       + `onStreet`, `offStreet`
+ `areBordersMarked` : Denotes whether parking spots are delimited (with blank lines or similar) or not.
    +	Attribute type: Boolean
    +	Optional
    
+	`totalSpotNumber` : The total number of spots offered by this car sharing station.     This number can be difficult to be obtained for those car sharing stations on which     spots are not clearly marked by lines.
    +	Attribute type: Number
    +	Allowed values: Any positive integer number or 0.
    +	Normative references: DATEX 2 version 2.3 attribute parkingNumberOfSpaces of the ParkingRecord class.
    + Optional

+	`totalSpotNumberForElectricVehicles` : The total number of spots offered by this car sharing station and dedicated to electric vehicles; this spots are intended to be equipped with a charging station.
    +	Attribute type: Number
    +	Allowed values: Any positive integer number or 0.
    +	Normative references: DATEX 2 version 2.3 attribute parkingNumberOfSpaces of the ParkingRecord class.
    + Optional

+	`totalSpotNumberForDisabledPeople ` : The total number of spots offered by this car sharing station and dedicated to disabled people.
    +	Attribute type: Number
    +	Allowed values: Any positive integer number or 0.
    +	Normative references: DATEX 2 version 2.3 attribute parkingNumberOfSpaces of the ParkingRecord class.
    + Optional
    
+ `totalAvailableSpotNumber`: The number of spots available globally, including reserved spaces, such as those for disabled people. This might be harder to estimate at those car sharing stations on which spots borders are not clearly marked by lines.
    +	Attribute type: Number
    +	Allowed values: A positive integer number, including 0. It must lower or equal than totalSpotNumber.
    +	Metadata:
        +	`timestamp` : Timestamp of the last attribute update
            + type: DateTime
    +	Optional
+ `availableSpotNumberForDisabledPeople`: The number of spots available for disabled people. This might be harder to estimate at those car sharing stations on which spots borders are not clearly marked by lines.
  + Attribute type: Number
  + Allowed values: A positive integer number, including 0. It must lower or equal than totalSpotNumber.
    +	Metadata:
        +	`timestamp` : Timestamp of the last attribute update
            + type: DateTime
    +	Optional
+ `availableSpotNumberForElectricVehicles`: The number of spots available for electric vehicles. This might be harder to estimate at those car sharing stations on which spots borders are not clearly marked by lines.
  + Attribute type: Number
  + Allowed values: A positive integer number, including 0. It must lower or equal than totalSpotNumber.
    +	Metadata:
        +	`timestamp` : Timestamp of the last attribute update
            + type: DateTime
    +	Optional
    
+ `totalAvailableVehicles`: The number of available vehicle in the car sharing station.
  + Attribute type: Number
  + Allowed values: A positive integer number, including 0. It must lower or equal than totalSpotNumber.
    +	Metadata:
        +	`timestamp` : Timestamp of the last attribute update
            + type: DateTime
    +	Optional
    	
+ `totalAvailableVehiclesForDisabledPeople`: The number of available vehicle in the car sharing station dedicated to disabled people.
  + Attribute type: Number
  + Allowed values: A positive integer number, including 0. It must lower or equal than totalSpotNumber.
    +	Metadata:
        +	`timestamp` : Timestamp of the last attribute update
            + type: DateTime
    +	Optional
    	
+ `totalAvailableElectricVehicles`: The number of available electric vehicle in the car sharing station.
  + Attribute type: Number
  + Allowed values: A positive integer number, including 0. It must lower or equal than totalSpotNumber.
    +	Metadata:
        +	`timestamp` : Timestamp of the last attribute update
            + type: DateTime
    +	Optional
+	`parkingMode` : Parking mode(s).
    +	Attribute type: List of [Text](http://schema.org/Text)
    +	Allowed values: Those defined by the DATEX II version 2.3 ParkingModeEnum enumeration:
        +	(perpendicularParking, parallelParking, echelonParking)
    +	Optional

+	`image` : A URL containing a photo of this parking site.
    +	Normative References: https://schema.org/image
    +	Optional

+	`refParkingSpot` : Individual parking spots belonging to this parking site.
    +	Attribute type: List of references to [ParkingSpot](https://fiware-datamodels.readthedocs.io/en/latest/Parking/ParkingSpot/doc/spec/index.html)
    +	Optional
    
+	`areaServed` : Area served by this car sharing station. Precise semantics can depend on the application or target city. For instance, it can be a neighbourhood, burough or district.
    +	Attribute type: [Text](http://schema.org/Text)
    +	Optional

+	`providedVehicleType`:  Vehicle type(s) provided by the car sharing station.
    +	Attribute type: List of [Text](http://schema.org/Text)
    +	Allowed Values:
        + (`electricVehicle`, `car`)
    +	Mandatory
    	
+	`providers` : Car sharing service providers.
    +	Attribute type: List of URL
    +	Normative references: https://schema.org/url
    + Optional

+	`contactPoint` : onstreet car sharing station contact point.
    +	Normative references: https://schema.org/contactPoint
    +	Optional
+ `security` : Security aspects provided by this car sharing station.
    +	Attributes: List of Text
    +	Allowed values: The following, some of them, defined by ParkingSecurityEnum of DATEX II version 2.3:
        +	(`patrolled`, `securityStaff`, `externalSecurity`, `cctv`, `dog`, `guard24hours`, `lighting`, `floodLight`, `fences`,`areaSeperatedFromSurroundings`, `bollard`, `camera`)
        + Any value not covered by the above enumeration and meaningful for the application.
●	Optional
