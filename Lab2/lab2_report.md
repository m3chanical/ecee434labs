% ECEE 434 Lab 2 - Mosfet Inverter Propagation Delay
% Liz MacLean & Carl Anderson
%

# Introduction & Background

Capacitance is an inherent property in transistors that can be used to determine other properties of the transistor.
The experiment performed involved simulating a CMOS inverter and measuring the output to determine the propagation delay ($t_{PHL}$ and $t_{PLH}$)
of the circuit. This information was then used to determine the NMOS/PMOS equivalent resistance, and the Gate and Drain capacitances.

The lab required further use of Cadence Virtuoso to modify several parameters and components, and then build and simulate the circuits.

\pagebreak 

# Procedure

This experiment consisted of four distinct but related parts. 

1. Verifying the strength of an NMOS transistor with respect to a PMOS. 
    * Simulate an inverter with matched PMOS/NMOS widths and measure the respective propagation delays.
    * $t_p$ can be found with the above propagation delays, and $R_n$ can be calculated.
2. Find $R_N$ and $R_P$
    * Using a new circuit with different load capacitance, use propagation delays and approximating functions to find the resistance values.
3. Find $C_D$ using some cool ass techniques.
    * boop!
4. Find $C_G$
    * More manipulation.

\pagebreak

# Results

### Verify Strength of NMOS with respect to PMOS

![Schematic used for Part (1) PMOS vs. NMOS Strength](2.1\ Inverter\ Schematic.png)

The values for $t_{PLH}$ and $t_{PHL}$ were measured from the output waveform of the simulation. 

$t_{PLH} = 25.141ns - 20.001ns = 5.140ns$

$t_{PHL} = 30.07ns - 30.001ns = 0.069ns$

$\frac{k_N}{k_P} \approx \frac{t_{PLH}}{t_{PHL}} = \frac{5.140}{0.069} = 74.49$

The reason $\frac{k_N}{k_P} \approx \frac{t_{PLH}}{t_{PHL}}$ is because the ratio $\frac{k_N}{k_P} = \frac{\mu_N}{\mu_P}$, which is representative of the carrier mobility. 
The propagation delay is present in part because of the carrier mobility and recombination rate of the materials. 

\pagebreak 

### Find $R_n$

![Schematic used to find $R_N$ of the Inverter circuit.](2.2\ Inverter\ Schematic.png)

$R_n$ can be found by using the average resistance equation for finding $t_{PHL}$:

$$t_{PHL} = 0.69*R_N*C_{load}$$

That function can be easily manipulated to find the $R_N$ value. The capacitance value is equivalent to the load capacitor in the circuit which was 500fF. 

$t_{PHL} = 103.7145ns - 100.0005ns = 3.714ns$

$R_N = \frac{t_{PHL}}{0.69*C_{load}} = 10765.22\Omega$

$t_{PLH} = 56.6188ns - 50.0015ns = 6.6173ns$

$R_P = \frac{t_{PLH}}{0.69*C_{load}} = 19180.58\Omega$

The time constant of an RC circuit is determined by $\tau = R_{eq}C_{eq}$. In this circuit, the high to low and low to high propagation delays are measured at half of the 
transition between the two states. This corresponds to a multiplication by 0.69 (half-time). Using this knowledge, the equivalent resistance of the MOSFET can be calculated. 

### Find $C_D$

$t_{PLH} = 50.1026ns - 50.0015ns =$

$t_{PHL} = 100.0592ns - 100.0005ns =$

### Find $C_G$

$t_{PLH} = 54.3188ns - 50.0016ns =$

$t_{PHL} = 103.0953ns - 100.0004ns =$

\pagebreak

# Conclusion

Things to say: 

* we found how to use propagation delays to determine certain aspects of 
* these results, while not necessarily entirely accurate, help describe in general the behavior of the circuit. 

