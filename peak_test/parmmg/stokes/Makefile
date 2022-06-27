PROJECT = stokes-parmmg-PETSc-3d.edp
FFMPIRUN = ff-mpirun
NPROCS = 4

default:
	$(FFMPIRUN) -np $(NPROCS) $(PROJECT) -v 0 -view 1

o:
	@vim $(PROJECT)

m:
	@vim Makefile

v:
	@paraview stokes-cavity_4.pvd

clean:
	-@rm -rf *.vtu *.pvd *.pvtu

.PHONY: default clean
