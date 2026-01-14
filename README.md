# TDEP.jl
Temperature Dependent Effective Potential Bindings in Julia. 

See my other lattice dynamics package [here](https://github.com/ejmeitz/LatticeDynamicsToolkit.jl) for further functionality.

## Quick Start
----------------------------------------------
To install this package (and TDEP!) run in the Julia REPL:
```julia
using Pkg
Pkg.add(url = "https://github.com/ejmeitz/TDEP.jl.git")
```

```julia
using TDEP

efc = ExtractForceConstants(secondorder_cutoff = 2.0)
rundir = "/home/emeitz/tests/TDEP/tdep_jl"
execute(efc, rundir)
```

MPI is also supported. Unless otherwise specified, a comptabile MPI is automaticalled downloaded. To use it simply specify the number of cores when calling `execute`
```julia
ncores = 10
execute(efc, rundir, ncores)
```
It is possible to use a local MPI and/or a locally built TDEP. I will write docs on how to do that soon!

----------------------------------------------

## Extensions:

There is a package extension for [Molly.jl](https://github.com/JuliaMolSim/Molly.jl) to run molecular dynamcis simulations. Examples can be found in the `scripts` directory Two algorithms are implemented to date:
- Dataset generation for fitting force constants
- Thermodynamic integration with a harmonic crystal reference

Both of these should work, but I have not extensively tested them. My focus is on the [LatticeDynamics.jl](https://github.com/ejmeitz/LatticeDynamicsToolkit.jl) package. This package implements much of lattice dynamics from scratch and uses TDEP routines when convenient. Report any issues please.