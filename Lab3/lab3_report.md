% ECEE 434 Lab #3 - Logic Gates
% Liz MacLean & Carl Anderson
%

\pagebreak

# Introduction & Background

This lab was designed with the intention of giving students a deeper understanding of
worst case scenarios and propagation delays of NMOS and PMOS transistors.  For this
experiment, students were asked to create three logic gates, specifically a NAND, NOR,
and XOR.  These were then assessed for the worst case scenario, or the scenario where the
least number of transistors were shut off.  Once determined, the equivalent resistances of
these scenarios for both the pull down and pull up networks would be found, and evaluated
in order to get equivalent rising and falling propagation delays, under 1 nanosecond.

\pagebreak

# Procedure

The goal of this lab is to have the rising and falling propagation delays be equivalent.
Since we are adjusting the size of the transistors for this design requirement to be true,
the most straightforward way of calculating them is using the propagation time equations.

The schematic diagrams shown below only display the gate itself. The load capacitor and input waves 
were added to the main schematic (not shown) where the responses of the circuit were measured. 

$$t_{PHL} = 0.69*R_n*C_{load}$$

$$t_{PLH} = 0.69*R_p*C_{load}$$

Based off of these equations, the only unknowns are the resistance values for the
transistors, $R_N$ and $R_P$.

$$R_N = \frac{12.5}{(W/L)_n}$$

$$R_P = \frac{30}{(W/L)_p}$$

Each circuit had its own worst case scenario that affected the equivalent resistances of the pull
up and pull down networks.

\pagebreak

## NAND Gate

For the NAND gate (Fig. 1) the worst case scenario was when only one PMOS
transistor was on, and two NMOS transistors were on.  Thus, in order for both networks to have
equivalent propagation delays and equivalents resistances, the equivalent resistances of the pull up
and pull down worst case networks had to be set to each other, as opposed to the best case scenario
resistances.  For the NAND circuit, this would be:

$$R_P = 2R_N$$


After setting $R_n$ equal to $R_p$ so that the $t_{PLH}$ and $t_{PHL}$ values would be equivalent,
the ratio of p to n for the NAND gate was:

$$p = 1.2n$$

Since the default width for the transistors in Cadence is $1.5\mu m$, that value was chosen for
the n-type transistor, and then p was calculated to be $1.8\mu m$.

![NAND Gate Schematic](NANDGate.png)

\pagebreak

## NOR Gate

For the NOR gate (Fig. 2), the worst case scenario was when two PMOS transistors were on, and one
NMOS transistor was on.  When the equivalent resistances were set to eachother, the resultant
equation was as follows:

$$2R_P = R_N$$


After setting $R_n$ equal to $R_p$ so that the $t_{PLH}$ and $t_{PHL}$ values would be equivalent,
the ratio of p to n for the NOR gate was:

$$p = 4.8n$$

Since the default width for the transistors in Cadence is $1.5\mu m$, that value was chosen for
the n-type transistor, and then p was calculated to be $7.2\mu m$.

![NOR Gate Schematic](NORGate.png)

\pagebreak

## XOR Gate

The worst case scenario for the XOR gate (Fig. 3) is similar to that of the inverter, where the number
of transistors in the pull up network were equivalent to the number of transistors in the pulldown network.
When the equivalent resistances were set to eachother, the resultant
equation was as follows:

$$2R_P = 2R_N$$

Which can be simplified to $2R_P = 2R_N$. After setting $R_n$ equal to $R_p$ so that the $t_{PLH}$
and $t_{PHL}$ values would be equivalent, the ratio of p to n for the NOR gate was:

$$p = 3.6n$$

Since the default width for the transistors in Cadence is $1.5\mu m$, that value was chosen for
the n-type transistor, and then p was calculated to be $3.6\mu m$.


![XOR Gate Schematic](XORGate.png)

\pagebreak

# Results

## NAND Gate

Using the parameters listed above in the procedure, the NAND gate transistors were set up with width ratios to still achieve minimum size.
The output waveform can be seen below, and the propagation delays were measured as follows: 

$$t_{PLH} = 26.11 - 25.001 = 1.109ns$$
$$t_{PHL} = 101.57 - 100.1 = 1.47ns$$
$$t_p = \frac{1}{2}(1.109 + 1.47) = 1.2895ns$$

![NAND Gate Waveform](NAND_wave.png)


## NOR Gate

Similar to the NAND gate, the transistor parameters were set up to match the ratio found above. The propagtion delays in this circuit 
could not reach the 1ns specification due to limitations in the transistor sizing. 

$$t_{PLH} = 75.5 - 75 = 0.5ns$$
$$t_{PHL} = 100.48 - 100.06 = 0.42ns$$
$$t_p = \frac{1}{2}(0.5 + 0.42) = 0.46ns$$

![NOR Gate Waveform](NOR_wave.png)

## XOR Gate

For the XOR gate, transistor parameters were set up according to ratios found in the Procedure section. 

$$t_{PLH} = 25.97 - 25.001 = 0.97ns$$
$$t_{PHL} = 76.9 - 75.3  = 1.6ns$$
$$t_p = \frac{1}{2}(0.97 + 1.6) = 1.285ns$$

![XOR Gatea Waveform](XOR_wave.png)

\pagebreak

# Conclusion

Overall the design goals of the experiment were met. However, in some of the cases (e.g. NOR gate), the 1ns design specification could not be achieved.
This is mostly due to limitations in the channel width of the transistors. 
