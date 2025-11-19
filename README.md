# Little Bee H1 - 魔改款高性能开源电流探头

https://item.taobao.com/item.htm?ft=t&id=860942806853

本探头在开源Little-Bee-B1项目上进行了改版，主要变更如下：

**优化**
- 带宽：原版为10M带宽，现在0.2V/A档的小信号带宽超过30MHz，1V/A档的带宽不低于10MHz。
  两级放大器分别更换为AD8130和LT1886，同时对应修改了参数并进行了补偿。
- 供电：新版板载锂电充放电管理电路，且内置可充电电池，仅需一根同轴电缆连接示波器，即可使用。
- 成本与可制造性：尽可能更换了国产器件，各插件均改单面贴片便于生产，盖板改亚克力面板更好看
- 量程：定制了10A磁头，用户可以根据实际需要自行采用；此外，10A磁头如果去掉磁芯只留空壳，可以测30A电流。

**牺牲**
- 功耗：由于放大器选型更换，功耗增大，但是电池也增大、且可充电，因此能实现3小时的续航；
- 噪声：带宽增大导致噪声变大，现在绿色档下噪声为66mVpp (~10mArms)

**标配5A磁头下的档位说明：**
绿色：0.2V/A（5x衰减），±5A量程，30MHz带宽
黄色：0.2V/A（5x衰减），±5A量程，1MHz带宽
深蓝：1V/A（1x衰减），±1.2A量程，1MHz带宽
浅蓝：1V/A（1x衰减），±1.2A量程，1MHz带宽
送一款10A磁头，建议标定为0.1V/A.
10A磁头如果去掉磁芯只留空壳，可以测30A电流，此时建议标定为0.05V/A

**提示**
本探头是一款高性价比高性能的开源探头，但是它有若干缺点：
- 量程小：**超过量程不会坏**，但是会磁化，此时无需下电需要短按以下消磁按钮；
- 使用时不能大幅晃动：传感器灵敏度高，地磁场会造成偏置，调零后不宜晃动，否则需重新长按调零；
- 噪声大：由于噪声略大，不适合低功耗测试，只适合电源电机调试使用。

**版本说明**

所有改动都是在立创EDA专业版上修改的，没有原理图，直接改的PCB
- LittleBeeH1-30M低成本款原稿V1.0.zip：这个版本还是0.25V/A的，后续改为0.2V/A了

<img width="1708" height="1280" alt="image" src="https://github.com/user-attachments/assets/c49175e4-83d5-4552-a92a-00b82bc52932" />
<img width="800" height="480" alt="image" src="https://github.com/user-attachments/assets/93494565-0b6c-4ad8-9cbe-ec1254d8001f" />
<img width="800" height="480" alt="image" src="https://github.com/user-attachments/assets/a4e45970-709f-4de0-a2e0-ee73402d75a8" />




# Little Bee H1 - Optimized High-Performance Open-Source Current Probe

This probe is a revised version based on the open-source Little-Bee-B1 project. The main changes are as follows:

**Optimizations**
- Bandwidth: The original version had a bandwidth of 10MHz. Now, the small-signal bandwidth in the 0.2V/A range exceeds 30MHz, and the bandwidth in the 1V/A range is no less than 10MHz.
The two-stage amplifiers have been replaced with AD8130 and LT1886, respectively, with corresponding parameter modifications and compensation applied.
- Power: The new version features onboard lithium battery charge and discharge management circuitry and includes a built-in rechargeable battery. It can be used with just a coaxial cable connected to an oscilloscope.
- Cost and Manufacturability: Components have been replaced with domestic alternatives where possible. All through-hole components have been changed to surface-mount devices (SMD) on a single side for easier production. The cover has been replaced with an acrylic panel for a better appearance.
- Range: A custom 10A magnetic head is provided, allowing users to select based on their actual needs. Additionally, if the magnetic core is removed from the 10A head, leaving only the empty shell, it can measure currents up to 30A.

**Trade-offs**
- Power Consumption: Due to the change in amplifier selection, power consumption has increased. However, the battery capacity has also been increased and is rechargeable, providing up to 3 hours of battery life.
- Noise: The increased bandwidth results in higher noise. The current noise level in the green range is 66mVpp (~10mArms).

