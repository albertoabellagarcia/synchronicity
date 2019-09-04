# NGSI-LD Guide 

This document explains how the SynchroniCity Data Models can easily be migrated
to NGSI-LD. There is a great [tutorial on NGSI-LD]() 
a [Howto]() and [FAQ](). 


## Generating the JSON-LD @context 

The JSON-LD @context contains the the mapping between terms (short hand strings)
and URIs (Fully Qualified Names). The JSON-LD @context can be generated 
using this [Python script]() as follows

```
python3 ldcontext_generator.py -f <folder> -u https://uri.synchronicity-iot.eu/dataModels#
```

Such Python script processes all the JSON Schemas and will generate a new 
JSON-LD @context including all the terms defined in those schemas 
mapped to the URI ` https://uri.synchronicity-iot.eu/dataModels#`

The SynchroniCity JSON-LD @context has been stored at []() and can be referenced
from NGSI-LD content. 

## Generating examples in NGSI-LD

There is a [Python script]() that facilitates the transformation betweeen a 
NGSIv2 JSON representation and an NGSI-LD representation. 

```
python3 
```