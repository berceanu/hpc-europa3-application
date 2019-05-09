# Laser-wakefield radiation sources as diagnostic tools  

## 1. Background information[^1]

### 1.1. Status of my research activities

$$i \partial_t \psi = H \psi$$

### 1.2. Project objectives

- LWFA in regime non-lineare da gas-jet di 3mm, con densità 1-3*10^18, energia del laser 3 J, spot rms 7um, durata 30fs, lunghezza d'onda 800nm, I=3*10^19 W/cm^2, a0=3.4

- LWFA in regime non-lineare da capillare di 3-10 cm, con densità 3-7*10^17, energia del laser 3 J, spot rms 7um, durata 30fs, lunghezza d'onda 800nm, I=3*10^19 W/cm^2, a0=3.4

### 1.3. Contribution to research field development
*beam profile monitor* 
params: He gas-jet target, bubble regime: 1 J energy, 30 fs (FWHM), 5 $\mu$m
rms spot, plasma density $n = (2 \pm 0.2) \times 10^19$ cm${}^{-3}$.
*emittance*
params: He gas-jet target, 1 J energy, 30 fs (FWHM), 10 $\mu$m diameter
focus, $a_0 = 4.4$, $n_e = (8 \ pm 1) \times 10^{18}$ cm${}^{-3}$, acceleration length of 1.2 mm. Estimated bubble radius is $R = 9\, \mu$m.

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

On *week 1*, I will ...

[^1]: The whole proposal should contain around 16k characters, or roughly 5 pages.
[^2]: Justify the necessity to *simulate larger systems* for the problem being
studied and demonstrate that the resources to which you currently have access are
*inadequate* for this.