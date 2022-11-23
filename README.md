# Software environments

Deployment steps
 - clone spack `git clone https://github.com/spack/spack.git`
 - enable spack `source enable-spack`
 - srun -N2 -n8 --partition=nvgpu spack -e ./env-spec/core install -j16
 - install gcc-11.3.0 view `spack -e  ./env-spec/gcc-11.3.0/ install`
 - install nvhpc-22.9 `srun -N1 --partition=nvgpu spack -e . install -j64`



 spack compiler find $(spack find --format {prefix.bin} gcc@11)
