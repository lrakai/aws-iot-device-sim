# aws-iot-device-sim
Device simulators for AWS IoT in Python.  Devices simulate what could be found in the kitchen of an office building.

# Devices
## Fire Sprinkler
* Published to topic office/kitchen at 1Hz: smoke level of 1 if space bar is pressed, 0 otherwise
* Subscribed to topic office/kitchen/kit-fs-001: messages written to standard output

### Usage
Using certificate based mutual authentication:
```shell
python fireSprinkler.py -e <endpoint> -r <rootCAFilePath> -c <certFilePath> -k <privateKeyFilePath>
```

Using MQTT over WebSocket:
```shell
python fireSprinkler.py -e <endpoint> -r <rootCAFilePath> -w
```

## Air Conditioner
* Published to topic office/kitchen at 1Hz: temperature reading
* Subscribed to topic office/kitchen/kit-ac-001: messages written to standard output
* Managed state: {"air-conditioning":("off"|"on)}

### Usage
Using certificate based mutual authentication:
```shell
python airConditioning.py -e <endpoint> -r <rootCAFilePath> -c <certFilePath> -k <privateKeyFilePath>
```

Using MQTT over WebSocket:
```shell
python airConditioning.py -e <endpoint> -r <rootCAFilePath> -w
```
