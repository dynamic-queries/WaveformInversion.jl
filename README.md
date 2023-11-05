# WaveformInversion.jl

## Simple FWI
A generic waveform inversion pipeline is shown below.

![fwi](https://github.com/dynamic-queries/WaveformInversion.jl/assets/81833704/706114de-8a87-4d80-b3a7-72261b6b3ad7)

Here, each of these blocks are investigated/implemented separately. 

- Typical compressors include conventional transforms such as KL expansions, wavelet decompositions, tensor decompositions and the like.
- Three physical models for wave propagation are considered - acoustic, elastic, seismic wave equations.
- Numerical solvers apposite to each of these equations are implemented separately.
- In general, sampling is informed by experiment. But the converse is also true. Here, optimal sampling algorithms are implemented for this purpose.
- Derivatives of the solvers with respect to the reduced inputs are computed to enable optimization.
- Optimization.jl, Turing.jl is relied upon to enable optimization.

## Multifidelity FWI

In general, inference with more than one model is much more robust than inference with a single model. This drives the need for multifidelity optimization.

![fiw2](https://github.com/dynamic-queries/WaveformInversion.jl/assets/81833704/a42e4e14-75d3-4156-9d10-348ca9bf8c53)

Here, different decision policies are implemented that correspond to the solvers that are implemented. Features from simple FWI are repurposed.
