# Restriction Exception

## Description

A “Restriction Exception” represents a particular case that specialise restriction reported in a “Restricted Traffic Areas”; for instance it could describe particular permissions applied to specific kind vehicles.

A data dictionary for
DATEX II terms can be found at [http://datexbrowser.tamtamresearch.com/](http://datexbrowser.tamtamresearch.com/).


## Data Model

+ `allowedVehicleType` : Vehicle type(s) allowed to cross the restricted traffic area.
    + Attribute type: [Text](http://schema.org/Text)
    + Allowed Values: The following list of values extends the one defined by *VehicleTypeEnum*, [DATEX 2 version 2.3](http://www.datex2.eu/sites/www.datex2.eu/files/DATEXIISchema_2_2_2_1.zip) :
        + (`petrolCarEuro0`, `petrolCarEuro1`, `petrolCarEuro2`, `petrolCarEuro3`, `petrolCarEuro4`, `petrolCarEuro5`, `petrolCarEuro6`, `dieselCarEuro0`, `dieselCarEuro1`, `dieselCarEuro2`, `dieselCarEuro3`, `dieselCarEuro4`, `dieselCarEuro5a`, `dieselCarEuro5b`, `dieselCarEuro6`, `agriculturalVehicle`, `bicycle`, `bus`, `car`, `caravan`, `carWithCaravan`, `carWithTrailer`, `constructionOrMaintenanceVehicle`, `lorry`, `moped`, `motorcycle`, `motorcycleWithSideCar`, `motorscooter`, `tanker`, `trailer`, `van`, `freightTransportVehicle`, `anyVehicle`)
        + Any value not covered by the above enumeration and meaningful for the application.
    + Mandatory
+ `exceptionValidityHours`: Days of the week and hours in which the exception is valid.
    +	Normative references: http://schema.org/openingHours
    +	Optional
 	
+ `refVehicleModel`: Specify characteristics of the vehicle for which the exception has been established.
    + 	Attribute type: Reference to a VehicleModel entity.
    +	Optional
   
+ `description`: Description about the exception.
    +	Normative References: https://schema.org/description
    +	Optional
+ `refRestrictedTrafficArea` : The Restricted Traffic Area this exception belongs.
    +	Attribute type: Reference to an entity of type [RestrictedTrafficArea](https://gitlab.com/synchronicity-iot/synchronicity-data-models/tree/master/RestrictedTrafficArea/schema.json)
    +	Mandatory