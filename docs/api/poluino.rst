***********
Poluino API
***********

The Poluino API provides programmatic access to read and write data.

Sending and Receiving Weather Data
==================================

POST /data/update
-----------------

To post board data you need to make a POST call to the following url:
``https://api.poluino.xyz/data/update``

Request Body Parameters

+----------------+----------+-----------------------+----------+
| Field          | Type     | Value                 | Optional |
+================+==========+=======================+==========+
| token          | String   | Your Board Token      | No       |
+----------------+----------+-----------------------+----------+
| temperature    | Number   | Temperature in Celsius| Yes      |
+----------------+----------+-----------------------+----------+
| pressure       | Number   | Pressure in hPA       | Yes      |
+----------------+----------+-----------------------+----------+
| humidity       | Number   | Humidity in RH        | Yes      |
+----------------+----------+-----------------------+----------+
| rainfall       | Number   |                       | Yes      |
+----------------+----------+-----------------------+----------+
| wind_speed     | Number   | -255                  | Yes      |
+----------------+----------+-----------------------+----------+
| wind_direction | Number   | -255                  | Yes      |
+----------------+----------+-----------------------+----------+
| lux            | Number   | -255                  | Yes      |
+----------------+----------+-----------------------+----------+
| uv_index       | Number   | -255                  | Yes      |
+----------------+----------+-----------------------+----------+

Output

.. code-block:: json

   { "Success" : true}

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
    "board_name": Your Board Name,
    "token": Your Board Token,
    "latitude": Your Board Latitude,
    "longitude": Your Board Longitude,
    "temperature": Your Latest Temperature,
    "pressure": Your Latest Pressure,
    "humidity": Your Latest Humidity,
    "rainfall": Your Latest Temperature,
    "wind_speed": Your Latest Wind Speed,
    "wind_direction": Your Latest Wind Direction,
    "lux": Your Latest Lux,
    "uv_index": Your Latest UV Index,
    "user_id": Your User ID,
    "last_time_connected": Time of Your Last Post,
    "online": 1 or 0,
    "public": 1 or 0,
    "verified": Number,
    "allow_collection": 1 or 0
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
    "board_name": Board Name,
    "latitude": Board Latitude,
    "longitude": Board Longitude,
    "temperature": Latest Temperature,
    "pressure": Latest Pressure,
    "humidity": Latest Humidity,
    "rainfall": Latest Temperature,
    "wind_speed": Latest Wind Speed,
    "wind_direction": Latest Wind Direction,
    "lux": Latest Lux,
    "uv_index": Latest UV Index,
    "last_time_connected": Last Time Connected,
    "online": 1 or 0,
    "public": 1
  }

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
    "email": Your Email,
    "password": A Hash of Your Password,
    "name": Your Name,
    "id": Your UID,
    "email_opt_in": 1,
    "verified": yes or no,
    "api": Your API Package,
    "requests": Requests You Made within the Hour,
    "discord_id": Your Discord ID,
    "discord_confirmed": 1 or 0,
    "discord_mentioned": 1 or 0,
    "discord_notified": 1 or 0,
    "admin": 1 or 0
  }

Posting Data to the API
=======================

POST /data/update
-----------------

To get user data you need to make a GET call to the following url:
``https://api.poluino.xyz/data/update``

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
| Token       | Number | String      | No       |
+-------------+--------+-------------+----------+

The body should be in JSON format.

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
