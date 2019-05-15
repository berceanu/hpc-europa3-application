---
title: Laser-wakefield radiation sources as diagnostic tools
author: A. C. Berceanu
date: 13 May 2019
---

Document source on
[GitHub](https://github.com/berceanu/hpc-europa3-application/blob/master/index.md).

## 1. Background information

### 1.1. Status of my research activities

I completed my PhD in the field of theoretical condensed matter physics at
Universidad Autónoma de Madrid (Spain) and am currently a postdoctoral
researcher at Extreme Light Infrastructure - Nuclear Physics (Romania). In my
new role, I am focusing on theoretical/computational aspects of high power
laser-plasma interaction, in particular accelerating particles to
megaelectronvolt energies using plasma wakefields, with the goal of obtaining
high-brilliance/high-energy secondary radiation sources with various
applications in medical imaging, as well as fundamental research.

Tajima and Dawson’s seminal 1979 paper [Phys. Rev. Lett. 43 (4): 267–70,
(1979)] first introduced the idea that particles could be accelerated to high
energies using laser-plasma interaction instead of the conventional RF
accelerators. The main concept was that the plasma would be perturbed by the
laser and act as a transformer, conveying the laser energy to the particles.
Subsequent experimental developments, in particular the chirped pulse
amplification lead to the advent of high-power lasers, which brought Tajima and
Dawson’s idea to reality. The main advantage of using a plasma instead of a
conventional accelerator is that the electric field gradients it can withstand
are about three orders of magnitude higher than the breakdown fields of an RF
cavity. This allows one to use much shorter acceleration distances, on the
order of centimeters (instead of kilometers) and achieve similar energies, with
the current state of the art of a few GeV. This acceleration process goes by
the name of laser wakefield acceleration (LWFA), due to the wake that the laser
leaves behind it in the plasma. A breakthrough occurred in 2004, when Pukhov
and coworkers [Plasma physics and controlled fusion, 46 (2004)], using
numerical simulations, discovered a new regime of LWFA: the so-called“bubble”
regime, allowing for the first time the production of mono-energetic electron
bunches that approach the quality of those obtained in conventional
accelerators.

This discovery was quickly confirmed by three experiments [Nature 431:541
(2004), Nature 431:535 (2004), Nature 431:538 (2004)]. In the bubble regime,
the laser creates a spherical cavity devoid of electrons behind it, as it
enters the plasma. The size of the cavity is proportional to the plasma
wavelength, and it propagates with a phase velocity equal to the laser group
velocity. There are several ways of injecting electrons from the background
plasma into this cavity, ranging from self-injection (simplest) to ionization
and colliding pulse injection. The bubble is positively charged due to the
background ions, and it has a linear accelerating field along the laser
propagation direction, as well as radial focusing fields, which help keep the
electron bunch emittance low. Under the action of the radial fields, the
injected electrons which are deviated from the propagation axis start to
oscillate around it, emitting synchrotron radiation, technically know as
betatron radiation. The mechanism of radiation emission is similar to what
happens to an electron bunch propagating inside an undulator, with the role of
the undulator played by the background plasma. The betatron spectrum usually
extends to the X-ray spectral region, due to the relativistic Doppler shift
involved.

The method used by Pukhov is a well established numerical approach in the
plasma physics community and goes by the name of “particle-in-cell” (PIC),
being developed in the early 1960’s by Buneman, Dawson, Hockney, Birdsall,
Morse and others. In a nutshell, one models the plasma as a collections of
macro-particles, each of which correspond to thousands of real particles. The
main PIC loop consists of: (1) integrating the relativistic Lorentz-Newton
equations of motion for the macro-particles, (2) interpolating the resulting
charges and currents to the mesh, (3) computing the electromagnetic (EM) fields
on the mesh and (4) interpolating the EM fields to the positions of the
macroparticles. Since we are dealing with around a billion macro-particles in a
typical simulation, and hundreds of thousands of time steps, PIC simulations
require large distributed computational resources, but also provide the most
accurate description of the plasma evolution, short of solving the
6-dimensional Vlasov-Boltzman equations.

### 1.2. Project objectives

The main project objective is using the emitted betatron radiation as a
non-intercepting, single-shot diagnostic tool for the properties of the
accelerated electron bunch. The basic algorithm is described in a recent
publication of the Frascati group [A. Curcio et. al, Appl. Phys. Lett. 111,
133105 (2017)], and, in a nutshell, it amounts to measuring both the electron,
as well as betatron energy spectra and obtaining the (radial) beam profile from
the system's S-matrix. In a related paper [A. Curcio et. al, Phys. Rev. Accel.
Beams 20, 012801 (2017)], the same group reconstructed both the beam profile,
as well as the radial emittance of the electron beam, finally obtaining the
trace-space density of the beam.

