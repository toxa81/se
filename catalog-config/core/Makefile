include ../../make.inc

# base name of the folder
se-name=$(shell basename $(CURDIR))

all:
	SPACK_USER_CONFIG_PATH=$(CURDIR) srun -N1 -n4 -c16 --partition=nvgpu $(SPACK) -e . install
