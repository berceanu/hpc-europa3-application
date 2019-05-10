# Laser-wakefield radiation sources as diagnostic tools  

Document source on [GitHub](https://github.com/berceanu/hpc-europa3-application).

## 1. Background information[^1]

### 1.1. Status of my research activities

I have completed my PhD in the field of theoretical condensed matter physics
at Universidad Autonoma (Spain) and am currently a postdoctoral researcher at
Extreme Light Infrastructure - Nuclear Physics (Romania). In my new role, I
am focusing on theoretical/computational aspects of high power laser-plasma
interaction, in particular accelerating particles to megaelectronvolt
energies using plasma wakefields, with the goal of obtaining
high-brilliance/high-energy secondary radiation sources with various
applications in medical imaging, as well as fundamental research.

Tajima and Dawson’s seminal 1979 paper [Phys. Rev. Lett. 43 (4): 267–70,
(1979)] first introduced the idea that particles could be accelerated to high
energies using laser-plasma interaction instead of the conventional RF
accelerators. The main concept was that the plasma would be perturbed by the
laser and act as a transformer, conveying the laser energy to the particles.
Subsequent experimental developments, in particular the chirped pulse
amplification lead to the advent of high-power lasers, which brought Tajima
and Dawson’s idea to reality. The main advantage of using a plasma instead of
a conventional accelerator is that the electric field gradients it can
withstand are about three orders of magnitude higher than the breakdown
fields of an RF cavity. This allows one to use much shorter acceleration
distances, on the order of centimeters (instead of kilometers) and achieve
similar energies, with the current state of the art of a few GeV. This
acceleration process goes by the name of laser wakefield acceleration (LWFA),
due to the wake that the laser leaves behind it in the plasma. A breakthrough
occured in 2004, when Pukhov and coworkers [Plasma physics and controlled
fusion, 46 (2004)], using numerical simulations, discovered a new regime of
LWFA: the so-called “bubble” regime, allowing for the first time the
production of mono-energetic electron bunches that approach the quality of
those obtained in conventional accelerators.

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
electron bunch emittance low. Unde the action of the radial fields, the
injected electrons which are deviated from the propagation axis start to
oscillate around it, emitting synchrotron radiation, technically know as
betatron radiation. The mechanism of radiation emission is similar to what
happens to an electron bunch propagating inside an undulator, with the role
of the undulator played by the background plasma. The betatron spectrum
usually extends to the X-ray spectral region, due to the relativistic Doppler
shift involved.

The method used by Pukhov is a well established numerical approach in the
plasma physics community and goes by the name of “particle-in-cell” (PIC),
being developed in the early 1960’s by Buneman, Dawson, Hockney, Birdsall,
Morse and others. In a nutshell, one models the plasma as a collections of
macro-particles, each of which correspond to thousands of real particles. The
main PIC loop consists of: (1) integrating the relativistic Lorentz-Newton
equations of motion for the macro-particles, (2) interpolating the resulting
charges and currents to the mesh, (3) computing the electromagnetic (EM)
fields on the mesh and (4) interpolating the EM fields to the positions of
the macroparticles. Since we are dealing with around a billion
macro-particles in a typical simulation, and hundreds of thousands of time
steps, PIC simulations require large distributed computational resources, but
also provide the most accurate description of the plasma evolution, short of
solving the 6-dimensional Vlasov-Boltzman equations.

### 1.2. Project objectives

The main project objective is using the emitted betatron radiation as a
non-intercepting, single-shot diagnostic tool for the properties of the
accelerated electron bunch. The basic algorithm is described in a recent
publication of the Frascati group [A. Curcio et. al, Appl. Phys. Lett. 111,
133105 (2017)], and, in a nutshell, it amounts to measuring both the electron,
as well as betatron energy spectra and obtaining the (radial) beam profile
from the system's S-matrix. In a related paper [A. Curcio et. al, Phys. Rev.
Accel. Beams 20, 012801 (2017)], the same group reconstructed both the beam
profile, as well as the radial emittance of the electron beam, finally
obtaining the trace-space density of the beam.

Both these experiments we perfomed using a pure Helium gas jet, with the
FLAME laser with operating at 1 J pulse energy, 30 fs FWHM@intensity pulse
duration. The electrons reached $\sim 300$ MeV energies in an accelerating
length $\gtrapprox 1$ mm. These studies used a 1D model, assuming a
cylindrically symetric electron bunch distribution. Our objective is to
extend this work to the 2D case, allowing one to reconstruct the 2D emittance
and spatial bunch profile. This would require an angularly-resolved
measurement of the betatron emission spectrum and electron energy spectrum,
as well as large scale numerical modelling using the PIC method.

A preliminary experimental setup is shown in the attached image. The laser
beam (red) is focused by the off-axis parabola (OAP) down to a few
micrometers spot size at the entrance of the gas jet. The probe beam is used
for interferometric imaging of the plasma on the CCD camera, and the
accelerated electrons are deflected by a magnetic dipole onto a LANEX screen
for spectral measurements. The emitted betatron radiation (pink) goes through
an X-ray scintillator onto an X-ray CCD which retrieves its spectral
information.

![envisaged experimental setup](https://raw.githubusercontent.com/berceanu/hpc-europa3-application/master/images/exp_setup.png?token=ABBTTGTHLCCLW345XORQSPS42GSS2)

A further goal of the project is to improve the trapping and general
properties of the electron beam. For example, the beam emittance could be
improved by using different injection schemes such as self-truncated
ionization injection [ref] by adding a small percentage of Nitrogen doping to
the Helium gas. The beam energy could be increased by using a capillary to
guide the laser pulse over a longer propagating distance, up to a few
centimeters, at a lower plasma density.

### 1.3. Contribution to research field development



## 2. Case for HPC-Europa3 funding

### 2.1. Research benefits of accessing HPC-Europa systems[^2]




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
