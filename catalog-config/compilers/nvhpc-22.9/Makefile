include ../../../make.inc

# base name of the folder
se-name=$(shell basename $(CURDIR))

all:
	SPACK_USER_CONFIG_PATH=$(SE_ROOT)/catalog/gcc-11.3.0 srun -N1 -n4 -c16 --partition=nvgpu $(SPACK) -e . install -j16
	SPACK_USER_CONFIG_PATH=$(CURDIR) $(SPACK) compiler find $$($(SPACK) -e . find --format {prefix}/Linux_x86_64/22.9/compilers/bin/ nvhpc)
	cp ./linux/compilers.yaml $(SE_ROOT)/catalog/$(se-name)
