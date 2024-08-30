# ESPHome Config for a Server Remote

An ESPHome Device to Boot and Shutdown my Server with Homeassistant.

## ESPHome CLI sheet

### update esp home
>
> pip3 install esphome -U
>

### configure yaml file in root directory and than compile file to generate firmware
>
> esphome compile server-power.yaml
>

### install the firmware to the device

on first install you have to manual flash the binary file:  
>
>.esphome\build\exampleProject\.pioenvs\exampleProject\firmware.bin
>

to the connected esp device

## update firmware
>
1. > esphome compile server-power.yaml
2. > esphome upload server-power.yaml
>

or

>
1. > esphome run server-power.yaml
>
---

## secrets

configure secrets in `secrets.yaml` file and bind the properties to the ``server-power.yaml`` file

To Bind to the root secrets file you can add another secrets.yaml in the device folder and paste this into the file:
>
> <<: !include ../secrets.yaml
>

1. configure secret in `secrets.yaml` file
   >
   > property: "myRealProperty"
   >
2. configure secret in `server-power.yaml` file
   >
   > property: !secret propety
   >