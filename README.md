# BITxo

![](https://github.com/davidanton/BITxo/blob/master/doc/img/logo.png)

---
###Stage of the project: **Prototyping**
---

####System Description

BITxo (pronounced */ˈbiʧo/*, Spanish for *bug*) is a bug bot that is able to move thanks to two ERM (eccentric rotating mass) vibration motors placed on the PCB. The centripetal force generated by the eccentric rotating mass is transmitted along the X and Z axes, being the Y axis the one collinear with the axis of rotation and the Z axis parallel to the normal of the PCB. The motors on BITxo rotate in opposite directions, canceling out the forces generated by both ERM vibration motors along the X axes and thus creating and up-down motion that would allow BITxo to move forward. Two single-core copper wires, attached each to a mechanical endstop, serve as BITxo's antennas. When one of the endstops is pressed against an obstacle, one of the ERM vibration motors stops rotating, therefore BITxo would rotate in the opposite direction of the obstacle.

![](https://github.com/davidanton/BITxo/blob/master/doc/img/PCB.png)

![](https://github.com/davidanton/BITxo/blob/master/doc/img/BITxo.png)

![](https://github.com/davidanton/BITxo/blob/master/doc/img/prototype1.jpg)

![](https://github.com/davidanton/BITxo/blob/master/doc/img/prototype2.jpg)

####Principle of Operation

The voltage is regulated by a linear regulator to 3.3V, the maximum operating voltage of the ERM vibration motors. The time during which the ERM vibration motor stops rotating depends on the RC time constant of *R1* and *C3* as shown in the figure. When the endstop is pressed, the capacitor *C3* charges and the ERM vibration motor *M1* stops vibrating. When the endstop is released, the capacitor would discharge and when its voltage reaches a certain threshold, the p-MOSFET *Q1* would allow *M1* to vibrate again.

The filtering capacitor *C4* and the flyback diode *D1* are not necessary for this simple design, but may be used in future implementations.

![](https://github.com/davidanton/BITxo/blob/master/doc/img/schematic.png)

![](https://github.com/davidanton/BITxo/blob/master/doc/img/schematic_detail.png)

Initial tests show that calibration is crucial for a stable forward motion. The pins used as legs don't function very well in that regard. A suggestion small slanted brushes, adding homogeneity, stability and allowing forward motion due to their slanted bristle position.

The performance of the capacitor circuit is not as reliable as first thought. An implementation using a microcontroller such as an ATtiny would be the next step in the design process.

####Video

https://www.youtube.com/watch?v=kGmnQzfZgtA
