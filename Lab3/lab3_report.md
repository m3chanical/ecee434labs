% ECEE 434 Lab #3 - Logic Gates
% Liz MacLean & Carl Anderson
%

\pagebreak

# Introduction & Background


\pagebreak

# Procedure

The goal of this lab is to have the rising and falling propagation delays be equivalent.
Since we are adjusting the size of the transistors for this design requirement to be true,
the most straightforward way of calculating them is using the propagation time equations.

$$t_{PHL} = 0.69*R_n*C_{load}$$

$$t_{PLH} = 0.69*R_p*C_{load}$$

Based off of these equations, the only unknowns are the resistance values for the
transistors, $R_N$ and $R_N.

$$R_N = \frac{12.5}{(W/L)_n}$$

$$R_P = \frac{30}{(W/L)_p}$$

Each circuit had its own worst case scenario that affected the equivalent resistances of the pull
up and pull down networks.  For the NAND gate, the worst case scenario was when only one PMOS
transistor was on, and two NMOS transistors were on.  Thus, in order for both networks to have
equivalent propagation delays and equivalents resistances, the 

After setting $R_n$ equal to $R_p$ so that the $t_{PLH}$ and $t_{PHL}$ values would be equivalent,
the ratio of p to n was:

$$p = 2.4n$$

Since the default width for the transistors in Cadence is $1.5\mu m$, that value was chosen for
the n-type transistor, and then p was calculated to be $3.6\mu m$.

\pagebreak

# Results


\pagebreak

# Conclusion