**Description with Standard 5A Magnetic Head:**
- Green: 0.2V/A (5x attenuation), ±5A range, 30MHz bandwidth
- Yellow: 0.2V/A (5x attenuation), ±5A range, 1MHz bandwidth
- Blue: 1V/A (1x attenuation), ±1.2A range, 1MHz bandwidth
- Teal: 1V/A (1x attenuation), ±1.2A range, 1MHz bandwidth
A 10A magnetic head is also included, recommended to be calibrated at 0.1V/A.
If the magnetic core is removed from the 10A head, leaving only the empty shell, it can measure currents up to 30A. In this case, it is recommended to calibrate at 0.05V/A.

**Notes**
This probe is a cost-effective, high-performance open-source probe, but it has several limitations:
- Small Range: Exceeding the range will not damage the probe, but it may cause magnetization. In this case, press the demagnetization button briefly without powering off.
- Avoid Significant Movement During Use: The sensor is highly sensitive, and the Earth's magnetic field can cause offset. After zeroing, avoid moving the probe significantly; otherwise, long-press the zero button to recalibrate.
- High Noise: Due to relatively high noise, it is not suitable for low-power testing. It is best used for power supply and motor debugging.

**Version Information**
All modifications were made using LCEDA Pro. There is no schematic as I am so lazy that the PCB was modified manually and directly without schematics.
-LittleBeeH1-30M Low-Cost Original Version V1.0.zip: This version still uses 0.25V/A, which was later changed to 0.2V/A.


## 以下为B1原始版本的介绍
## Intorduction for the Original Little Bee B1:
# Little Bee B1 - A high performance current & magnetic field probe
**Operating Instructions are located in the [getting-started](getting-started/README.md) folder**


The Little Bee B1 is an open source magnetic field and current probe based on an Anisotropic Magneto-Resistive (AMR) magnetic sensor.
It directly senses magnetic fields and measures current with a current sensing attachment consisting of a gapped ferrite toroid that is placed around a wire, establishing a fixed relation between the current in the wire and magnetic field the sensor is subject to.

The probe is capable of sensing DC currents and has a high frequency -3dB bandwidth in excess of 10Mhz. Typical specifications for current sensing are a +/- 5A range, and a 3mA RMS noise floor. For magnetic field sensing the probe has a +/- 6 gauss range. It is compatible with any 1M ohm input oscilloscope and is powered by a single AA battery. The probe uses a PIC microcontroller to automatically zero the sensor and to provide adjustable gain and bandwidth.

