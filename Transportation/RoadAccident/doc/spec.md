# Road Accident

## Description
The proposed data model is intended to describe road accidents giving description and information about causes, casualties and aftermath.
The data-model tries to adher to EU guide-lines to treat statistical data concerning road-accidents



## Data Model

+ `id` : Unique identifier. 

+ `type` : Entity type. It must be equal to `RoadAccident`.

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

+ `status` : status of road accident (eg. "OnGoing", "Solved", "Archived").
    + Attribute type: [Text](http://schema.org/Text)
    + Allowed values:
       + `onGoing`, `solved`, `archived`
       + Any value not covered by the above enumeration and meaningful for the application.
    + Semantics of values: 
       + `onGoing` : the accident is still active and affecting road circulation
       + `solved` : the accident has been solved and it is not affecting the road circulation anymore
       + `archived` : the aftermath of the accidents has been filed (eg. "victims within 30 days") and the accident can be historicized
    + Mandatory

+ `accidentDate` : datetime of the accident
    + Attribute type: [DateTime](https://schema.org/DateTime)
    + Mandatory if `accidentStatisticalDate` is missing

+ `accidentStatisticalDate` : approximate datetime of the accident (often original accident data source reports only statistical attributes such as season, weeakday and approximate hour).
    + Attribute type: structured
       + `year` : integer 
       + `quarter` : integer
          + Allowed values : 1, 2, 3, 4
       + `weekday` : [Text](http://schema.org/Text)
          + Allowed values : "Monday"..."Sunday"
       + `hour` : integer
          + Allowed values : 0..24
          + Semantics : 24 means "unknown"          
    + Mandatory if `accidentDate` is missing

+ `location` : Geolocation of the Road Accident represented by a GeoJSON Point.
    + Attribute type: `geo:json`.
    + Normative References: [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
    + Mandatory if `address` is not defined. 
    
+ `address` : Address of the Road Accident
    + Normative References: [https://schema.org/address](https://schema.org/address)
    + Mandatory if `location` not defined

+ `accidentType` : quick classification this Road Accident.
    + Attribute type: list of integer
    + Values: see Appendix 1
    + Optional

+ `accidentDescription` : Description about this Road Accident as a combination of codified situation enlisted in Appendix 2
    + Attribute type: list of integer
    + Values: see Appendix 2
    + Optional
    
+ `weatherConditions` : brief description of weather conditions during this Road Accident
    + Attribute type: list of integer
    + Values: see Appendix 3
    + Optional
    
+ `roadSurface` : brief description of the condition of the road during the accident.
    + Attribute type: integer
    + Values: see Appendix 4
    + Optional

+ `roadPaving` : brief description of the paving status of the road where the accident took place.
    + Attribute type: integer
    + Values: see Appendix 5 
    + Optional

+ `accidentLocation` : brief description if the accident took place in a urban or extra-urban area
    + Attribute type: integer
    + Optional
    + Values: see Appendix 6

+ `roadClass` : The classification of road where this accident took place.
    +   Attribute type: [Text](https://schema.org/Text)
    +   Allowed values: Those described by
        [OpenStreetMap](http://wiki.openstreetmap.org/wiki/Key:highway).
    +   Optional

+ `roadIntersection` : brief description of the piece of the road where the accident took place
    + Attribute type: integer
    + Optional
    + Values: see Appendix 7 

+ `roadTrunk` : brief description of type of trunk of the road where the accident took place
    + Attribute type: integer
    + Optional
    + Values: see Appendix 8 

+ `signRoad` : briefd description of the road sign where the accident took place
    + Attribute type: integer
    + Optional
    + Values: see Appendix 9

+ `pedestriansInvolved` : boolean to determine if pedestrians were involved in the accidents
    + Attribute type: boolean
    + Optional

+ `vehiclesInvolved` : list of the vehicles (and pedestrians) involved because the accident
    + Attribute type: list of integer
    + Values: combination of values in Appendix 10
    + Optional
    + Example : _[1, 5]_ (eg. ''bicycle' and 'car')

+ `weakestSubject` : vehicle that represent the weakest subject involved because the accident (usually pedestrian)
    + Attribute type: integer
    + Values: see Appendix 10
    + Optional

+ `numPassengersInjured` : number of vehicle's passengers injured because the accident
    + Attribute type: integer
    + minimum : 0
    + Optional

+ `numPassengersDead` : number of vehicle's passengers dead because the accident
    + Attribute type: integer
    + minimum : 0
    + Optional

+ `numPedestrianInjured` : number of pedestrians injured because the accident
    + Attribute type: integer
    + minimum : 0
    + Optional

+ `numPedestrianDead` : number of pedestrians dead because the accident
    + Attribute type: integer
    + minimum : 0
    + Optional

+ `totalInjured` : total number of people injured (not dead) because the accident
    + Attribute type: integer
    + minimum : 0
    + Optional

+ `totalDeadPeopleWithin24Hours` : number of people dead directly because the accident
    + Attribute type: integer
    + minimum : 0
    + Optional

+ `totalDeadPeopleWithin30Days` : number of people dead because the aftermath of the accident
    + Attribute type: integer
    + minimum : 0
    + Optional

 
##
##

## Appendix 1: Suitable values codes for `accidentType` attribute

+ 1:	Frontal collision;
+ 2:	Frontal-lateral collision;
+ 3:	Side crash;
+ 4:	Collision;
+ 5:	Pedestrian investment;
+ 6:	Impact with vehicle stopped or stopped;
+ 7:	Impact with parked vehicle;
+ 8:	Impact with obstacle;
+ 9:	Impact with train;
+ 10:	Spill, slip;
+ 11:	Accident due to sudden braking;
+ 12:	Accident due to falling from a vehicle;


## Appendix 2: Suitable values codes for `accidentDescription` attribute

+ 0:	Unspecified circumstance;
+ 1:	Driver proceeded regularly without turning;
+ 2:	Driver proceeded with a distracted driving or undecided course;
+ 3:	Driver proceeded without maintaining a safe distance;
+ 4:	Driver proceeded without giving priority to the vehicle coming from the right;
+ 5:	Driver proceeded without respecting the stop;
+ 6:	Driver proceeded without respecting the signal to give precedence;
+ 7:	Driver proceeded against traffic;
+ 8:	Driver proceeded without respecting the traffic light or agent signals;
+ 10:	Driver proceeded without respecting the signs of prohibition of transit or access;
+ 11:	Driver proceeded with speeding;
+ 12:	Driver proceeded without respecting the speed limits;
+ 13:	Driver proceeded with the dazzling lights crossing other vehicles;
+ 14:	Driver turned right regularly;
+ 15:	It turned irregularly to the right;
+ 16:	Driver turned left regularly;
+ 17:	It turned irregularly to the left;
+ 18:	Driver passed at the intersection;
+ 20:	Driver proceeded regularly;
+ 21:	Driver proceeded with a distracted driving or undecided course;
+ 22:	Driver proceeded without maintaining a safe distance;
+ 23:	Driver proceeded with speeding;
+ 24:	Driver proceeded without respecting the speed limits;
+ 25:	It proceeded not near the right edge of the roadway;
+ 26:	Driver proceeded against traffic;
+ 27:	Driver proceeded without respecting the signs of prohibition of transit or access;
+ 28:	Driver proceeded with the dazzling lights crossing other vehicles;
+ 29:	Driver passed regularly;
+ 30:	It passed irregularly to the right;
+ 31:	Driver overtook on a curve, on a hill or with insufficient visibility;
+ 32:	It overtook a vehicle that was overtaking another;
+ 33:	Driver passed without observing the appropriate prohibition sign;
+ 34:	Maneuvered in relegation or conversion;
+ 35:	Driver maneuvered to get into the flow of circulation;
+ 36:	Maneuvering To turn left (private passage, distributor);
+ 37:	Driver maneuvered regularly to stop or stop;
+ 38:	Driver maneuvered irregularly to stop or stop;
+ 39:	It was joined by other irregular two-wheeled vehicles;
+ 40:	Driver proceeded regularly;
+ 41:	Driver proceeded with speeding;
+ 42:	Driver proceeded without respecting the speed limits;
+ 43:	Driver proceeded against traffic;
+ 44:	Driver passed the vehicle in gear;
+ 45:	Maneuvered;
+ 46:	Maneuvered without respecting traffic light or agent signals;
+ 47:	Driver came out of the driveway without precaution;
+ 48:	Driver stepped out of the lane and hit the pawn;
+ 49:	It did not give priority to the pedestrian on the appropriate crossings;
+ 50:	It overtook a vehicle stopped to allow the crossing;
+ 51:	Driver hit the pedestrian with the load;
+ 52:	Driver was passing a tram unevenly at the stop;
+ 60:	Driver proceeded regularly;
+ 61:	Driver proceeded with a distracted driving or undecided course;
+ 62:	Driver proceeded without maintaining a safe distance;
+ 63:	Driver proceeded against traffic;
+ 64:	Driver proceeded with speeding;
+ 65:	Driver proceeded without respecting the speed limits;
+ 66:	Driver proceeded without respecting the signs of prohibition of transit or access;
+ 67:	Driver was passing another vehicle in gear;
+ 68:	Driver imprudently crossed the level crossing;
+ 70:	Spill with spillage to avoid impact;
+ 71:	Listening with spillage for distracted driving;
+ 72:	List with over-speed spill;
+ 73:	Driver suddenly braked with consequence to the transported;
+ 74:	Fall of person from vehicle for: door opening;
+ 75:	Fall of person from vehicle for: descent from vehicle in motion;
+ 76:	Fall of person from vehicle due to: clinging or improperly placed;
+ 80:	Brake failure or failure;
+ 81:	Breakage or steering failure;
+ 82:	Tire burst or excessive wear;
+ 83:	Lack or insufficiency of headlights or position lights;
+ 84:	Lack or insufficiency of flashing lights or stopping light signals;
+ 85:	Breaking of trailer coupling parts;
+ 86:	Deficiency of dangerous goods transport equipment;
+ 87:	Deficiency of the adaptations prescribed to vehicles of physically handicapped people;
+ 88:	Wheel detachment;
+ 89:	Lack or insufficiency of visual devices for cycles;


## Appendix 3 : Suitable values codes for `weatherConditions` attribute

+	0	:	clearNight
+	1	:	sunnyDay
+	2	:	slightlyCloudy
+	3	:	partlyCloudy
+	4	:	mist
+	5	:	fog
+	6	:	highClouds
+	7	:	cloudy
+	8	:	veryCloudy
+	9	:	overcast
+	10	:	lightRainShower
+	11	:	drizzle
+	12	:	lightRain
+	13	:	heavyRainShower
+	14	:	heavyRain
+	15	:	sleetShower
+	16	:	sleet
+	17	:	hailShower
+	18	:	hail
+	19	:	shower
+	20	:	lightSnow
+	21	:	snow
+	22	:	heavySnowShower
+	23	:	heavySnow
+	24	:	thunderShower
+	25	:	thunder


## Appendix 4 : Suitable values codes for `roadSurface` attribute

+ 1:	Dry;
+ 2:	Wet;
+ 3:	Slippery;
+ 4:	frozen;
+ 5:	Snowcapped;


## Appendix 5 : Suitable values codes for `roadPaving` attribute

+ 1:	Paved road;
+ 2:	Rough paved road;
+ 3:	Unpaved road;


## Appendix 6 : Suitable values codes for `accidentLocation` attribute

+ 0:	Regional within the urban area
+ 1:	Urban road in the town
+ 2:	Provincial road within the town
+ 3:	State road within the village
+ 4:	Extra-urban road
+ 5:	Provincial
+ 6:	State road
+ 7:	Highway
+ 8:	Another way
+ 9:	Regional road


## Appendix 7 : Suitable values codes for `roadIntersection` attribute

+ 1:	Crossroad;
+ 2:	Roundabout;
+ 3:	Reported intersection;
+ 4:	Intersection with traffic light;
+ 5:	Intersection not reported;
+ 6:	Rail crossing;
+ 7:	Straight;
+ 8:	Curve;
+ 9:	Bump, bottleneck;
+ 10:	Slope;
+ 11:	Illuminated gallery;
+ 12:	Unlit gallery;



## Appendix 8 : Suitable values codes for `roadTrunk` attribute

+ 1:	Road branch;
+ 2:	Secondary branch;
+ 3:	Minor branch;
+ 4:	Junction branch;
+ 5:	Road junction;
+ 6:	Motorway left lane;
+ 7:	Highway carriageway right;
+ 8:	Motorway junction entrance;
+ 9:	Highway exit junction;
+ 10:	Highway junction trunk;
+ 11:	Highway station;
+ 12:	Other cases;
+ 15:	Extra urban road;



## Appendix 9 : Suitable values codes for `roadSign` attribute

+ 1:	Absent;
+ 2:	Vertical;
+ 3:	Horizontal;
+ 4:	Vertical and horizontal;
+ 5:	Temporary by construction site;



## Appendix 10 : Suitable values codes for `vehiclesInvolved` and `weakestSubject` attributes
The following values are defined by _VehicleTypeEnum_ or _VehicleTypeEnum2_ [DATEX 2 version 2.3](http://d2docs.ndwcloud.nu/_static/umlmodel/v2.3/index.htm) or _pedestrian_

+	0	:	pedestrian
+	1	:	bicycle
+	2	:	agriculturalVehicle
+	3	:	bus
+	4	:	minibus
+	5	:	car
+	6	:	caravan
+	7	:	tram
+	8	:	tanker
+	9	:	carWithCaravan
+	10	:	carWithTrailer
+	11	:	lorry
+	12	:	moped
+	13	:	tanker
+	14	:	motorcycle
+	15	:	motorcycleWithSideCar
+	16	:	motorscooter
+	17	:	trailer
+	18	:	van
+	19	:	caravan
+	20	:	constructionOrMaintenanceVehicle
+	21	:	trolley
+	22	:	binTrolley
+	23	:	sweepingMachine
+	24	:	cleaningTrolley

