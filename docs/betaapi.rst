WSP API
=======

The Weather Station Project Beta API provides programmatic access to read and write data.

Post Board Data
---------------

To post board data you need to make a POST call to the following url:
``https://beta.api.weatherstationproject.com/data/update``

Request Body Parameters

+----------------+----------+-----------------------+----------+
| Field          | Type     | Header 3              | Optional |
+================+==========+=======================+==========+
| token          | String   | Value                 | No       |
+----------------+----------+-----------------------+----------+
| temperature    | Number   | Your Board Token      | Yes      |
+----------------+----------+-----------------------+----------+
| pressure       | Number   | Temperature in Celsius| Yes      |
+----------------+----------+-----------------------+----------+
| humidity       | Number   | Pressure in hPA       | Yes      |
+----------------+----------+-----------------------+----------+
| rainfall       | Number   | Humidity in RH        | Yes      |
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

Get Board Data
--------------

To get board data you need to make a GET call to the following url:
``https://beta.api.weatherstationproject.com/data/board/:token``

Path Parameters

+----------------+------------------+---------------------+
| Field | Type   | Value            | If Value is Unknown |
+=======+========+==================+=====================+
| token | String | Your Board Token | REQUIRED            |
+----------------+------------------+---------------------+

Output

.. code-block:: json
 
  [
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
   ]

Get User Data
-------------

To get user data you need to make a GET call to the following url:
``https://beta.api.weatherstationproject.com/data/user/:uid``

Path Parameters

+----------------+----------+----------+
| Field | Type   | Value    | Optional |
+=======+========+==========+==========+
| uid   | String | Your UID | No       |
+-------+--------+----------+----------+

Output

.. code-block:: json
 
  {
    "email": "Your Email",
    "password": "A Hash of Your Password",
    "name": "Your Name",
    "id": "Your UID",
    "email_opt_in": 1,
    "verified": "yes or no",
    "api": "Your API Package",
    "requests": "Requests You Made within the Hour",
    "discord_id": "Your Discord ID",
    "discord_confirmed": "1 or 0",
    "discord_mentioned": "1 or 0",
    "discord_notified": "1 or 0",
    "admin": "1 or 0"
  }

Get Public Board Data
---------------------

To get user data you need to make a GET call to the following url:
``https://beta.api.weatherstationproject.com/data/public_boards``

Output

.. code-block:: json
 
  [
    {
      "id": "Board ID",
      "board_name": "Board Name",
      "latitude": "Board Latitude",
      "longitude": "Board Longitude",
      "temperature": "Latest Temperature",
      "pressure": "Latest Pressure",
      "humidity": "Latest Humidity",
      "rainfall": "Latest Temperature",
      "wind_speed": "Latest Wind Speed",
      "wind_direction": "Latest Wind Direction",
      "lux": "Latest Lux",
      "uv_index": "Latest UV Index",
      "last_time_connected": "Last Time Connected",
      "online": "1 or 0",
      "public": 1
    },
    ...
  ]

Get Public Board (ID)
---------------------

To get board data by ID you need to make a GET call to the following url:
``https://beta.api.weatherstationproject.com/data/public_boards/id/:id``

Path Parameters

+----------------+----------+----------+
| Field | Type   | Value    | Optional |
+=======+========+==========+==========+
| id    | String | Board ID | No       |
+-------+--------+----------+----------+

Output

.. code-block:: json
 
  [
    {
      "id": "Board ID",
      "board_name": "Board Name",
      "latitude": "Board Latitude",
      "longitude": "Board Longitude",
      "temperature": "Board Temperature",
      "pressure": "Board Pressure",
      "humidity": "Board Humidity",
      "rainfall": "Board Rainfall",
      "soil_moisture": "Board Soil Moistyre",
      "wind_speed": "Board Wind Speed",
      "wind_direction": "Board Wind Direction",
      "lux": "Board Lux",
      "uv_index": "Board UV Index",
      "last_time_connected": "Last Time Connected",
      "online": "1 or 0",
      "public": 1
    }
  ]

Get Public Board (Name)
-----------------------

To get board data by name you need to make a GET call to the following url:
``https://beta.api.weatherstationproject.com/data/public_boards/name/:name``

Path Parameters

+----------------+------------+----------+-----------------------------+
| Field | Type   | Value      | Optional | If Value is Unknown         |
+=======+========+============+==========+=============================+
| name  | String | Board Name | No       | First Letters of Board Name |
+-------+--------+------------+----------+-----------------------------+

Output

.. code-block:: json
 
  [
    {
      "id": "Board ID",
      "board_name": "Board Name",
      "latitude": "Board Latitude",
      "longitude": "Board Longitude",
      "temperature": "Latest Temperature",
      "pressure": "Latest Pressure",
      "humidity": "Latest Humidity",
      "rainfall": "Latest Temperature",
      "wind_speed": "Latest Wind Speed",
      "wind_direction": "Latest Wind Direction",
      "lux": Latest "Lux",
      "uv_index": "Latest UV Index",
      "last_time_connected": "Last Time Connected",
      "online": "1 or 0",
      "public": 1
    }
  ]