All project source files are in this repository and the project currently has a CrowdSupply [campaign](https://www.crowdsupply.com/weston-braun/little-bee)
<img src="doc/images/little_bee_v4_attachment.jpg" width="400"/> <img src="doc/images/little_bee_v4_circuit.jpg" width="400"/>

### Typical Electrical Performance

#### Current sensing

- **Bandwidth**: DC - 10 MHz
- **Sensitivity**: 0.25 Volts/Amp
- **Max Current**: +/- 5 A
- **Noise**
    - 3 mA RMS at 10 MHz bandwidth
    - 2 mA RMS at 1 MHz bandwidth
- **DC Accuracy**: +/- 15%
- **Insertion Impedance**: 100 nH in parallel with 70 Ohms

#### Magnetic Field Sensing

- **Bandwidth**: DC - 10 MHz
- **Sensitivity**: 0.2 Volts/Gauss
- **Max Field**: +/- 6 Gauss
- **Noise**
    - 4mG RMS at 10 MHz bandwidth
    - 2.5mG RMS at 1 MHz bandwidth

## Operation
Connect the Little Bee to any oscilloscope with a SMA-BNC cable. When the probe is powered on it automatically zeros and starts in the high bandwidth and low gain mode. Tapping the "Mode Select" button will cycle through the bandwidth and gain options, which are indicated by the LED color.

The probe should be re-zeroed after switching modes. This is accomplished by pressing and holding the "zero/reset" button for at least one second before releasing. The LED will blink once when the button is first pressed and a second time when the zeroing operation is done.

When the sensor is exposed to an excessive magnetic field, or excessive current when the current sensing attachment is used, the sensor will be demagnetized and need to be reset for normal operation. For on axis fields the probe can detect this and will turn the indicator light red.
Off axis fields, which can occur when the probe is used for magnetic field sensing, can exceed the sensor limit without being detected. This will result a loss of sensitivity and noticeable distortion in the sensed waveforms.  
The sensor can be reset and normal operation restored without impacting the zeroing of the probe by tapping the "zero/reset" button, which will briefly flash the indicator light.

If the probe senses a low battery that will inhibit normal operation the indicator light will flash red. An alkaline AA battery should provide around 4 hours of battery life.

### Current Sensing
Current sensing is achieved with the current sensing attachment, which clips on to the tip of the probe. The current sensing attachment uses a ferrite core to translate the current flowing in to a wire into a known magnetic field strength.
A wire can be threaded through the current sensing attachment or the current sensing attachment can be slipped over a wire before being clipped on. With the logo and writing on the Little Bee facing the user, a wire carrying current away from the user will be read as a positive current.

The location of the wire within the current sensing attachment has some impact on the sensitivity of the probe due to the magnetic field in generates. It is recommended to keep the wire on the opposite side of the sensing tip within the aperture of the current sensing attachment.

For higher resolution when measuring low currents, multiple turns of the wire can be made through the aperture of the current sensing attachment. The final sensitivity will be the set sensitivity times the number of turns.

Tapping the "Mode Select" button will cycle through the bandwidth and gain options, which are indicated by the LED color:

| LED Color | Mode                    |
|-----------|-------------------------|
| Green     | 10MHz bandwidth 0.25V/A |
| Yellow    | 1MHz bandwidth 0.25V/A  |
| Blue      | 10MHz bandwidth 1V/A    |
| Teal      | 1MHz Bandwidth 1V/A     |

The gain of the probe can be adjusted with the labeled trimmer resistor on the PCB. Units are shipped calibrated to the above gains.

### Magnetic Field Sensing
The magnetic sensor is located approximately 1.0mm offset from the tip of the probe. The Little Bee will measure a magnetic field entering perpendicular to the top of the probe as a positive voltage. To measure the magnetic field emitted by a PCB trace the probe should be placed perpendicular to the PCB with the long direction of the tip parallel to the trace.

The earth's magnetic field is typically between 0.3 - 0.6 Gauss, depending on geographic location. This is well within the sensing range of the probe. Additionally, large ferrous objects and transformers can emit stray magnetic fields. It is recommended the Little Bee is zeroed while holding it in the orientation used for taking measurements to reduce the error introduced by stray magnetic fields.


The gain of the probe is calibrated based on measurements with the current sensing attachment, so the true sensitivity will depend on the tolerance current sensing attachment. The nominal sensitivities are:

| LED Color | Mode                           |
|-----------|--------------------------------|
| Green     | 10MHz bandwidth 0.2 V/Gauss  |
| Yellow    | 1MHz bandwidth 0.2 V/Gauss   |
| Blue      | 10MHz bandwidth 0.8 V/Gauss  |
| Teal      | 1MHz Bandwidth 0.8 V/Gauss   |



## Hardware
The kicad PCB files are in the [PCB](pcb/) directory and the [schematic](doc/current-sense.pdf) is in the doc directory.

## Firmware
The Little Bee uses a PIC16 microcontroller to automatically zero the probe and control gain and bandwidth switching. The firmware is built with the
MPLAB X IDE and the complete project is in the [firmware](firmware) directory

## Open Source
This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

## Demos
### Sensing the AC line current into a switch-mode power supply
<img src="doc/images/flux_concentrator_demo.jpg" width="600"/>

### Sensing the magnetic field from an inductor
<img src="doc/images/field_mode_demo.jpg" width="600"/>

### Example Waveforms
Yellow Waveform: Little Bee B1

Green Waveform: Tektronix CT-2 Current Transformer
#### Ramp
<img src="doc/images/waveform-ramp.PNG" width="600"/>

#### SinC
<img src="doc/images/waveform-sinc.PNG" width="600"/>

#### Square Wave (Low Current)
<img src="doc/images/waveform-square-wave.PNG" width="600"/>

#### Noise Floor
<img src="doc/images/waveform-noise-floor.PNG" width="600"/>
