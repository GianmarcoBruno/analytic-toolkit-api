<h1 id="analytic-toolkit-rest-api">Analytic Toolkit REST API v1.0.0</h1>

> Scroll down for example requests and responses.

Base URLs:

* <a href="http://localhost:8080/v1">http://localhost:8080/v1</a>

 License: Apache License 2.0

<h1 id="analytic-toolkit-rest-api-estimator">estimator</h1>

## status

<a id="opIdstatus"></a>

`GET /estimator/status/summary`

*Return the current status computed from all estimators*

> Example responses

> 200 Response

```json
{
  "timeslot": 0,
  "status": "BaU"
}
```

<h3 id="status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorSummary](#schemaestimatorsummary)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## statusDetails

<a id="opIdstatusDetails"></a>

`GET /estimator/status/details`

*Detailed status of all estimators*

<h3 id="statusdetails-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the estimator to retrieve|

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "name": "string",
    "tag": "string"
  }
]
```

<h3 id="statusdetails-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorDetailList](#schemaestimatordetaillist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## statusDetailsById

<a id="opIdstatusDetailsById"></a>

`GET /estimator/status/details/{Id}`

*Detailed state for a specific estimator*

<h3 id="statusdetailsbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the estimator to retrieve|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "name": "string",
  "tag": "string"
}
```

<h3 id="statusdetailsbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorDetail](#schemaestimatordetail)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getEstimatorParams

<a id="opIdgetEstimatorParams"></a>

`GET /estimator/params`

*Get the ARIMA parameters used by the estimators*

> Example responses

> 200 Response

```json
{
  "id": 0,
  "name": "string",
  "tag": "string"
}
```

<h3 id="getestimatorparams-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorDetail](#schemaestimatordetail)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## putEstimatorParams

<a id="opIdputEstimatorParams"></a>

`PUT /estimator/params`

*Update the ARIMA parameters used by the estimators*

> Body parameter

```json
{
  "P": 0,
  "D": 0,
  "Q": 0
}
```

<h3 id="putestimatorparams-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ArimaParameters](#schemaarimaparameters)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "name": "string",
  "tag": "string"
}
```

<h3 id="putestimatorparams-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorDetail](#schemaestimatordetail)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getEstimatorThreads

<a id="opIdgetEstimatorThreads"></a>

`GET /estimator/threads`

*Get the number of threads used by ARIMA estimators*

> Example responses

> 200 Response

```json
0
```

<h3 id="getestimatorthreads-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|integer|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## putEstimatorThreads

<a id="opIdputEstimatorThreads"></a>

`PUT /estimator/threads`

*Update the number of threads used by ARIMA estimators*

> Body parameter

```json
0
```

<h3 id="putestimatorthreads-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|integer(int32)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "name": "string",
  "tag": "string"
}
```

<h3 id="putestimatorthreads-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorDetail](#schemaestimatordetail)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-nodes">nodes</h1>

## getNodes

<a id="opIdgetNodes"></a>

`GET /nodes`

*Return list of nodes currently managed*

> Example responses

> 200 Response

```json
[
  {
    "node-id": "string",
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": "string"
  }
]
```

<h3 id="getnodes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeList](#schemanodelist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## postNode

<a id="opIdpostNode"></a>

`POST /nodes`

*Manage a new node*

> Body parameter

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="postnode-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Node](#schemanode)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
[
  {
    "node-id": "string",
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": "string"
  }
]
```

<h3 id="postnode-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeList](#schemanodelist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getNodeById

<a id="opIdgetNodeById"></a>

`GET /nodes/{Id}`

*Detailed information for a specific node*

<h3 id="getnodebyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the node to retrieve|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="getnodebyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## putNodeById

<a id="opIdputNodeById"></a>

`PUT /nodes/{Id}`

*Update information for a specific node {Id}*

> Body parameter

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="putnodebyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the node to update|
|body|body|[Node](#schemanode)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="putnodebyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## deleteNodeById

<a id="opIddeleteNodeById"></a>

`DELETE /nodes/{Id}`

*Remove node {id} from the managed nodes*

<h3 id="deletenodebyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the node to delete|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="deletenodebyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## postNodeIgnore

<a id="opIdpostNodeIgnore"></a>

`POST /nodes/{Id}/ignore`

*If set to true, keep node {id} tracked but do not consider for the estimation.*

> Body parameter

```json
true
```

<h3 id="postnodeignore-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the node|
|body|body|boolean|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
[
  {
    "node-id": "string",
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": "string"
  }
]
```

<h3 id="postnodeignore-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeList](#schemanodelist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-use-cases">use-cases</h1>

## getUsecases

<a id="opIdgetUsecases"></a>

`GET /use-cases`

*Return list of use-cases currently managed*

> Example responses

> 200 Response

```json
[
  {
    "node-id": "string",
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": "string"
  }
]
```

<h3 id="getusecases-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeList](#schemanodelist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## postUseCase

<a id="opIdpostUseCase"></a>

`POST /use-cases`

*Manage a new use-case*

