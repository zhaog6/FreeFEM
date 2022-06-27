PROJECT = driven-cavity-flow.edp
FFMPIRUN = ff-mpirun
NPROCS = 4
FFFLAGS = -v 0

default:
	@$(FFMPIRUN) -np $(NPROCS) $(PROJECT) $(FFFLAGS)

o:
	@vim $(PROJECT)

m:
	@vim Makefile

clean:
	-@$(RM) *.pvd *.pvtu *.vtu

.PHONY: default clean
