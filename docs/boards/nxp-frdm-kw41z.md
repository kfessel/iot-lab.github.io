---
title: NXP FRDM-KW41Z
group: boards
---

The FRDM-KW41Z open node is a [NXP FRDM-KW41Z](https://www.nxp.com/docs/en/user-guide/FRDMKW41ZUG.pdf)
This open node provides a BLE radio interface and a 802.15.4 radio interface.

<div style="text-align:center">
<img src="https://www.nxp.com/assets/images/en/photography/FRDM-KW41Z-DEMO.png"/>
</div>

The FRDM-KW41Z Open Node can reset, debug and program the ARM Cortex M0+ through
the embedded debugger (OpenOCD) connected to the gateway USB port. This
component also allows a UART connection to the M0. The input power source is
configured through the power management.

## IoT-LAB special configuration

The serial connection baudrate should be configured at **115200 bauds** in the
firmware.

## Extensions with sensors

Nodes in **Saclay site (frdm-kw41z-1 to frdm-kw41z-5)** are equipped with an
[ST X-NUCLEO-IKS01A2](https://www.st.com/en/ecosystems/x-nucleo-iks01a2.html)
shield.
This gives access to external sensors to the `frdm-kw41z` nodes:
  * a temperature and humidity sensor
    [HTS221](https://www.st.com/resource/en/datasheet/hts221.pdf)
  * an atmospheric pressure sensor
    [LPS22HB](https://www.st.com/resource/en/datasheet/dm00140895.pdf)
  * an accelerometer sensor
    [LSM6DSL](https://www.st.com/resource/en/datasheet/lsm6dsl.pdf)
  * an accelerometer sensor
    [LSM303AGR](https://www.st.com/resource/en/datasheet/lsm303agr.pdf)

## Example firmware

IoT-LAB provides an [example firmware](https://raw.githubusercontent.com/wiki/iot-lab/iot-lab/firmwares/custom/frdm-kw41z-default.elf)
that can be used on FRDM-KW41Z boards.
This firmware is based on [RIOT-OS saul example](https://github.com/RIOT-OS/RIOT/tree/master/examples/default).
The firmware can interact with the HTS221 and LSM6DSL sensors, as well as with
the 4 on-boards LEDs and buttons.
Example of RIOT shell commands:
<pre>
% list available commands
help
% list available actuators and sensors
saul
% read temperature value
saul read 8
% read relative humidity value
saul read 9
</pre>