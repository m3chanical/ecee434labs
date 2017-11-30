% ECEE 434 Lab #5 - Positive/Negative Flip-flop
% Liz MacLean & Carl Anderson
%

\pagebreak

# Introduction & Background

The previous experiment introduced the use of D-latches, how they operate,
and their limitations. This experiment introduces a different kind of
latch called a flip-flop. A flip-flop differs from a latch in that it
registers data while the clock is rising, rather than when it is high. A negative
version can also be created.

The purpose of this experiment is to build a positive flip-flop and
characterize it. The D-latch from the previous experiment,
and a negative D-latch, is used in this one to create the new circuit.

In order to characterize the positive flip-flop two specific measurements
will be considered. The first is "setup-time." Setup-time
is defined as the minimum amount of time before the clock's leading edge
that the data must be stable for it to be latched correctly.
Data that is switched in violation of the setup-time parameter will not have
time to propagate through the circuit.

The second parameter is called "hold-time." Hold-time is defined as the
minimum amount of time after the clock's leading edge during which
the data must be stable. The effect is similar to the setup-time.

\pagebreak

# Procedure

In order to successfully create a positive D flip-flop that saved
data on the rising edge of the clock, two D-latches, one negative
and one positive had to be combined.  The positive D-latch was created
in the previous lab, and the negative D-latch was essentially the same,
except that there was an additional inverter used.  Then, these two components
were connected in series, and the outputs from both latches were recorded.  The
output of the second latch (and thus the output of the combination of the two)
is expected to have the behavior of a positive D flip-flop.  The hold and setup
times were then measured by measuring the time between when the clock
changed, and the data line rose or fell.

\pagebreak

# Results

![Schematic used for Positive Flip-flop](d_flip_flop_schematic.png)

The overall circuit can be seen in Fig. 1. Before this circuit was built,
first a negative latch was created using the D-latch from the previous
experiment. However, the difference from previous was the addition
of an inverter to the input of the D-latch within the circuit. This is
not seen in the schematic, because it was built in to the symbol. The
operation of the Negative D-latch can be seen in Fig. 2 on the Qm graph.
Only when the clock is negative will the data be accepted into the circuit, which
is reflected in the output plot.

![Output plot of Positive Flip-flop. CLK, D, Qm, Qs, shown (listed as shown from top to bottom).](d_flip_flop_output.png)

Further, the operation of the D-flip-flop can be seen at the Qs output. The output
data changes only on the leading edge of the input clock. Otherwise, the output is constant.

The setup and hold times were found as follows, using the methods mentioned in the procedure:

$$setup time = $$
$$hold time = $$


\pagebreak

# Conclusion

Overall, the results were correct with respect to initial behavioral assumptions.
For the negative latch, the output data, Qm, only changed when the clock was negative, and
the output data of the entire schematic, Qs, only changed on the rising edge of the clock.
Not only did this exercise with latches assist with a deeper understanding of how latches work,
but it also established a clear difference between latches and flip flops through interactive
methods.  In the future, it would be interesting to create a negative D flip-flop, as well
as play with the order of the latches by placing them in parallel, or in opposite series from this example.
This experiment is also useful because it starts to introduce students to ways to
manipulate signals as desired.  For example, if a device uses chip select for certain functionality, and
the user wants to access each of these functionalities at different times, a flip flop may be a useful way
to change this data line.  It is also important to appreciate the measuring of the setup and hold times, because
without those values being known, a student may erroneously try to change the data line too soon, or do some other
change that will corrupt the stored data.  With these values, measures can be taken to prevent future invalid or
incorrect outputs.



