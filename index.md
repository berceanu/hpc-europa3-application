# Laser-wakefield radiation sources as diagnostic tools  

## 1. Background information[^1]

### 1.1. Status of my research activities

$$i \partial_t \psi = H \psi$$

### 1.2. Project objectives

- LWFA in regime non-lineare da gas-jet di 3mm, con densità 1-3*10^18, energia del laser 3 J, spot rms 7um, durata 30fs, lunghezza d'onda 800nm, I=3*10^19 W/cm^2, a0=3.4

- LWFA in regime non-lineare da capillare di 3-10 cm, con densità 3-7*10^17, energia del laser 3 J, spot rms 7um, durata 30fs, lunghezza d'onda 800nm, I=3*10^19 W/cm^2, a0=3.4

### 1.3. Contribution to research field development

*Parameters for beam monitor paper:*
Plasma with nₚ=2.0e+19 cm**(-3) (1.15e-02 nc), ωₚ=0.252 1/fs, kₚ=0.842 1/µm, λₚ=7.5 µm, Ewb=430.0 MV/mm
Pc=1.5 TW, Ldeph=0.24 mm, Ldepl=0.78 mm, ΔE=375.7 MeV over Lacc=1.00 mm
for laser beam with w0=10.0 µm (FWHM=11.8 µm), zᵣ=0.39 mm, λL=0.80 µm, kL=7.854 1/µm, ωL=2.355 1/fs, ɛL=1.0 J, τL=30.0 fs, P₀=31.3 TW
I₀=2.0e+19 W/cm**2, a₀=3.1, E₀=1.2e+04 MV/mm

*Parameters for emmitance paper:*
Plasma with nₚ=6.1e+18 cm**(-3) (3.52e-03 nc), ωₚ=0.140 1/fs, kₚ=0.466 1/µm, λₚ=13.5 µm, Ewb=238.3 MV/mm
Pc=4.8 TW, Ldeph=1.70 mm, Ldepl=2.55 mm, ΔE=294.9 MeV over Lacc=1.18 mm
for laser beam with w0=6.9 µm (FWHM=8.2 µm), zᵣ=0.19 mm, λL=0.80 µm, kL=7.854 1/µm, ωL=2.355 1/fs, ɛL=1.0 J, τL=30.0 fs, P₀=31.3 TW
I₀=4.1e+19 W/cm**2, a₀=4.4, E₀=1.8e+04 MV/mm
N=1.9e+09 electrons, Q=300.1 pC, η=0.089

**Frascati future exp [...]**
*Parameters for He gas jet:*
Plasma with nₚ=3.0e+18 cm**(-3) (1.72e-03 nc), ωₚ=0.098 1/fs, kₚ=0.326 1/µm, λₚ=19.3 µm, Ewb=166.6 MV/mm
Pc=9.9 TW, Ldeph=4.38 mm, Ldepl=5.22 mm, ΔE=460.6 MeV over Lacc=3.00 mm
for laser beam with w0=15.6 µm (FWHM=18.3 µm), zᵣ=0.95 mm, λL=0.80 µm, kL=7.854 1/µm, ωL=2.355 1/fs, ɛL=3.0 J, τL=30.0 fs, P₀=93.9 TW
I₀=2.5e+19 W/cm**2, a₀=3.4, E₀=1.4e+04 MV/mm

*Parameters for H capillary:*
Plasma with nₚ=3.0e+17 cm**(-3) (1.72e-04 nc), ωₚ=0.031 1/fs, kₚ=0.103 1/µm, λₚ=61.0 µm, Ewb=52.7 MV/mm
Pc=98.7 TW, Ldeph=138.49 mm, Ldepl=52.22 mm, ΔE=2427.6 MeV over Lacc=50.00 mm
for laser beam with w0=15.6 µm (FWHM=18.3 µm), zᵣ=0.95 mm, λL=0.80 µm, kL=7.854 1/µm, ωL=2.355 1/fs, ɛL=3.0 J, τL=30.0 fs, P₀=93.9 TW
I₀=2.5e+19 W/cm**2, a₀=3.4, E₀=1.4e+04 MV/mm
Scaling laws valid up to a0c=42.6


## 2. Case for HPC-Europa3 funding

### 2.1. Research benefits of accessing HPC-Europa systems[^2]

![experimental setup](https://raw.githubusercontent.com/berceanu/hpc-europa3-application/master/images/exp_setup.png?token=ABBTTGTHLCCLW345XORQSPS42GSS2)

### 2.2. Research benefits of interacting with my local scientific host

## 3. Weekly-based project workplan

### 3.1. List of specific objectives and approximate timeline

Objective | Timeline
----------|---------
fbpic parameter scan | week 1
task | week 2
task | week 3
task | week 4
task | week 5
task | week 6
task | week 7
task | week 8

- full-scale `PIConGPU` simulation
- scan of the parameter space via `fbpic` (envelope model, cylindrical symmetry)
- post-processing trajectories to extract betatron spectrum
- estimation using the scaling laws (Lu for electrons and Thomas for betatron)
- installation of `fbpic` and `PIConGPU` on the cluster
- `PIConGPU` test runs
- convergence testing
- data analysis
- writing up the results
- reproduce previour results (2 published papers)
- simulations for future ELI experiments

[A. Curcio et. al, Appl. Phys. Lett. 111, 133105 (2017)]
[A. Curcio et. al, Phys. Rev. Accel. Beams 20, 012801 (2017)]

On *week 1*, I will ...

[^1]: The whole proposal should contain around 16k characters, or roughly 5 pages.
[^2]: Justify the necessity to *simulate larger systems* for the problem being
studied and demonstrate that the resources to which you currently have access are
*inadequate* for this.