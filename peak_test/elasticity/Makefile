PROJECT = elasticity-3d-PETSc.edp

FreeFEM = /share/home/zhaogang/zg/FreeFEM/New_Version/FreeFem-sources/src/mpi/FreeFem++-mpi

run: $(PROJECT)
	bsub -J mywork -q batch -R "span[ptile=36]" -n 1152 -e err.dat -o out.dat "mpiexec.hydra -genvall $(FreeFEM) $< -v 0 -nn 10 -refi 3 -ksp_view -ksp_monitor_true_residual -log_view"

o:
	vim $(PROJECT)

m:
	vim Makefile

clean:
	-rm -rf Database
	-rm -rf err.dat
	-rm -rf out.dat
	-rm -rf core.*

.PHONY: default clean
