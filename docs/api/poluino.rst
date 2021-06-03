***********
Poluino API
***********

The Poluino API provides programmatic access to read and write data.

Sending and Receiving Weather Data
==================================

GET /data/board/:token
----------------------

To get board data you need to make a GET call to the following url:
``https://api.poluino.xyz/data/board/:token``

Path Parameters

+-------+--------+------------------+----------+
| Field | Type   | Value            | Optional |
+=======+========+==========+=======+==========+
| token | String | Your Board Token | No       |
+-------+--------+------------------+----------+

Output

.. code-block:: json
 
  {
    "id": Your Board ID,
    "name": Your Board Name,
    "owner": Your User ID,
    "latitude": Your Board Latitude,
    "longitude": Your Board Longitude,
    "temperature": Your Latest Temperature,
    "pressure": Your Latest Pressure,
    "humidity": Your Latest Humidity,
    "public": 1 or 0,
    "verified": 1 or 0,
    "online": 1 or 0,
  }

GET /data/public_boards
-----------------------

To get user data you need to make a GET call to the following URL:
``https://api.poluino.xyz/data/public_boards``

Query String Parameters

+-------+--------+------------+----------+
| Field | Type   | Value      | Optional |
+=======+========+============+==========+
| name  | String | Board Name | No       |
+-------+--------+------------+----------+
| id    | String | Board ID   | No       |
+-------+--------+------------+----------+

Example

.. code-block:: bash

  curl https://api.poluino.xyz/data/public_boards

.. code-block:: bash

  curl https://api.poluino.xyz/data/public_boards?name=Pasig

.. code-block:: bash

  curl https://api.poluino.xyz/data/public_boards?id=1008

Output

.. code-block:: json

  {
    "id": Board ID,
    "name": Board Name,
    "latitude": Board Latitude,
    "longitude": Board Longitude,
    "temperature": Latest Temperature,
    "pressure": Latest Pressure,
    "humidity": Latest Humidity,
    "public": 1 or 0,
    "verified": 1 or 0,
    "online": 1 or 0,
  }

POST /data/update
-----------------

To get user data you need to make a GET call to the following url:
``https://api.poluino.xyz/data/update``

Headers

+-------------+--------+--------------+----------+
| Field       | Type   | Value        | Optional |
+=============+========+==============+==========+
| token       | String | Device Token | No       |
+-------------+--------+--------------+----------+

For Windows

.. code-block:: bash

  curl -H "Content-Type: application/json" -H "token: <BOARD TOKEN>" -X POST -d {\"temperature\":30,\"humidity\":78} https://api.poluino.xyz/data/update

For *nix or Mac OSX

.. code-block:: bash

  curl -H "Content-Type: application/json" -H "token: <BOARD TOKEN>" -X POST -d '{"temperature":30,"humidity":78}' https://api.poluino.xyz/data/update

Body Parameters

+-------------+--------+-------------+----------+
| Field       | Type   | Value       | Optional |
+=============+========+=============+==========+
| Temperature | Number | Temperature | Yes      |
+-------------+--------+-------------+----------+
| Pressure    | Number | Pressure    | Yes      |
+-------------+--------+-------------+----------+
| Humidity    | Number | Humidity    | Yes      |
+-------------+--------+-------------+----------+


The body should be in JSON format.

Getting User Data
=================

GET /data/user/:uid
-------------------

To get user data you need to make a GET call to the following url:
``https://api.poluino.xyz/data/user/:uid``

Path Parameters

+-------+--------+----------+----------+
| Field | Type   | Value    | Optional |
+=======+========+==========+==========+
| uid   | String | Your UID | No       |
+-------+--------+----------+----------+

Output

.. code-block:: json
 
  {
    "id": Your UID,
    "name": Your Name,
    "accType": Number,
    "loginMethod": Number,
    "discordId": Your Discord ID,
    "verified": 1 or 0,
  }

Errors
======

The Poluino API uses the following error codes:

+------------------+----------------------------------------------------------+
| Error Code       | Meaning                                                  |
+==================+==========================================================+
| NO_TOKEN         | A token needed to process the request was not specified. |
+------------------+----------------------------------------------------------+
| ERROR_NO_DEVICE  | The board that was being searched for was not found.     |
+------------------+----------------------------------------------------------+
| ERR_MISSING_JSON | There was a missing parameter in the request body.       |
+------------------+----------------------------------------------------------+
| SQL_ERROR        | There was an error within the server.                    |
+------------------+----------------------------------------------------------+
