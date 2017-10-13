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
    * Simulate and inverter with matched PMOS/NMOS widths and measure the respective propagation delays.

\pagebreak

# Results

### Verify Strength of NMOS with respect to PMOS

$t_{PLH} = 25.141ns - 20.001ns = 5.140ns$

$t_{PHL} = 30.07ns - 30.001ns = 0.069ns$

### Find $R_n$

Verify ratios. Find $R_n$ using $t_p$. Profit. 

$t_{PLH} = 56.6188ns - 50.0015ns = 6.6173ns$

$t_{PHL} = 103.7145ns - 100.0005ns = 3.714ns$

### Find $C_D$

$t_{PLH} = 50.1026ns - 50.0015ns =$

$t_{PHL} = 100.0592ns - 100.0005ns =$

### Find $C_G$

$t_{PLH} = 54.3188ns - 50.0016ns =$

$t_{PHL} = 103.0953ns - 100.0004ns =$


\pagebreak

# Conclusion

Conclusion? We did some totally sick shit, bro.
