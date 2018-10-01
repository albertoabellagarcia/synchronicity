# Restricted Traffic Area

## Description

An area of a city in which the traffic generated by cars or any other kind of vehicles is subjected to limitation.

A data dictionary for
DATEX II terms can be found at [http://datexbrowser.tamtamresearch.com/](http://datexbrowser.tamtamresearch.com/).


## Data Model

+ `id` : Unique identifier. 

+ `type` : Entity type. It must be equal to `RestrictedTrafficArea`.

+ `dateCreated` : Entity's creation timestamp
    + Attribute type: [DateTime](https://schema.org/DateTime)
    + Read-Only. Automatically generated.

+ `dateModified` : Last update timestamp of this entity
    + Attribute type: [DateTime](https://schema.org/DateTime)
    + Read-Only. Automatically generated.
+ `name` : Name given to the Restricted Traffic Area.
    + Normative References: [https://schema.org/name](https://schema.org/name)
    + Mandatory
+ `location` : Geolocation of the Restricted Traffic Area represented by a GeoJSON (Multi)Polygon.
    + Attribute type: `geo:json`.
    + Normative References: [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
    + Mandatory if `address`is not defined. 
+ `address` : Registered Restricted Traffic Area civic address.
    + Normative References: [https://schema.org/address](https://schema.org/address)
    + Mandatory if location not defined
+ `description` : Description about the Restricted Traffic Area. 
    + Normative References: [https://schema.org/description](https://schema.org/description)
    + Optional
+ `category` : Restricted traffic area's category(ies). The purpose of this field is to allow to tag, generally speaking, restricted traffic area entities. Particularities and detailed descriptions should be found under the corresponding specific attributes.
    + Attribute type: List of [Text](http://schema.org/Text)
    + Allowed values:
       + `public`, `private`, `publicPrivate`, `guarded`, `barrierAccess`, `gateAccess`, `forElectricalVehicles`, `onlyElectricalVehicles`, `forBikes`, `onlyResidents`, `onlyWithPermit`, `forEmployees`, `forVisitors`, `forCustomers`, `forStudents`, `forMembers`, `forDisabled`, `forResidents`, `onlyResident`, `forPedestrian`, `onlyPedestrian`
        + Any value not covered by the above enumeration and meaningful for the application.
    + The semantics of the forxxx values is that the restricted traffic area can be crossed under particular condition.
    +	The semantics of the onlyxxx values is that the restricted traffic area can be crossed only on that particular condition.
    + Mandatory
	
+ `source` : A sequence of characters giving the source of the entity data.

	+ Attribute type: [Text](http://schema.org/Text) or [URL](https://schema.org/URL)
	+ Optional
	
+ `notAllowedVehicleType` : Vehicle type(s) not allowed to cross the restricted traffic area.
    + Attribute type: List of [Text](http://schema.org/Text)
    + Allowed Values: The following list of values extends the one defined by *VehicleTypeEnum*,
	[DATEX 2 version 2.3](http://www.datex2.eu/sites/www.datex2.eu/files/DATEXIISchema_2_2_2_1.zip) :
        + (`petrolCarEuro0`, `petrolCarEuro1`, `petrolCarEuro2`, `petrolCarEuro3`, `petrolCarEuro4`, `petrolCarEuro5`, `petrolCarEuro6`, `dieselCarEuro0`, `dieselCarEuro1`, `dieselCarEuro2`, `dieselCarEuro3`, `dieselCarEuro4`, `dieselCarEuro5a`, `dieselCarEuro5b`, `dieselCarEuro6`, `agriculturalVehicle`, `bicycle`, `bus`, `car`, `caravan`, `carWithCaravan`, `carWithTrailer`, `constructionOrMaintenanceVehicle`, `lorry`, `moped`, `motorcycle`, `motorcycleWithSideCar`, `motorscooter`, `tanker`, `trailer`, `van`, `freightTransportVehicle`, `anyVehicle`)
        + Any value not covered by the above enumeration and meaningful for the application.
    + Mandatory
    
+ `specialRestrictions`: Individual vehicle type not allowed to cross the restricted traffic area in a specific time slot.

    +	Attribute type: List of [SpecialRestriction](https://gitlab.com/synchronicity-iot/synchronicity-data-models/tree/master/RestrictedTrafficArea/SpecialRestriction/schema.json)
    +	Optional
+ `restrictionExceptions`: Individual vehicle type allowed to cross the restricted traffic area in a specific time slot.
    +	Attribute type: List of [RestrictionException](RestrictedTrafficArea/RestrictionException/RestrictionException/schema.json)
    +	Optional
+ `restrictionValidityHours`: Days of the week and hours in which the traffic restriction is active.
    +	Normative references: http://schema.org/openingHours
    +	Optional
    	
+ `regulation`: A URL pointing to the regulation for the specific restricted traffic area.
	+ Attribute type: Text or URL
    + Optional
+ `validityStartDate`: The date from which the restriction is applied.
    + Attribute type: DateTime
    +	Optional
+ `validityEndDate`: The date at which the restriction is dismissed.
    +	Attribute type: DateTime
    +	Optional
+ `security` : Security aspects provided by this restricted traffic area.
    +	Attributes: List of Text
    +	Allowed values: The following, some of them, defined by ParkingSecurityEnum of DATEX II version 2.3:
        +	(`patrolled`, `securityStaff`, `externalSecurity`, `cctv`, `dog`, `guard24hours`, `lighting`, `floodLight`, `fencesareaSeperatedFromSurroundings`, `bollard`, `camera`)
        + Any value not covered by the above enumeration and meaningful for the application.
●	Optional