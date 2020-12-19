Beta API
=========
The Weather Station Project Beta API provides programmatic access to read and write data.

POST /data/update
-----------------

To post board data you need to make a POST call to the following url:
``https://beta.api.weatherstationproject.com/data/update``

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
``https://beta.api.weatherstationproject.com/data/board/:token``

Path Parameters

+-------+--------+------------------+---------------------+
| Field | Type   | Value            | If Value is Unknown |
+=======+========+==================+=====================+
| token | String | Your Board Token | REQUIRED            |
+-------+--------+------------------+---------------------+

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

GET /data/user/:uid
-------------------

To get user data you need to make a GET call to the following url:
``https://beta.api.weatherstationproject.com/data/user/:uid``

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

GET /data/public_boards
-----------------------

To get user data you need to make a GET call to the following url:
``https://beta.api.weatherstationproject.com/data/public_boards``

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


GET /data/public_boards/id/:id
------------------------------

To get board data by ID you need to make a GET call to the following url:
``https://beta.api.weatherstationproject.com/data/public_boards/id/:id``

Path Parameters

+-------+--------+----------+----------+
| Field | Type   | Value    | Optional |
+=======+========+==========+==========+
| id    | String | Board ID | No       |
+-------+--------+----------+----------+

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
  
GET /data/public_boards/name/:name
----------------------------------

To get board data by name you need to make a GET call to the following url:
``https://beta.api.weatherstationproject.com/data/public_boards/name/:name``

Path Parameters

+-------+--------+------------+----------+-----------------------------+
| Field | Type   | Value      | Optional | If Value is Unknown         |
+=======+========+============+==========+=============================+
| name  | String | Board Name | No       | First Letters of Board Name |
+-------+--------+------------+----------+-----------------------------+

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
  
GET /updates/latest
-------------------

To get the latest updates from us, make a GET request to this link:
``https://beta.api.weatherstationproject.com/updates/latest``

Output

.. code-block:: json
 
  {
    "id": Update ID,
    "author": Update Author,
    "text": Update Text,
    "time": Update Time
  }

GET /updates/id/:updateID
-------------------------

To get the latest updates from us, make a GET request to this link:
``https://beta.api.weatherstationproject.com/updates/id/:updateID``

Path Parameters

+-----------+--------+----------+----------+
| Field     | Type   | Value    | Optional |
+===========+========+==========+==========+
| updateID  | String | updateID | No       |
+-----------+--------+----------+----------+

Output

.. code-block:: json

  {
    "id": Update ID,
    "author": Update Author,
    "text": Update Text,
    "time": Update Time
  }

GET /ml/:token
--------------

To get the latest updates from us, make a GET request to this link:
``https://beta.api.weatherstationproject.com/ml/:token``

Path Parameters

+-------+--------+------------------+---------------------+
| Field | Type   | Value            | If Value is Unknown |
+=======+========+==================+=====================+
| token | String | Your Board Token | REQUIRED            |
+-------+--------+------------------+---------------------+

Output

.. code-block:: json
 
  {
    "token": Your Board Token,
    "latitude": Your Latitude,
    "longitude": Your Longitude,
    "year": Year when Data was Recorded,
    "month": Month when Data was Recorded in Numbers(s),
    "date": Day when Data was Recorded in Numbers(s),
    "hour": Hour when Data was Recorded in Numbers(s),
    "min_temp": Minimum Temperature Recorded,
    "max_temp": Maximum Temperature Recorded,
    "min_press": Minimum Pressure Recorded,
    "max_press": Maximum Pressure Recorded,
    "min_hum": Minimum Humidity Recorded,
    "max_hum": Maximum Humidity Recorded,
    "min_rain": Minimum Rainfall Recorded,
    "max_rain": Maximum Rainfall Recorded,
    "min_wind_speed": Minimum Wind Speed Recorded,
    "max_wind_speed": Maximum Wind Speed Recorded,
    "min_wind_direction": Minimum Wind Direction Recorded,
    "max_wind_direction": Maximum Wind Direction Recorded
  }

Errors
------

The WSP Beta API uses the following error codes:

+------------------+----------------------------------------------------------+
| Error Code       | Meaning                                                  |
+==================+==========================================================+
| MISSING_TOKEN    | A token needed to process the request was not specified. |
+------------------+----------------------------------------------------------+
| NO_BOARD         | The board that was being searched for was not found.     |
+------------------+----------------------------------------------------------+
| ERR_MISSING_JSON | There was a missing parameter in the request body.       |
+------------------+----------------------------------------------------------+
| SQL_ERROR        | There was error within the server.                       |
+------------------+----------------------------------------------------------+
