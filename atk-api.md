---
title: Analytic Toolkit REST API
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="analytic-toolkit-rest-api">Analytic Toolkit REST API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URLs:

* <a href="http://localhost:8080/v1">http://localhost:8080/v1</a>

 License: Apache License 2.0

<h1 id="analytic-toolkit-rest-api-estimator">estimator</h1>

## status

<a id="opIdstatus"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/estimator/status/summary \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/estimator/status/summary HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/estimator/status/summary',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/estimator/status/summary',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/estimator/status/summary',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/estimator/status/summary', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/estimator/status/summary");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/estimator/status/summary", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/estimator/status/details \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/estimator/status/details HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/estimator/status/details',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/estimator/status/details',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/estimator/status/details',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/estimator/status/details', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/estimator/status/details");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/estimator/status/details", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/estimator/status/details/{Id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/estimator/status/details/{Id} HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/estimator/status/details/{Id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/estimator/status/details/{Id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/estimator/status/details/{Id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/estimator/status/details/{Id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/estimator/status/details/{Id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/estimator/status/details/{Id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/estimator/params \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/estimator/params HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/estimator/params',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/estimator/params',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/estimator/params',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/estimator/params', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/estimator/params");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/estimator/params", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/v1/estimator/params \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/v1/estimator/params HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/estimator/params',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "P": 0,
  "D": 0,
  "Q": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/estimator/params',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/v1/estimator/params',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/v1/estimator/params', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/estimator/params");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/v1/estimator/params", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/estimator/threads \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/estimator/threads HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/estimator/threads',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/estimator/threads',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/estimator/threads',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/estimator/threads', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/estimator/threads");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/estimator/threads", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/v1/estimator/threads \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/v1/estimator/threads HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/estimator/threads',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '0';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/estimator/threads',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/v1/estimator/threads',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/v1/estimator/threads', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/estimator/threads");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/v1/estimator/threads", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/nodes \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/nodes HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/nodes',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/nodes',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/nodes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/nodes', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/nodes");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/nodes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/v1/nodes \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/v1/nodes HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/nodes',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/nodes',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/v1/nodes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/v1/nodes', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/nodes");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/v1/nodes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/nodes/{Id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/nodes/{Id} HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/nodes/{Id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/nodes/{Id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/nodes/{Id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/nodes/{Id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/nodes/{Id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/nodes/{Id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/v1/nodes/{Id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/v1/nodes/{Id} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/nodes/{Id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/nodes/{Id}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/v1/nodes/{Id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/v1/nodes/{Id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/nodes/{Id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/v1/nodes/{Id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/v1/nodes/{Id} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:8080/v1/nodes/{Id} HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/nodes/{Id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/nodes/{Id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:8080/v1/nodes/{Id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:8080/v1/nodes/{Id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/nodes/{Id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:8080/v1/nodes/{Id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/v1/nodes/{Id}/ignore \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/v1/nodes/{Id}/ignore HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/nodes/{Id}/ignore',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = 'true';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/nodes/{Id}/ignore',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/v1/nodes/{Id}/ignore',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/v1/nodes/{Id}/ignore', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/nodes/{Id}/ignore");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/v1/nodes/{Id}/ignore", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/use-cases \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/use-cases HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/use-cases',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/use-cases',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/use-cases',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/use-cases', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/use-cases");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/use-cases", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/v1/use-cases \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/v1/use-cases HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/use-cases',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/use-cases',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/v1/use-cases',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/v1/use-cases', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/use-cases");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/v1/use-cases", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/use-cases/{Id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/use-cases/{Id} HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/use-cases/{Id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/use-cases/{Id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/use-cases/{Id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/use-cases/{Id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/use-cases/{Id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/use-cases/{Id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/v1/use-cases/{Id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/v1/use-cases/{Id} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/use-cases/{Id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/use-cases/{Id}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/v1/use-cases/{Id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/v1/use-cases/{Id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/use-cases/{Id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/v1/use-cases/{Id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/v1/use-cases/{Id} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:8080/v1/use-cases/{Id} HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/use-cases/{Id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/use-cases/{Id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:8080/v1/use-cases/{Id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:8080/v1/use-cases/{Id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/use-cases/{Id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:8080/v1/use-cases/{Id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/history \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/history HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/history',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/history',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/history',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/history', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/history");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/history", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/history/{Id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/history/{Id} HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/history/{Id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/history/{Id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/history/{Id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/history/{Id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/history/{Id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/history/{Id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/v1/history/realign \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/v1/history/realign HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/history/realign',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/history/realign',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/v1/history/realign',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/v1/history/realign', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/history/realign");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/v1/history/realign", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/history/realign/{Id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/history/realign/{Id} HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/history/realign/{Id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/history/realign/{Id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/history/realign/{Id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/history/realign/{Id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/history/realign/{Id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/history/realign/{Id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/history/ts-min \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/history/ts-min HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/history/ts-min',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/history/ts-min',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/history/ts-min',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/history/ts-min', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/history/ts-min");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/history/ts-min", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/history/ts-max \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/history/ts-max HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/history/ts-max',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/history/ts-max',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/history/ts-max',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/history/ts-max', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/history/ts-max");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/history/ts-max", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/history/autorefresh \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/history/autorefresh HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/history/autorefresh',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/history/autorefresh',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/history/autorefresh',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/history/autorefresh', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/history/autorefresh");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/history/autorefresh", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/v1/version \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/v1/version HTTP/1.1
Host: localhost:8080
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/v1/version',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/v1/version',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/v1/version',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/v1/version', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/v1/version");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/v1/version", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

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

