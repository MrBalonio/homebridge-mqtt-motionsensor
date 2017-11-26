# homebridge-mqtt-motionsensor

Get Motion Sensor status via MQTT in Homebridge

Use field_name to parse the field containing your sensor value.
if field_name is not added to config the plugging will try to parse the
value. It assumes you ahve a single digit with the values below.

The value of the field must be a 0 or a 1
0 for false
1 for true

Installation
--------------------
    sudo npm install -g homebridge-mqtt-motionsensor


Sample HomeBridge Configuration
--------------------
    {
      "bridge": {
        "name": "HomeBridge",
        "username": "CC:33:3B:D3:CE:32",
        "port": 51826,
        "pin": "321-45-123"
      },

      "description": "",

      "accessories": [
        {
          "accessory": "mqtt-motionsensor",
          "name": "Living Room",
          "url": "mqtt://localhost",
          "topic": "home/livingroom/motionsensor",
          "username": "username",
          "password": "password",
          "field_name": "json_field_name"
        }
      ],

      "platforms": []
    }
