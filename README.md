Given input:

```
{
        "id": "urn:ngsi-v2:cot-imec-be:WaterQualityObserved:vmm-iow-46GLMKCC78gWVCnXG9UxKM",
        "type": "https://uri.fiware.org/ns/data-models#WaterQualityObserved",
        "NO3": [
            {
                "type": "Property",
                "value": 213,
                "instanceId": "urn:ngsi-ld:4825506e-7825-4259-b9af-92e25d625ee9",
                "observedAt": "2022-06-28T10:14:17.000Z",
                "unitCode": "Q30"
            },
            {
                "type": "Property",
                "value": 212,
                "instanceId": "urn:ngsi-ld:7af8064e-0398-4c6a-ae15-1c3b187c52c9",
                "observedAt": "2022-06-28T10:09:16.000Z",
                "unitCode": "Q30"
            }
        ],
        "https://uri.fiware.org/ns/data-models#batteryLevel": [
            {
                "type": "Property",
                "rawValue": {
                    "type": "Property",
                    "value": {}
                },
                "statusCode": {
                    "type": "Property",
                    "value": 1
                },
                "timestamp": {
                    "type": "Property",
                    "value": "2022-06-28T10:22:07.000Z"
                },
                "value": 0.66,
                "instanceId": "urn:ngsi-ld:1916e19b-02c0-4310-b9c4-132fee192649",
                "observedAt": "2022-06-28T10:22:07.000Z"
            },
            {
                "type": "Property",
                "rawValue": {
                    "type": "Property",
                    "value": {}
                },
                "statusCode": {
                    "type": "Property",
                    "value": 1
                },
                "timestamp": {
                    "type": "Property",
                    "value": "2022-06-28T09:22:07.000Z"
                },
                "value": 0.66,
                "instanceId": "urn:ngsi-ld:cc4b5f7b-240c-494a-a0e6-1cfd2fdf09cd",
                "observedAt": "2022-06-28T10:09:16.000Z"
            }
        ],
        "@context": [
            "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context-v1.3.jsonld"
        ]
    }
```

We see three distinct timestamps (2022-06-28T10:09:16.000Z, 2022-06-28T10:22:07.000Z, 2022-06-28T10:14:17.000Z),
so we create three members:

Member at 2022-06-28T10:09:16.000Z:
```
[{
        "id": "urn:ngsi-v2:cot-imec-be:WaterQualityObserved:vmm-iow-46GLMKCC78gWVCnXG9UxKM/2022-06-28T10:22:07.000Z",
        "type": "https://uri.fiware.org/ns/data-models#WaterQualityObserved",
        "dcterms:isVersionOf": "urn:ngsi-v2:cot-imec-be:WaterQualityObserved:vmm-iow-46GLMKCC78gWVCnXG9UxKM",
        "NO3": [
            {
                "type": "Property",
                "value": 212,
                "instanceId": "urn:ngsi-ld:7af8064e-0398-4c6a-ae15-1c3b187c52c9",
                "observedAt": "2022-06-28T10:09:16.000Z",
                "unitCode": "Q30"
            }
        ],
        "https://uri.fiware.org/ns/data-models#batteryLevel": [
            {
                "type": "Property",
                "rawValue": {
                    "type": "Property",
                    "value": {}
                },
                "statusCode": {
                    "type": "Property",
                    "value": 1
                },
                "timestamp": {
                    "type": "Property",
                    "value": "2022-06-28T09:22:07.000Z"
                },
                "value": 0.66,
                "instanceId": "urn:ngsi-ld:cc4b5f7b-240c-494a-a0e6-1cfd2fdf09cd",
                "observedAt": "2022-06-28T10:09:16.000Z"
            }
        ],
        "@context": [
            {
              "dcterms:isVersionOf": "http://purl.org/dc/terms/isVersionOf"
            },
            "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context-v1.3.jsonld"
        ]
    }
```

Member at 2022-06-28T10:14:17.000Z:
```
[{
        "id": "urn:ngsi-v2:cot-imec-be:WaterQualityObserved:vmm-iow-46GLMKCC78gWVCnXG9UxKM/2022-06-28T10:14:17.000Z",
        "type": "https://uri.fiware.org/ns/data-models#WaterQualityObserved",
        "dcterms:isVersionOf": "urn:ngsi-v2:cot-imec-be:WaterQualityObserved:vmm-iow-46GLMKCC78gWVCnXG9UxKM",
        "NO3": [
            {
                "type": "Property",
                "value": 213,
                "instanceId": "urn:ngsi-ld:4825506e-7825-4259-b9af-92e25d625ee9",
                "observedAt": "2022-06-28T10:14:17.000Z",
                "unitCode": "Q30"
            }
        ]
        "@context": [
            {
              "dcterms:isVersionOf": "http://purl.org/dc/terms/isVersionOf"
            },
            "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context-v1.3.jsonld"
        ]
    }
```

Member at 2022-06-28T10:22:07.000Z:
```
[{
        "id": "urn:ngsi-v2:cot-imec-be:WaterQualityObserved:vmm-iow-46GLMKCC78gWVCnXG9UxKM/2022-06-28T10:22:07.000Z",
        "type": "https://uri.fiware.org/ns/data-models#WaterQualityObserved",
        "dcterms:isVersionOf": "urn:ngsi-v2:cot-imec-be:WaterQualityObserved:vmm-iow-46GLMKCC78gWVCnXG9UxKM",
        "https://uri.fiware.org/ns/data-models#batteryLevel": [
            {
                "type": "Property",
                "rawValue": {
                    "type": "Property",
                    "value": {}
                },
                "statusCode": {
                    "type": "Property",
                    "value": 1
                },
                "timestamp": {
                    "type": "Property",
                    "value": "2022-06-28T10:22:07.000Z"
                },
                "value": 0.66,
                "instanceId": "urn:ngsi-ld:1916e19b-02c0-4310-b9c4-132fee192649",
                "observedAt": "2022-06-28T10:22:07.000Z"
            }
        ],
        "@context": [
            {
              "dcterms:isVersionOf": "http://purl.org/dc/terms/isVersionOf"
            },
            "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context-v1.3.jsonld"
        ]
    }
```
