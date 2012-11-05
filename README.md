smpICE
======

A kind of software In-Circuit Emulator running on SMP architecture.

1) Concept:

1.1) With the advent of quad-core ARM, to use 1 CPU (Debug Kernel) to debug Linux running on the rest 3 CPUs (Production Kernel).
-- CONFIG_NR_CPUS=4   =>   CONFIG_NR_CPUS=3

1.2) This is AMP + SMP design. 
-- 3 CPUs and the 4th CPU runs in the asynchronous way, while 3 CPUs work the SMP way.

1.3) Production kernel (on 3 CPUs) and Debug kernel (on 4th CPU) running concurrently.
-- Debug kernel access ARM H/W resources via CoreSight interface.