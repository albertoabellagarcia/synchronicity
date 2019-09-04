# Store

## Description

This entity Type models stores/shops in the city. The model is based on the one defined by [Schema.org](https://schema.org/Store). In particular, the model contains a subset of the properties defined in the mentioned link, and a list of store categories, that can be afterwards specialized as concrete Types (see [https://schema.org/Store](https://schema.org/Store)). 

## Data Model

+ `id`: Entity Id
  + It shall be `urn:ngsi-ld:Store:<identifier>`

+ `type`: Entity Type
  + It shall be equal to `Store`

+ `source` : A sequence of characters giving the source of the entity data.
  + Attribute type: Text or URL
  + Optional

+ `dataProvider` : Specifies the URL to information about the provider of this
  information
  + Attribute type: URL
  + Optional

+ `dateCreated` : Entity's creation timestamp.
  + Attribute type: [DateTime](https://schema.org/DateTime)
  + Read-Only. Automatically generated.

+ `dateModified` : Last update timestamp of this Entity.
  + Attribute type: [DateTime](https://schema.org/DateTime)
  + Read-Only. Automatically generated.  

+ `name`: Name of this store.
  + Attribute type: [Text](https://schema.org/Text)
  + Mandatory.  

+ `description` : Description of this store.
  + Normative References: [https://schema.org/description](https://schema.org/description)
  + Mandatory.

+ `address` : Address of the store.
  + Normative References: [https://schema.org/address](https://schema.org/address)
  + Mandatory if `location` is not present.

+ `location`: Location of this store represented by a GeoJSON geometry,
    usually a `Point` or a `Polygon`.
  + Attribute type: `geo:json`.
  + Normative References: [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
  + Mandatory if `address` is not defined.  

+ `image`: An image of this store.
  + Attribute type: [URL](https://schema.org/URL)
  + Optional  

+ `currenciesAccepted` : Currencies accepted in this store. Use standard formats  [ISO 4217](https://es.wikipedia.org/wiki/ISO_4217) currency format (e.g. USD, EUR)
  + Attribute type: Array of [Text](https://schema.org/Text)
  + Mandatory.

+ `paymentAccepted`: Payment method accepted in this store.
  + Attribute type: Array of [Text](https://schema.org/Text)
  + Optional.  

+ `openingHoursSpecification`:  Opening hours specification for this store.
  + Normative References: [http://schema.org/openingHoursSpecification](http://schema.org/openingHoursSpecification)
  + Attribute type: List of OpeningHoursSpecification
  + Optional

+ `logo`: An associated logo for this store.
  + Attribute type: [URL](https://schema.org/URL)
  + Optional

+ `telephone`: The telephone number of this store.
  + Attribute type: [Text](https://schema.org/Text)
  + Optional.

+ `email`: The email address of this store.
  + Attribute type: [Text](https://schema.org/Text)
  + Optional.

+ `url`: Website with information about the store.
  + Attribute type: [URL](https://schema.org/URL)
  + Optional.  

+ `category`: Category of the store  
  + Attribute type: [Text](https://schema.org/Text)
  + Allowed values: `AutoPartsStore`, `BikeStore`, `BookStore`, `ClothingStore`, `ComputerStore`, `ConvenienceStore`, `DepartmentStore`, `ElectronicsStore`, `Florist`, `FurnitureStore`, `GardenStore`, `GroceryStore`, `HardwareStore`, `HobbyShop`, `HomeGoodsStore`, `JewelryStore`, `LiquorStore`, `MensClothingStore`, `MobilePhoneStore`, `MovieRentalStore`, `MusicStore`, `OfficeEquipmentStore`, `OutletStore`, `PawnShop`, `PetStore`, `ShoeStore`, `SportingGoodsStore`, `TireShop`, `ToyStore`, `WholesaleStore`.
  + Optional

## Examples

### Normalized Example

Normalized NGSI response 

```json
{
  "id": "urn:ngsi-ld:Store:santander:COM4111",
  "type": "Store",
  "dateModified": {
    "type": "DateTime",
    "value": "2018-06-01T11:19:54.00Z"
  },
  "name": {
    "type": "Text",
    "value": "MARTA KAUFMANN"
  },
  "description": {
    "type": "Text",
    "value": "Cosmetica natural fabricada en Santander."
  },
  "location": {
    "type": "geo:json",
    "value": {
      "type": "Point",
      "coordinates": [-3.8077562, 43.4628255]
    }
  },  
  "image": {
    "type": "Text",
    "value": "http://www.comerciosantander.com/imagenes/Comercios/124F214A-CE55-5A33-A77D-679C0F848FFC.jpg/resize/50/100/"
  },
  "currenciesAccepted": {
    "type": "StructuredValue",
    "value": ["EUR"]
  }
}
```
### key-value pairs Example

Sample uses simplified representation for data consumers `?options=keyValues`

```json
{
  "id": "urn:ngsi-ld:Store:santander:COM4111",
  "type": "Store",
  "dateModified": "2018-06-01T11:19:54.00Z",
  "name": "MARTA KAUFMANN",
  "description": "Cosmetica natural fabricada en Santander.",
  "location": {
    "type": "Point",
    "coordinates": [-3.8077562, 43.4628255]
  },
  "image": "http://www.comerciosantander.com/imagenes/Comercios/124F214A-CE55-5A33-A77D-679C0F848FFC.jpg/resize/50/100/",
  "currenciesAccepted": ["EUR"]
}
```

### LD Example

Sample uses the NGSI-LD representation. 


```json
{
    "id": "urn:ngsi-ld:Store:santander:COM4111",
    "type": "Store",
    "modifiedAt": "2018-06-01T11:19:54.00Z",
    "name": {
        "type": "Property",
        "value": "MARTA KAUFMANN"
    },
    "description": {
        "type": "Property",
        "value": "Cosmetica natural fabricada en Santander."
    },
    "location": {
        "type": "GeoProperty",
        "value": {
            "type": "Point",
            "coordinates": [
                -3.8077562,
                43.4628255
            ]
        }
    },
    "image": {
        "type": "Property",
        "value": "http://www.comerciosantander.com/imagenes/Comercios/124F214A-CE55-5A33-A77D-679C0F848FFC.jpg/resize/50/100/"
    },
    "currenciesAccepted": {
        "type": "Property",
        "value": [
            "EUR"
        ]
    },
    "@context": [
        "https://example.org/context.jsonld",
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"
    ]
}
```

## Open issues