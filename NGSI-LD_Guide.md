# NGSI-LD Guide 

This document explains how the SynchroniCity Data Models can easily be migrated
to NGSI-LD. There is a great [tutorial on NGSI-LD]() 
a [Howto]() and [FAQ](). 


## Generating the JSON-LD @context 

The JSON-LD @context contains the the mapping between terms (short hand strings)
and URIs (Fully Qualified Names). The JSON-LD @context can be generated 
using this [Python script]() as follows

```
python3 ldcontext_generator.py -f <folder> -u https://uri.synchronicity-iot.eu/ns/dataModels
```

`<folder>` can be root folder of the SynchroniCity Data Models. 

Such Python script processes all the JSON Schemas and will generate a new 
JSON-LD @context including all the terms defined in those schemas 
mapped to the URI `https://uri.synchronicity-iot.eu/ns/dataModels#<term>`

Note: SynchroniCity shall consider hosting information at such URI the same 
way as FIWARE does at [https://uri.fiware.org/ns/dataModels](https://uri.fiware.org/ns/dataModels) 

The SynchroniCity JSON-LD @context has been stored at []() and can be referenced
from NGSI-LD examplem content. 

## Generating examples in NGSI-LD

There is a [Python script](https://github.com/FIWARE/dataModels/blob/master/tools/normalized2LD.py) 
that facilitates the transformation from an NGSIv2 JSON representation to an NGSI-LD representation. 

```
python3 normalized2LD.py example-normalized.json example-normalized-ld.jsonld https://gitlab.
```

Please observe that the URI where the SynchroniCity @context is stored is provided. 

All the NGSI-LD example files shall be named `example-normalized-ld.jsonld`. As
a way of example, the [Store]() Data Model has been updated with NGSI-LD content. 

## Additional Resources

Generic JSON Schemas for NGSI-LD content are provided by [ETSI]()