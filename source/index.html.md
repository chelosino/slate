---
title: API Reference

language_tabs:
  - URLs

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Los Cuates del Tequila API! You can use our API to access Los Cuates del Tequila API endpoints, which can get information on various products in our database.

You can view code examples in the dark area to the right.

# Authentication

> To authorize, use this code:

```URLs
Autenticameeeee
```


> Make sure to replace `cuatesKey` with your API key.

Los Cuates del Tequila uses API keys to allow access to the API. You can register a new Los Cuates del Tequila API key at our [developer portal](http://example.com/developers).

Los Cuates del Tequila expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: cuatesKey`

<aside class="notice">
You must replace <code>cuatesKey</code> with your personal API key.
</aside>

# Consultas REST


## Consultar Stock del Producto por SKU

Este método recibe una SKU y retorna la cantidad de productos existentes

### HTTP Request

`GET http://integra10.ing.puc.cl/api/consultar/:sku`

### Query Parameters

Parameter | Description
--------- | -----------
:sku (int) | código de identificación del producto

### Query Responses

Parameter | Description
--------- |  -----------
stock (int) | Cantidad existente del producto consultado
:sku (int) | código de identificación del producto


## Recibir una Orden de Compra

Este método recibe una orden de compra y retorna su aceptación

### HTTP Request

`GET http://integra10.ing.puc.cl/api/oc/recibir/:idoc`

### Query Parameters

Parameter | Description
--------- | -----------
:idoc (string) | id de la Orden de Compra

### Query Responses

Parameter | Description
--------- |  -----------
aceptado (boolean) | True en el caso de ser aceptada
:idoc (string) | id de la Orden de Compra


## Recibir una Factura

Este método recibe una factura y retorna su validación

### HTTP Request

`GET http://integra10.ing.puc.cl/api/facturas/recibir/:idfactura`

### Query Parameters

Parameter | Description
--------- | -----------
:idfactura (string) | id de la Factura

### Query Responses

Parameter | Description
--------- |  -----------
validado (boolean) | True en el caso de ser validada
:idfactura (string) | id de la Factura


## Recibir una Transacción

Este método recibe una transacción y retorna su validación

### HTTP Request

`GET http://integra10.ing.puc.cl/api/pagos/recibir/:idtrx?idfactura=:idfactura`

### Query Parameters

Parameter | Description
--------- | -----------
:idtrx (string) | id de la Transacción
:idfactura (string) | id de la Factura

### Query Responses

Parameter | Description
--------- |  -----------
validado (boolean) | True en el caso de ser validada
:idtrx (string) | id de la Transacción
