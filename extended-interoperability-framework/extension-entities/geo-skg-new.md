---
title: New entity
parent: Interoperability framework
ancestor: Geolocation & timestamp extension
layout: default
nav_order: 3
# nav_exclude: true
---

# New entity introduced by GEO-SKG

{: .important }
To prevent possible clashes with other extensions, each extension is assigned a unique prefix (e.g., the acronym you provided upon requesting an extension) that you need to prepend when defining new properties and relations for core entities. For this extension, the acronym is `geo_skg`.

Describe here the properties and relations of a new entity introduced by this extension.
Like any other entity in the SKG-IF, this one has to have some basic mandatory fields for identification and for its type.


## Properties

### `local_identifier`
*String* (mandatory): Unique code identifying the entity in the SKG (if any, otherwise "stateless identifier").

{: .highlight }
**Suggestion:** Use a URL as a string to make this entity dereferenceable on the Web. For additional information, see the [section 'Local identifiers of entities' of the Interoperability Framework](/interoperability-framework/#local-identifiers-of-entities).

```json
    "local_identifier": "https://..."
```

### `identifiers`
*List* (recommended): Objects representing external identifiers for the entity. 

Each identifier is structured as follows:
- `scheme` *String* (mandatory): The scheme for the external identifier.
- `value` *String* (mandatory): The external identifier.

**Note:** the current version of SKG-IF includes the following types of identifiers (to be specified as strings in the field “scheme”): `orcid`, `handle`, `url`, ...

```json
    "identifiers": [
        {
            "scheme": "...",
            "value": "..."
        }           
    ]
```

### `entity_type`
*String* (mandatory): Field stating what kind of entity is being serialised. Needed for parsing purposes; fixed to `geo_skg_new`. Please notice that you need to prepend the assigned `geo_skg` prefix to your type in order to prevent possible clashes with other extensions.

```json
    "entity_type": "geo_skg_new"
```

### `geo_skg_property`
*String* (mandatory): a description.

```json
    "geo_skg_property": ...
```

----
