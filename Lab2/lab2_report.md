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

This experiment consisted of four distinct but related parts. The main objective is to measure the propagation delays of various circuit configurations
in order to determine the capacitance of the components used.

First, the strength of an NMOS transistor with respect to a PMOS was verified by simulating an inverter with matched PMOS/NMOS widths and measuring
the respective propagation delays.

Next, by using a new circuit with different load capacitance, propagation delays and approximating functions were used to find the resistance values.

An inverter circuit with no load capacitor was then implemented. Since $R_N$ was already known, the propagation delay would be entirely due to the inverter's capacitance.

Lastly, a circuit was created with two chained inverters and the propagation delay was measured between them: a result of the gate capacitance of the second inverter,
which can be found in a similar manner to the previous steps.

All of the circuits are pictured in the results, along with the transient analyses of each.

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

![Transient Analysis of Schematic from first circuit](2.1\ Transient.png)

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

![Transient Analysis of Schematic from Second Circuit](2.2\ Transient.png)

\pagebreak

### Find $C_D$

![Schematic used to find $C_D$ for Part (3)](2.3\ Inverter\ Schematic.png)

The output capacitor was removed in this step. This caused the propagation delay to be solely a result of the drain capacitance of the inverter. Since $R_N$ is already known,
the capacitance can be determined with simple algebra. Behold!

$t_{PLH} = 50.1026ns - 50.0015ns = 0.1011ns$

$t_{PHL} = 100.0592ns - 100.0005ns = 0.0587ns$

$C_D = \frac{t_{PLH}}{0.69*R_N} = 13.6fF$

Since $C_D$ is for both $W_n$ and $W_p$, however, it must be expressed in terms of
$C'_D = \frac{fF}{\mu m}$

$C'_D = \frac{C_D}{W_n + W_p} = \frac{13.6fF}{3\mu m} = 4.53fF/\mu m$

![Transient Analysis of Schematic from Third Circuit](2.3\ Transient.png)

\pagebreak

### Find $C_G$

![Schematic used to find $C_G$ for Part (4)](2.4\ Inverter\ Schematic.png)

Another inverter was added as a "load capacitor" for the first inverter. The result of this configuration is that the circuit's propagation delay is caused by the gate capacitance of the second inverter.
Again, the capacitance can be determined using measured delays and previously known values.

$t_{PLH} = 54.3188ns - 50.0016ns = 4.3172ns$

$t_{PHL} = 103.0953ns - 100.0004ns = 3.0949ns$

$C_G = \frac{t_{PLH}}{0.69*R_N} = 581.2fF$


![Transient Analysis of Schematic from Fourth Circuit](2.4\ Transient.png)

\pagebreak

# Conclusion

This experiment allowed for a visual way to understand propogation delays, and the effect of varying capacitance,
width, and setup of the transistors on the output voltage.  For example, propagation delays were incredibly helpful in
determining internal capacitance and resistance of the transistors.  In addition, seeing how each component varies the
results in different ways deepens knowledge of how to manipulate these components to make specific design choices and
troubleshoot results that need to be adjusted.

While the results may not have been entirely accurate due to actual transistors being less set in stone, they are very useful
because the actual building of the circuits designed above would only have some variance.


