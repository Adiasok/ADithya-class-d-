# Adithya-class D amplifier
a class d amplifier

This project presents a Class D audio amplifier built with fully discrete gate drivers, engineered for high efficiency, tight switching control, and low distortion. By replacing integrated driver ICs with a custom discrete design. The result is a compact, efficient, and highly tunable switching amplifier that demonstrates both the challenges and advantages of going fully discrete in modern power-audio design.

The beginning of the project was my simulation, but due to inexperience with making a practical design i was not able to make the pwm wave necessary. I was successfully able to create a square wave which i have added above. But the rest were not coming properly. Because of trying to make the whole thing work in simulation, i might have slightly backtracked and the work lagged, the schematic has also been uploaded above.
the file (Screenshot (9).png), shows the theoritical wave generation and comparing it with the signal to get a PWM signal. I choose TLV3271D because of the high GBW and the high frequency it is able to handle easily. R and C values where choosen to properly generate the frequency of 400khz in the circuit.

In the next image (Screenshot (10).png), i desinged the power supply and the Signal input. the power supply was a standard 5v coming from the barrel jack which will pass through bulk capacitors so that if the whole circuit demands too much current, then the bulk will be able to supply the necessary current. The values of bulk capacitors are standards values of 0.1u and 10u. The screw terminal in the bottom is used to get the input signal from outside the system. 

![image alt](https://github.com/Adiasok/ADithya-class-d-/blob/main/Screenshot%20(11).png?raw=truehttps://github.com/Adiasok/ADithya-class-d-/blob/main/Screenshot%20(11).png?raw=true)

in the next image (Screenshot (11).png), we have two parts of the circuit, dead time generation and the mosfet switching. Dead time generation is ery important, as it negates the chances of short circuiting the mosfet in case the rising of one edge touches the falling of the other ones edge. This leads to large of amount of current generated which will fry the mosfet. The mosfet used here is the IRF3205, a n channel mosfet. In the higher switching side capacitors are added to provide the gate with voltage higher than Vcc. 

The output is again a pwm signal which gets filtered by the LC filter into the amplified signal.
