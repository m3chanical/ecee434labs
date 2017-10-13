% ECEE 434 Lab 2 - Mosfet Inverter Propagation Delay
% Liz MacLean & Carl Anderson
%

# Introduction & Background

Capacitance is an inherent property in transistors that can be used to determine other properties of the transistor. 
The experiment performed involved simulating a CMOS inverter and measuring the output to determine the propagation delay ($t_{PHL}$ and $t_{PLH}$) 
of the circuit. This information was then used to determine the NMOS/PMOS equivalent resistance, and the Gate and Drain capacitances. 

The lab required further use of Cadence Virtuoso to modify several parameters and components, build circuits, and simulate the circuits. 

\pagebreak 

# Procedure

This experiment consisted of four distinct but related parts. 

1. Verifying the strength of an NMOS transistor with respect to a PMOS. 
    * Simulate an inverter with matched PMOS/NMOS widths and measure the respective propagation delays.
    * $t_p$ can be found with the above propagation delays, and $R_n$ can be calculated.
2. Find $C_D$ using some cool ass techniques.
\pagebreak

# Results

### Verify Strength of NMOS with respect to PMOS

$t_{PLH} = 25.141ns - 20.001ns = 5.140ns$

$t_{PHL} = 30.07ns - 30.001ns = 0.069ns$

### Find $R_n$

$R_n$ can be found 

$t_{PLH} = 56.6188ns - 50.0015ns = 6.6173ns$

$t_{PHL} = 103.7145ns - 100.0005ns = 3.714ns$

The value of $t_p$ can be found by averaging the two propagation delays found above, shown as follows: 

$$t_p = \frac{t_{PLH} + t_{PHL}}{2} = \frac{6.6173 + 3.714}{2} = 5.16565ns$$

$R_n$ can be found by algebraically manipulating the following the equation:

$$t_p = 0.69*R_n*C$$

$$R_n = 14972.9\Omega$$

Where C is the value of the capacitor on the output of the inverter. 

### Find $C_D$

$t_{PLH} = 50.1026ns - 50.0015ns =$

$t_{PHL} = 100.0592ns - 100.0005ns =$

### Find $C_G$

$t_{PLH} = 54.3188ns - 50.0016ns =$

$t_{PHL} = 103.0953ns - 100.0004ns =$


\pagebreak

# Conclusion