Both these experiments we performed using a pure Helium gas jet, with the FLAME
laser [F.G. Bisesto et. al, Nucl. Instrum. Methods Phys. Res. A 909, 452
(2018)] operating at 1 J pulse energy, 30 fs FWHM@intensity pulse duration. The
electrons reached $\sim 300$ MeV energies in an accelerating length $\gtrapprox
1$ mm. These studies used a 1D model, assuming a cylindrically symmetric
electron bunch distribution. Our objective is to extend this work to the 2D
case, allowing one to reconstruct the 2D emittance and spatial bunch profile.
This would require an angularly-resolved measurement of the betatron emission
spectrum and electron energy spectrum, as well as large scale numerical
modelling using the PIC method.

A preliminary experimental setup is shown in the attached image. The laser beam
(red) is focused by the off-axis parabola (OAP) down to a few micrometers spot
size at the entrance of the gas jet. The probe beam is used for interferometric
imaging of the plasma on the CCD camera, and the accelerated electrons are
deflected by a magnetic dipole onto a LANEX screen for spectral measurements.
The emitted betatron radiation (pink) goes through an X-ray scintillator onto
an X-ray CCD which retrieves its spectral information.

![envisaged experimental
setup](https://raw.githubusercontent.com/berceanu/hpc-europa3-application/master/images/exp_setup.png?token=ABBTTGTHLCCLW345XORQSPS42GSS2)

A further goal of the project is to improve the trapping and general properties
of the electron beam. For example, the beam emittance could be improved by
using different injection schemes such as self-truncated ionization injection
[M. Zeng, Physics of Plasmas 21 (3), 030701 (2014)], experimentally
demonstrated in [M. Mirzaie, et. al, Scientific Reports 5, 14659 (2015)] and
[J. P. Couperus et. al, Nature Communications 8 (1) 487 (2017)]. Ionization
injection can be achieved by adding a small percentage of Nitrogen doping to
the Helium gas, and the truncation effect is due to the subsequent
beam-loading. The beam energy could also be increased, leading to a higher
critical energy in the betatron spectrum. One way to do this is by using a
capillary to guide the laser pulse over a propagating distance much longer than
the Rayleigh length, of up to a few centimeters, at a lower plasma density.
Another approach is to optimize the laser and plasma parameters to obtain a
better self-guiding of the laser (above the critical power) inside the gas jet,
leading to an increased propagation distance.

The experimental developments are strongly coupled with large-scale numeric
simulations, which serve a dual purpose. The first one is to guide the choice
of laser (energy, duration, beam profile etc) and plasma (density, profile etc)
parameters for the experimental campaign in order to optimize the accelerated
electron beam's quality and shot-to-shot reproducibility, as well as maximize
its energy. The second purpose of the numeric modelling would be to confront
and interpret the experimental data, leading to new physical insights.

### 1.3. Contribution to research field development

The main deliverable of the project should be a peer-reviewed publication in a
(preferably open access) scientific journal, combining the experimental results
with numerical modelling in order to achieve the main project objectives. We
will also release any data analysis tools and plugins developed in the process
as open source software. The data produced by the large-scale simulations will
also be released as self-documented HDF5/ADIOS files using the [openPMD
standard](https://github.com/openPMD/openPMD-standard) for mesh-based metadata.
If time permits, we will also contribute to the development of the main
particle-in-cell codes used in the production runs.

On the experimental side, we will implement a new technique for resolving
angularly the betatron spectrum emitted by the accelerated electron beam and
extend our previous work to the 2D case. The main task will regard the study of
the geometry and material for a custom X-Ray filter to install in front of the
detector. Despite the homogeneous aluminium foil employed in the last
experimental campaign, we will need an attenuation depending on the transverse
coordinate. In this way, relying on the fact that different material
thicknesses can stop different photon energies, we can reconstruct the betatron
spectrum resolving the angular dependence.

## 2. Case for HPC-Europa3 funding

### 2.1. Research benefits of accessing HPC-Europa systems

My previous HPC experience with particle-in-cell codes includes running
`PIConGPU` on the [HYPNOS](https://www.hzdr.de/db/Cms?pOid=12231&pNid=852) HPC
cluster at the Helmholtz Zentrum Dresden Rossendorf, which comprises of 9
GPU-compute nodes, each equipped with a dual Intel 8-Core Xeon@2.4 GHz CPU, 256
GB RAM and 4 x Nvidia K80 GPU cards. During my access time I was impressed by
the order of magnitude increase in performance over popular CPU-based PIC
codes.

We estimate that the large scale simulations relevant for this project will at
least require a comparable computational power, both in terms of TFLOPS as well
as total cumulated GPU memory. For the time being our institute can only
provide local access to a CPU-based grid with ~300 cores, which proves
inadequate for the type of 3D laser-plasma simulations necessary for this
project. A separate challenge is presented by the long propagation lengths (up
to a few centimeters) that have to be modelled in the case of using the
discharge capillary. While the background plasma dynamics should not be a
problem, the injected electrons can experience various numerical instabilities
for simulaitons of over 100k time steps, under the influence of the numerical
dispersion produced by the field solver. Mitigating such numerical effects
would require a dramatic increase in both the temporal and longitudinal
resolution, leading to increased computational times and larger memory demands
for storing the electromagnetic fields.

The calculation of the far-field angularly- and spectrally-resolved betatron
emission spectrum, which could be done in situ on the GPUs, using the radiation
plugin develop by R. Pausch et. al for the `PIConGPU` code, also contributes to
increasing the computational time of a typical production run. Therefore, the
runtime per simulation should be between 1 week to 10 days for each parameter
set, and we would probably require around 200k CPU-hours in order to properly
explore the parameter space. Assuming every GPU is assigned to 18 CPU cores,
that would translate into ~11k GPU-hours, which is roughly 2 large-scale
production runs using 30 GPUs simultaneously.

As far as storage space is concerned, a single simulation can produce around 1
TB output, so transferring it over the network is not a viable option – we
would need to do the post-processing locally, perhaps using CPU nodes.

### 2.2. Research benefits of interacting with my local scientific host

I've met some of the members of the INFN-LNF [SPARC LAB](
http://w3.lnf.infn.it/lab/sparc_lab) at at the recent CERN ["High Gradient
Wakefield Accelerator"](https://indico.cern.ch/event/759579) school in Sesimbra
(Portugal) and we soon discovered similar research topics with my group at
ELI-NP. One of the key distinguishing features of SPARC LAB is the integration
of a high-power, ultrashort Ti:Saph laser system (FLAME) with a high-brightness
photo-injector. Together with a recently-developed hydrogen discharge
capillary, this allows for very flexible setups in both laser wakefield (LWFA)
as well as plasma wakefield (PWFA) experiments. Meanwhile, the ELI-NP project
is still in its implementation phase, with preliminary experiments being
scheduled for later this year, so we would definitely benefit from the
extensive expertise of the Frascati group in the design and planning of future
experiments. On the other hand, both groups would benefit from large-scale
laser-plasma simulations using the particle-in-cell method for a better
understanding of the fast dynamical phenomena that can't usually be resolved by
conventional diagnostic tools. We envision this grant to be the perfect
opportunity to start a long-lasting collaboration between our research groups,
with subsequent bilateral visits.

## 3. Weekly-based project workplan

### 3.1. List of specific objectives and approximate timeline

On *week 1*, I will get better acquainted with the research activities and
personnel at SPARC LAB, sort out any unforseen logistic problems and proceed to
install the `fbpic` and `PIConGPU` particle-in-cell codes on the cluster
provided by hpc-Europa and perform preliminary test runs, comparing results to
well-know analytical solutions. I will also develop an `fbpic` -
[`signac`](https://signac.io/) interface which we will use in *week 4*.

On *week 2*, I will calibrate and test the newly installed PIC codes by
reproducing the previously published results from [A. Curcio et. al, Appl.
Phys. Lett. 111, 133105 (2017), A. Curcio et. al, Phys. Rev. Accel. Beams 20,
012801 (2017)]. This would also allow a better understanding of the underlying
physical assumptions of the previously used model.

On *week 3*, I will estimate the optimally matched laser and plasma parameters
following the analytical model of W. Lu et. al [W. Lu et. al, Phys. Rev. ST
Accel. Beams 10 (6) 061301, (2007)]. Special consideration has to be given to
the case of using a the discharge capillary. Furthermore, the betatron
radiation spectrum can be estimated via the scaling laws developed by A. Thomas
[A. G. Thomas, Physics of Plasmas 17 (5) 056708 (2010)].

On *week 4*, I will proceed with a large-scale scan of the parameter space
using the `fbpic` code [R. Lehe et. al, Comp. Phys. Comm. 203, 66 (2016)].
`fbpic` is a spectral, quasi-3D PIC code which also has a reduced envelope
model for the laser and as such, is well suited to quick parameter scans of
setups which benefit from cylindrical symmetry. Typically, uses a large number
of GPUs simultaneously for such a scan, each GPU assigned to an individual
start-to-end simulation for a given parameter set. Since the parameter sets are
independent, there is no need for inter-GPU communication in this case.
However, since the `fbpic` code doesn't (yet) contain a plugin for calculating
the far-field emitted radiation spectrum, the betatron spectrum will have to be
calculated during post-processing, from the recorded electron trajectories,
using the Liénard–Wiechert potentials. This requires a separate code, for which
a good starting candidate would be
[`synchrad`](https://github.com/hightower8083/synchrad), perhaps with
additional further development.

On *weeks 5-8* I will undertake full-scale PIC simulations using `PIConGPU`,
for the most promising parameter sets discovered during *week 4*. `PIConGPU`
[Bussmann et. al, Proc. Int. Conf. on HPC, Networking, Storage and Analysis,
(2013)], a fully relativistic 3D3V code running on graphic processing units
(GPUs). The code is open source, with a GPL license, and developed by the
Junior Group Computational Radiation Physics at the Institute for Radiation
Physics at HZDR in close collaboration with the Center for Information Services
and High Performance Computing (ZIH) of the Technical University Dresden.
`PIConGPU` is a parallel code, using message parsing (MPI) to communicate
between various GPUs and `Alpaka`, an abstraction library for parallel kernel
acceleration based on CUDA, at the single-GPU level. Due to the large memory
required for simulating scenarios relevant to the current laser-plasma
experiments, `PIConGPU` has to be run on multiple GPUs, with the simulation
domain split up between them.

The production runs will be followed by converge testing and post-processing of
the simulation results, in close interaction with the experimental and
simulation teams from SPARC LAB. Any data analysis scripts developed in the
process, as well as the simulation data itself will be released open-source for
the benefit of the community. Also during this time I plan to start some
simulations for preliminary ELI-NP experiments which might share some of the
previously-described workflow.

On *week 8* I will start writing down a draft (eventually leading to
peer-reviewed publication) detailing the analyzed data up to that point and any
preliminary conclusions that might be reached by combining experimental data
with the results of numerical modelling.

The numerical simulations and data analysis will then continue until the
expiration date of the HPC cluster account, ~6 months after the initial visit.