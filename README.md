openapi: "3.0.0"
info:
  version: 1.0.0
  title: Analytic Toolkit REST API
  license:
    name: Apache License 2.0
servers:
  - url: http://localhost:8080/v1
paths:
  /estimator/status/summary:
    get:
      summary: Return the current status computed from all estimators
      operationId: get status
      tags:
        - estimator
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/EstimatorSummary"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
  /estimator/status/details:
    get:
      summary: Detailed status of all estimators
      operationId: get all status details
      tags:
        - estimator
      parameters:
        - name: Id
          in: path
          required: true
          description: The id of the estimator to retrieve
          schema:
            type: string
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/EstimatorDetailList"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
  /estimator/status/details/{Id}:
    get:
      summary: Detailed state for a specific estimator
      operationId: get status details by id
      tags:
        - estimator
      parameters:
        - name: Id
          in: path
          required: true
          description: The id of the estimator to retrieve
          schema:
            type: string
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/EstimatorDetail"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
  /estimator/params:
    get:
      summary: Get the ARIMA parameters used by the estimators
      operationId: get estimator paramaters
      tags:
        - estimator
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/EstimatorDetail"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
    put:
      summary: Update the ARIMA parameters used by the estimators
      operationId: update estimator parameters
      tags:
        - estimator
      requestBody:
        description: Optional description in *Markdown*
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/ArimaParameters'
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/EstimatorDetail"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
  /estimator/threads:
    get:
      summary: Get the number of threads used by ARIMA estimators
      operationId: get estimator threads
      tags:
        - estimator
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                type: integer
                format: int32
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
    put:
      summary: Update the number of threads used by ARIMA estimators
      operationId: update estimator threads
      tags:
        - estimator
      requestBody:
        description: Optional description in *Markdown*
        required: true
        content:
          application/json:
            schema:
              type: integer
              format: int32
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/EstimatorDetail"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
  /nodes:
    get:
      summary: Return list of nodes currently managed
      operationId: get all nodes
      tags:
        - nodes
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/NodeList"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"              
    post:
      summary: Manage a new node
      operationId: manage new node
      tags:
        - nodes
      requestBody:
        description: Optional description in *Markdown*
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Node'
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/NodeList"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"              
  /nodes/{Id}:
    get:
      summary: Detailed information for a specific node
      operationId: get node by id
      tags:
        - nodes
      parameters:
        - name: Id
          in: path
          required: true
          description: The id of the node to retrieve
          schema:
            type: string
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Node"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
    put:
      summary: Update information for a specific node {Id}
      operationId: update node by id
      tags:
        - nodes
      parameters:
        - name: Id
          in: path
          required: true
          description: The id of the node to update
          schema:
            type: string
      requestBody:
        description: Optional description in *Markdown*
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Node'
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Node"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
    delete:
      summary: Remove node {id} from the managed nodes
      operationId: delete node by id
      tags:
        - nodes
      parameters:
        - name: Id
          in: path
          required: true
          description: The id of the node to delete
          schema:
            type: string
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Node"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
  /nodes/{Id}/ignore:
    post:
      summary: If set to true, keep node {id} tracked but do not consider for the estimation.
      operationId: ignore a node
      tags:
        - nodes
      parameters:
        - name: Id
          in: path
          required: true
          description: The id of the node
          schema:
            type: string
      requestBody:
        description: Optional description in *Markdown*
        required: true
        content:
          application/json:
            schema:
              type: boolean
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/NodeList"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
  /use-cases:
    get:
      summary: Return list of use-cases currently managed
      operationId: get all use-cases
      tags:
        - use-cases
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/NodeList"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"              
    post:
      summary: Manage a new use-case
      operationId: manage a new use-case
      tags:
        - use-cases
      requestBody:
        description: Optional description in *Markdown*
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Node'
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/NodeList"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"              
  /use-cases/{Id}:
    get:
      summary: Detailed information for a specific use-case
      operationId: get use-case by id
      tags:
        - use-cases
      parameters:
        - name: Id
          in: path
          required: true
          description: The id of the use-case to retrieve
          schema:
            type: string
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Node"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
    put:
      summary: Update information for a specific use-case {Id}
      operationId: update use-case
      tags:
        - use-cases
      parameters:
        - name: Id
          in: path
          required: true
          description: The id of the use-case to update
          schema:
            type: string
      requestBody:
        description: Optional description in *Markdown*
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Node'
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Node"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
    delete:
      summary: Remove use-case {id} from the managed use-cases
      operationId: delete use-case
      tags:
        - use-cases
      parameters:
        - name: Id
          in: path
          required: true
          description: The id of the use-case to delete
          schema:
            type: string
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Node"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
  /history:
    get:
      summary: Return history of all nodes currently managed
      operationId: get history
      tags:
        - history
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                type: "string"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"              
  /history/{Id}:
    get:
      summary: Return history for the given node Id
      operationId: get history by id
      tags:
        - history
      parameters:
        - name: Id
          in: path
          required: true
          description: The id of the node to retrieve
          schema:
            type: string
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Node"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
  /history/realign:
    post:
      summary: Reread history from input data, adapt and store them in local history for all nodes
      operationId: realign history for all nodes
      tags:
        - history
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                type: "string"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"              
  /history/realign/{Id}:
    get:
      summary: Reread history from input data, adapt and store them in local history for a given node Id
      operationId: realing history for node id
      tags:
        - history
      parameters:
        - name: Id
          in: path
          required: true
          description: The Id of the node to realign history
          schema:
            type: string
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Node"
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"
  /history/ts-min:
    get:
      summary: Return minimum number of timeslots to populate local history
      operationId: get minimum timeslots
      tags:
        - history
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                type: integer
                format: int32
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"              
  /history/ts-max:
    get:
      summary: Return maximum number of timeslots to populate local history
      operationId: get maximum timeslots
      tags:
        - history
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                type: integer
                format: int32
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"              
  /history/autorefresh:
    get:
      summary: Return the time interval between consecutive data captures
      operationId: get autorefresh
      tags:
        - history
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                type: integer
                format: int32
        default:
          description: unexpected error
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Error"              
  /version:
    get:
      summary: Return the ATk software version
      operationId: get version
      tags:
        - version
      responses:
        '200':
          description: Expected response to a valid request
          content:
            application/json:
              schema:
                type: "string"
