# Large-Scale Linear Elasticity System in 3D

## Lame Coefficients
lambda = 3.10345e+08
    mu = 3.44828e+07

## User Input
mpiexec.hydra -genvall /share/home/zhaogang/zg/FreeFEM/New_Version/FreeFem-sources/src/mpi/FreeFem++-mpi elasticity-3d-PETSc.edp -v 0 -refi 3 -ksp_view -ksp_monitor_true_residual -log_view

## PETSc Option Table Entries
-pc_type gamg -pc_gamg_threshold 0.02 -pc_gamg_esteig_ksp_type cg
-mg_levels_esteig_ksp_type cg -ksp_type cg -ksp_rtol 1e-8 -ksp_converged_reason

## Performance Brief
 CPU time:             444975.44 sec
 Max Memory:           3867932 MB
 Average Memory:       2083764.88 MB
 Max Swap:             2 MB
 Max Processes:        1184
 Max Threads:          2336

 Domain:               [0, 10] x [0, 1] x [0, 1]
 # of Elements:        53,084,160
 # of Dofs:            214,665,987 ([P2, P2, P2])
 # of Procs:           1152
 
 # of iterations:      46
 MatPtAPSymbolic:      81.059 sec
 MatPtAPNumeric:       100.64 sec
 KSPSolve:             280.99 sec
 PCSetUp:              210.25 sec

ttttttttttttttttttttttttttttttttttttttttttttt
FreeFEM elapsed time is 342.128 s
ttttttttttttttttttttttttttttttttttttttttttttt

---------------------------------------------- PETSc Performance Summary: ----------------------------------------------

/share/home/zhaogang/zg/FreeFEM/New_Version/FreeFem-sources/src/mpi/FreeFem++-mpi on a  named c6u22n04 with 1152 processors, by zhaogang Thu Oct 15 12:59:04 2020
Using Petsc Release Version 3.13.5, Sep 01, 2020 

                         Max       Max/Min     Avg       Total
Time (sec):           3.892e+02     1.001   3.890e+02
Objects:              1.436e+03     1.001   1.434e+03
Flop:                 7.011e+10     2.390   4.506e+10  5.191e+13
Flop/sec:             1.802e+08     2.390   1.158e+08  1.334e+11
MPI Messages:         2.616e+05    11.093   1.045e+05  1.203e+08
MPI Message Lengths:  4.333e+09    10.490   1.728e+04  2.079e+12
MPI Reductions:       2.263e+03     1.000

Flop counting convention: 1 flop = 1 real number operation of type (multiply/divide/add/subtract)
                            e.g., VecAXPY() for real vectors of length N --> 2N flop
                            and VecAXPY() for complex vectors of length N --> 8N flop

Summary of Stages:   ----- Time ------  ----- Flop ------  --- Messages ---  -- Message Lengths --  -- Reductions --
                        Avg     %Total     Avg     %Total    Count   %Total     Avg         %Total    Count   %Total
 0:      Main Stage: 3.8903e+02 100.0%  5.1909e+13 100.0%  1.203e+08 100.0%  1.728e+04      100.0%  2.256e+03  99.7%

------------------------------------------------------------------------------------------------------------------------
See the 'Profiling' chapter of the users' manual for details on interpreting output.
Phase summary info:
   Count: number of times phase was executed
   Time and Flop: Max - maximum over all processors
                  Ratio - ratio of maximum to minimum over all processors
   Mess: number of messages sent
   AvgLen: average message length (bytes)
   Reduct: number of global reductions
   Global: entire computation
   Stage: stages of a computation. Set stages with PetscLogStagePush() and PetscLogStagePop().
      %T - percent time in this phase         %F - percent flop in this phase
      %M - percent messages in this phase     %L - percent message lengths in this phase
      %R - percent reductions in this phase
   Total Mflop/s: 10e-6 * (sum of flop over all processors)/(max time over all processors)

------------------------------------------------------------------------------------------------------------------------
Memory usage is given in bytes:

Object Type          Creations   Destructions     Memory  Descendants' Mem.
Reports information only for process 0.

--- Event Stage 0: Main Stage

              Matrix   275            275    693302224     0.
      Matrix Coarsen     9              9         5724     0.
   Matrix Null Space     1              1          696     0.
         Vec Scatter    65             65        52000     0.
              Vector   736            736    191806640     0.
           Index Set   204            204      1529224     0.
   Star Forest Graph    74             74        82880     0.
       Krylov Solver    30             30        50712     0.
      Preconditioner    21             21        20124     0.
              Viewer     3              2         1680     0.
========================================================================================================================
Average time to get PetscTime(): 1.19209e-07
Average time for MPI_Barrier(): 1.55926e-05
Average time for zero size MPI_Send(): 4.12493e-06

-----------------------------------------
