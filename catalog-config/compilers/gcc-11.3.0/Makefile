include ../../../make.inc

# base name of the folder
se-name=$(shell basename $(CURDIR))

all:
	# build and install all packages of the environment
	srun -N1 -n4 -c16 --partition=nvgpu $(SPACK) -e . install -j16
	# detect newly installed gcc
	SPACK_USER_CONFIG_PATH=$(CURDIR) $(SPACK) compiler find $$($(SPACK) -e . find --format={prefix.bin} gcc)
	# copy config of the compiler
	cp ./linux/compilers.yaml $(SE_ROOT)/catalog/$(se-name)
	## make the config of the upstream
	#echo 'upstreams:' &> upstreams.yaml
	#echo '  spack-root-instance:' >> upstreams.yaml
	#echo '    install_tree: $(SE_ROOT)/catalog/$(se-name)' >> upstreams.yaml
	#cp ./upstreams.yaml $(SE_ROOT)/catalog/$(se-name)