components:
  schemas:
    EstimatorDetail:
      type: object
      required:
        - id
      properties:
        id:
          type: integer
          format: int64
        name:
          type: string
        tag:
          type: string
    EstimatorDetailList:
      type: array
      items:
        $ref: '#/components/schemas/EstimatorDetail'
    NodeList:
      type: array
      items:
        $ref: '#/components/schemas/Node'
    Node:
      type: object
      required:
        - node-id
      properties:
        node-id:
          type: string
        tags:
          type: array
          items:
            type: string
        tracked:
          type: boolean
        use-case:
          type: string
    UseCaseList:
      type: array
      items:
        $ref: '#/components/schemas/UseCase'
    UseCase:
      type: object
      required:
        - uc-id
      properties:
        uc-id:
          type: string
        tags:
          type: array
          items:
            type: string
        adaptation:
          type: string
        bau:
          type: object
          properties:
            samples:
              type: integer
              format: int32
            threshold:
              type: integer
              format: int32
            threshold-type:
              type: string
        warning:
          type: object
          properties:
            samples:
              type: integer
              format: int32
            hysteresis:
              type: string
    EstimatorSummary:
      type: object
      properties:
        timeslot:
          type: "integer"
          format: int64
        status:
          type: "string"
          enum: [BaU, Warn, Alarm, Undefined]
    ArimaParameters:
      type: object
      properties:
        P:
          type: "integer"
          format: int64
        D:
          type: "integer"
          format: int64
        Q:
          type: "integer"
          format: int64
    Error:
      type: object
      required:
        - code
        - message
      properties:
        code:
          type: integer
          format: int32
        message:
          type: string