> Body parameter

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="postusecase-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Node](#schemanode)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
[
  {
    "node-id": "string",
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": "string"
  }
]
```

<h3 id="postusecase-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeList](#schemanodelist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getUseCaseById

<a id="opIdgetUseCaseById"></a>

`GET /use-cases/{Id}`

*Detailed information for a specific use-case*

<h3 id="getusecasebyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the use-case to retrieve|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="getusecasebyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## putUseCase

<a id="opIdputUseCase"></a>

`PUT /use-cases/{Id}`

*Update information for a specific use-case {Id}*

> Body parameter

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="putusecase-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the use-case to update|
|body|body|[Node](#schemanode)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="putusecase-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## deleteUseCaseById

<a id="opIddeleteUseCaseById"></a>

`DELETE /use-cases/{Id}`

*Remove use-case {id} from the managed use-cases*

<h3 id="deleteusecasebyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the use-case to delete|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="deleteusecasebyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-history">history</h1>

## getHistory

<a id="opIdgetHistory"></a>

`GET /history`

*Return history of all nodes currently managed*

> Example responses

> 200 Response

```json
"string"
```

<h3 id="gethistory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|string|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getHistoryById

<a id="opIdgetHistoryById"></a>

`GET /history/{Id}`

*Return history for the given node Id*

<h3 id="gethistorybyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the node to retrieve|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="gethistorybyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## postHistoryRealign

<a id="opIdpostHistoryRealign"></a>

`POST /history/realign`

*Reread history from input data, adapt and store them in local history for all nodes*

> Example responses

> 200 Response

```json
"string"
```

<h3 id="posthistoryrealign-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|string|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## postHistoryRealignById

<a id="opIdpostHistoryRealignById"></a>

`GET /history/realign/{Id}`

*Reread history from input data, adapt and store them in local history for a given node Id*

<h3 id="posthistoryrealignbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The Id of the node to realign history|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="posthistoryrealignbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getTsMin

<a id="opIdgetTsMin"></a>

`GET /history/ts-min`

*Return minimum number of timeslots to populate local history*

> Example responses

> 200 Response

```json
0
```

<h3 id="gettsmin-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|integer|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getTsMax

<a id="opIdgetTsMax"></a>

`GET /history/ts-max`

*Return maximum number of timeslots to populate local history*

> Example responses

> 200 Response

```json
0
```

<h3 id="gettsmax-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|integer|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getAutorefresh

<a id="opIdgetAutorefresh"></a>

`GET /history/autorefresh`

*Return the time interval between consecutive data captures*

> Example responses

> 200 Response

```json
0
```

<h3 id="getautorefresh-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|integer|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-version">version</h1>

## getVersion

<a id="opIdgetVersion"></a>

`GET /version`

*Return the ATk software version*

> Example responses

> 200 Response

```json
"string"
```

<h3 id="getversion-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|string|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSestimatordetail">EstimatorDetail</h2>

<a id="schemaestimatordetail"></a>

```json
{
  "id": 0,
  "name": "string",
  "tag": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|true|none|none|
|name|string|false|none|none|
|tag|string|false|none|none|

<h2 id="tocSestimatordetaillist">EstimatorDetailList</h2>

<a id="schemaestimatordetaillist"></a>

```json
[
  {
    "id": 0,
    "name": "string",
    "tag": "string"
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[EstimatorDetail](#schemaestimatordetail)]|false|none|none|

<h2 id="tocSnodelist">NodeList</h2>

<a id="schemanodelist"></a>

```json
[
  {
    "node-id": "string",
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": "string"
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Node](#schemanode)]|false|none|none|

<h2 id="tocSnode">Node</h2>

<a id="schemanode"></a>

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|node-id|string|true|none|none|
|tags|[string]|false|none|none|
|tracked|boolean|false|none|none|
|use-case|string|false|none|none|

<h2 id="tocSusecaselist">UseCaseList</h2>

<a id="schemausecaselist"></a>

```json
[
  {
    "uc-id": "string",
    "tags": [
      "string"
    ],
    "adaptation": "string",
    "bau": {
      "samples": 0,
      "threshold": 0,
      "threshold-type": "string"
    },
    "warning": {
      "samples": 0,
      "hysteresis": "string"
    }
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[UseCase](#schemausecase)]|false|none|none|

<h2 id="tocSusecase">UseCase</h2>

<a id="schemausecase"></a>

```json
{
  "uc-id": "string",
  "tags": [
    "string"
  ],
  "adaptation": "string",
  "bau": {
    "samples": 0,
    "threshold": 0,
    "threshold-type": "string"
  },
  "warning": {
    "samples": 0,
    "hysteresis": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uc-id|string|true|none|none|
|tags|[string]|false|none|none|
|adaptation|string|false|none|none|
|bau|object|false|none|none|
|» samples|integer(int32)|false|none|none|
|» threshold|integer(int32)|false|none|none|
|» threshold-type|string|false|none|none|
|warning|object|false|none|none|
|» samples|integer(int32)|false|none|none|
|» hysteresis|string|false|none|none|

<h2 id="tocSestimatorsummary">EstimatorSummary</h2>

<a id="schemaestimatorsummary"></a>

```json
{
  "timeslot": 0,
  "status": "BaU"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|timeslot|integer(int64)|false|none|none|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|BaU|
|status|Warn|
|status|Alarm|
|status|Undefined|

<h2 id="tocSarimaparameters">ArimaParameters</h2>

<a id="schemaarimaparameters"></a>

```json
{
  "P": 0,
  "D": 0,
  "Q": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|P|integer(int64)|false|none|none|
|D|integer(int64)|false|none|none|
|Q|integer(int64)|false|none|none|

<h2 id="tocSerror">Error</h2>

<a id="schemaerror"></a>

```json
{
  "code": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer(int32)|true|none|none|
|message|string|true|none|none|

