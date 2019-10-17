# NGSI-LD Guide 

This document explains how the SynchroniCity Data Models can easily be migrated
to NGSI-LD. There is a great 
[tutorial on NGSI-LD](https://github.com/FIWARE/tutorials.Linked-Data) 
a [Howto](https://github.com/FIWARE/dataModels/blob/master/specs/howto.md) 
and [FAQ](https://github.com/FIWARE/dataModels/blob/master/specs/ngsi-ld_faq.md). 


## Generating the JSON-LD @context 

The JSON-LD @context contains the the mapping between terms (short hand strings)
and URIs (Fully Qualified Names). The JSON-LD @context can be generated 
using this [Python script](https://github.com/FIWARE/dataModels/blob/master/tools/ldcontext_generator.py) as follows

```
python3 ldcontext_generator.py -f <folder> -u https://uri.synchronicity-iot.eu/ns/data-models
```

`<folder>` must be the root folder of the SynchroniCity Data Models. 

Such Python script processes all the JSON Schemas and will generate a new 
JSON-LD @context including all the terms defined in those schemas 
mapped to the URI `https://uri.synchronicity-iot.eu/ns/dataModels#<term>`

Note: SynchroniCity should consider hosting the content at such URI the same 
way as FIWARE does at [https://uri.fiware.org/ns/data-models](https://uri.fiware.org/ns/data-models) 

The SynchroniCity JSON-LD @context has been stored at 
[https://gitlab.com/synchronicity-iot/synchronicity-data-models/raw/master/context.jsonld](https://gitlab.com/synchronicity-iot/synchronicity-data-models/raw/master/context.jsonld) 
and can be referenced from NGSI-LD example content. Please note that ideally 
SynchroniCity should store such LD @context in a proper hosting space and it 
should be served using the MIME type `application/ld+json`. 

## Generating examples in NGSI-LD

There is a 
[Python script](https://github.com/FIWARE/data-models/blob/master/tools/normalized2LD.py) 
that facilitates the transformation from an NGSIv2 JSON representation 
to an NGSI-LD representation. 

```
python3 normalized2LD.py example-normalized.json example-normalized-ld.jsonld https://gitlab.com/synchronicity-iot/synchronicity-data-models/raw/master/context.jsonld
```

Please observe that the URI where the SynchroniCity @context is stored is provided. 

All the NGSI-LD example files shall be named `example-normalized-ld.jsonld`. As
a way of example, the [Store](https://gitlab.com/synchronicity-iot/synchronicity-data-models/tree/master/PointOfInterest/Store) 
Data Model has been updated with NGSI-LD content. 

## NGSI-LD implementations

-   Orion-LD: [https://github.com/Fiware/context.Orion-LD](https://github.com/Fiware/context.Orion-LD)
-   Scorpio:  [https://github.com/ScorpioBroker/ScorpioBroker](https://github.com/ScorpioBroker/ScorpioBroker)
-   Djane:    [https://github.com/sensinov/djane/](https://github.com/sensinov/djane/)

## Additional Resources

Generic JSON Schemas for NGSI-LD content are provided by [ETSI](https://forge.etsi.org/rep/NGSI-LD/NGSI-LD/tree/master/schema)