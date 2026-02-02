# Adithya-class D amplifier
a class d amplifier

This project presents a Class D audio amplifier built with fully discrete gate drivers, engineered for high efficiency, tight switching control, and low distortion. By replacing integrated driver ICs with a custom discrete design. The result is a compact, efficient, and highly tunable switching amplifier that demonstrates both the challenges and advantages of going fully discrete in modern power-audio design.

The project initially began with extensive circuit-level simulation to validate the PWM generation approach before moving to hardware. A high-speed comparator–based method was explored, where a reference waveform was compared against a carrier signal to generate the required PWM. During this phase, a stable high-frequency square-wave carrier was successfully generated and verified in simulation.

To support operation at a carrier frequency of 400 kHz, the TLV3271D was selected due to its high gain-bandwidth product and fast response characteristics, making it suitable for high-frequency signal processing. The RC values were carefully chosen to achieve the target switching frequency while maintaining waveform stability.

While the square-wave generation behaved as expected, integrating the full PWM generation chain highlighted practical challenges related to component tolerances, comparator dynamics, and real-world non-idealities that are not always apparent at the simulation stage. Iterating on the design exposed limitations of the initial approach and helped identify areas requiring refinement before hardware implementation.

This process reinforced the importance of balancing simulation fidelity with practical design considerations, particularly in high-frequency switching systems. The experience provided valuable insight into PWM generation techniques, high-speed analog behavior, and the gap between theoretical models and real-world circuit performance, which informed later design decisions in the project.
In the next image (Screenshot (10).png), i desinged the power supply and the Signal input. the power supply was a standard 5v coming from the barrel jack which will pass through bulk capacitors so that if the whole circuit demands too much current, then the bulk will be able to supply the necessary current. The values of bulk capacitors are standards values of 0.1u and 10u. The screw terminal in the bottom is used to get the input signal from outside the system. 

![image alt](https://github.com/Adiasok/ADithya-class-d-/blob/main/Screenshot%20(11).png?raw=truehttps://github.com/Adiasok/ADithya-class-d-/blob/main/Screenshot%20(11).png?raw=true)

in the next image (Screenshot (11).png), we have two parts of the circuit, dead time generation and the mosfet switching. Dead time generation is ery important, as it negates the chances of short circuiting the mosfet in case the rising of one edge touches the falling of the other ones edge. This leads to large of amount of current generated which will fry the mosfet. The mosfet used here is the IRF3205, a n channel mosfet. In the higher switching side capacitors are added to provide the gate with voltage higher than Vcc. 

The output is again a pwm signal which gets filtered by the LC filter into the amplified signal.
