include ../../make.inc

# base name of the folder
se-name=$(shell basename $(CURDIR))

all:
	SPACK_USER_CONFIG_PATH=$(CURDIR) srun -N1 -n4 -c16 --partition=nvgpu $(SPACK) -e . spec -I
#	SPACK_USER_CONFIG_PATH=$(CURDIR) srun -N1 -n4 -c16 --partition=nvgpu $(SPACK) -e . install
#	SPACK_USER_CONFIG_PATH=$(SE_ROOT)/catalog/core srun -N1 --partition=nvgpu $(SPACK) -e . spec -I

