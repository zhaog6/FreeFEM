PROJECT = test.edp

FreeFEM = /share/home/zhaogang/zg/FreeFEM/New_Version/FreeFem-sources/src/mpi/FreeFem++-mpi

run: $(PROJECT)
	bsub -J mywork -q batch -R "span[ptile=36]" -n 72 -e err.dat -o out.dat "mpiexec.hydra -genvall $(FreeFEM) $< -v 0 -nn 32"

o:
	vim $(PROJECT)

m:
	vim Makefile

clean:
	-rm -rf Database
	-rm -rf err.dat
	-rm -rf out.dat

.PHONY: default clean
