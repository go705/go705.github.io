# Page 1

18-dB on-chip vacuum squeezing in an adaptively
poled lithium niobate waveguide
Tushar Sanjay Karnik∗1,4, Xinyi Ren∗1,2, Chun-Ho Lee∗1,2, Bo-Han Wu3,6, Mihir
Chaudhari1, Clayton Cheung1,2, James Wang1, Shi-Yuan Ma3, Mahmoud Jalali
Mehrabad3, Ian Christen1, Reshma Kopparapu1,2, Kiwon Kwon1,4, Yue Yu1,2,4, Sri
Krishna Vadlamani3, Kamila Kunes1,2, Quntao Zhuang2,5, Dirk Englund3, Zaijun
Chen1,2, and Mengjie Yu†1,2,4
1Department of Electrical Engineering and Computer Sciences, University of California,
Berkeley, CA 94720, USA
2Ming Hsieh Department of Electrical and Computer Engineering, University of Southern
California, Los Angeles, CA 90089, USA
3Research Laboratory of Electronics, MIT, Cambridge, MA 02139, USA
4Materials Sciences Division, Lawrence Berkeley National Laboratory, Berkeley, CA 94720,
USA
5Department of Physics and Astronomy, University of Southern California, Los Angeles, CA
90089, USA
6Department of Electrical and Computer Engineering, University of Hawaii at M¯ anoa,
Honolulu, HI 96822, USA
Abstract
Quantum squeezed states of light can enhance measurement sensitivity beyond
classical limits and enable quantum information processing, but scalable low-loss
sources remain challenging. We demonstrate continuous-wave quantum squeez-
ing on a chip, achieving 18 dB of squeezing and 20 dB of anti-squeezing at 1570
nm in a 1.6-cm traveling-wave adaptively poled thin-film lithium niobate waveg-
uide. A distributed model independently determines facet losses, phase noise,
and nonlinear interaction strength without prior assumptions, enabling rigorous
inference of on-chip performance. We estimate a 95% confidence interval of [-
18.96, -17.25] dB squeezing and [19.96, 21.35] dB anti-squeezing. These values
represent the highest squeezing reported for any integrated photonic platform
and the first assumption-free statistical validation of integrated squeezing per-
formance. Our results establish thin-film lithium niobate as a high-performance,
scalable platform for continuous-variable quantum sensing, communications, and
computing.
∗These authors contributed equally.
†Corresponding author: mengjie.yu@berkeley.edu
1
arXiv:2605.27607v1  [physics.optics]  26 May 2026


# Page 2

1 Introduction
The generation of quantum squeezed light enables the suppression of noise in one field
quadrature below the shot-noise limit imposed by Heisenberg’s uncertainty principle [1,
2]. Over the past decade, squeezed light has significantly enhanced the sensitivity of
gravitational-wave detectors [3, 4], highlighting its importance for practical quantum
sensing applications [5]. Furthermore, replacing coherent vacuum with squeezed states
has enabled performance improvements in a wide range of fields, including quantum
imaging [6, 7], quantum computing [8–10] , dual-comb spectroscopy [11, 12] and opto-
mechanical sensing [13, 14] .
Quantum squeezing has been realized using several nonlinear mechanisms, includ-
ing quadraticχ (2) nonlinearities [15–25], Kerrχ (3) nonlinearities [26–31], and optome-
chanical interactions [32]. Among these,χ (2) platforms offer the highest nonlinear
light-matter interaction strength and are therefore particularly attractive for generat-
ing strong squeezing. State-of-the-art squeezing experiments still predominantly rely
on bulk, discrete optical parametric oscillators (OPOs), which have achieved squeezing
levels as high as 15 dB via combiningχ (2) nonlinear materials with free-space cavities
to provide Purcell enhancement [15, 33].
Photonic integrated circuits (PICs) offer significant advantages in size, weight, and
power (SWaP) compared with free-space systems, providing a promising route toward
scalable squeezed-light sources. More importantly, tight optical confinement enhances
light–matter interaction and enables dispersion engineering, potentially allowing effi-
cient squeezing even without cavity enhancement. In particular, the thin-film lithium
niobate (TFLN) has emerged as a leading material platform for optical parametric
amplification (OPA) and squeezed-light generation by leveraging tight modal confine-
ment and large second-order nonlinear coefficients [34–36]. Although squeezing has
recently been demonstrated in TFLN resonators [23, 23–25], achieving simultaneously
high escape efficiencies and low propagation losses remains challenging. In addition,
maintaining the stringent co-resonance condition at both the pump and squeezed wave-
lengths requires precise temperature stabilization [25, 37, 38], which has limited the
inferred squeezing levels to less than 8 dB [25].
In contrast, non-resonant periodically poled thin-film lithium niobate (PP-TFLN)
waveguide-based approaches provide a simpler and monolithic architecture capable
of generating broadband squeezing [39–42]. Recent experiments have demonstrated
5.6 dB anti-squeezing and−0.77 dB squeezing using a 1-cm PPLN waveguide under
continuous-wave (CW) pumping [42], while inferred pulsed squeezing of 10.5 dB has
also been reported using pulses source with a 10-W peak power and a 75-fs pulse du-
ration [39]. Despite the use of high peak powers and ultrafast optical pulse sources,
pulsed squeezing schemes can still involve practical considerations such as requiring a
temporally matched local oscillator (LO) for efficient homodyne detection, while the
effective interaction length is often influenced by group-velocity matching. The achiev-
able squeezing benefits from stronger second-order nonlinear interaction sustained over
a longer interaction length, with the gain scaling approximately as √gPL, whereg
is the nonlinear coupling coefficient,Pis the pump power, andLis the interaction
length. However, maintaining strong nonlinear coupling over long waveguides is chal-
lenging because thickness variations can disrupt phase matching and reduce conversion
efficiency [43, 44]. More importantly, quantum-limited noise variance reduction (namely
2


# Page 3

squeezing) is known to be highly vulnerable to any optical loss, which increases also
with interaction length L, posting additional challenges compared with achieving large
classical parametric gain. Demonstrating strong squeezing therefore requires excellent
device performance together with accurate modeling to confidently extract the true
squeezing level [45]. In this context, low-loss, long, adaptively poled PPLN nanowaveg-
uides offer a promising route toward achieving continuous-wave squeezing levels beyond
10 dB, a milestone not yet demonstrated on any integrated platform, while approach-
ing the performance of state-of-the-art bulk OPO systems and maintaining broadband
operation with reduced system complexity.
In this work, we demonstrate CW quadrature squeezing in a 1.6-cm-long adaptively
poled TFLN waveguide with a low propagation loss of 0.1 dB/cm. By mapping the
lithium niobate thickness prior to poling, we tailor the local poling period to maintain
strong parametric gain across the entire device length, achieving a second-harmonic
generation (SHG) efficiency of 2740 % W −1. Our device exhibits the highest reported
anti-squeezing for any waveguide or resonator platform, reaching +13.22±0.44 dB
under CW operation at a pump power of 200 mW, along with measured squeezing
of -0.66±0.35 dB. Leveraging a bidirectional SHG method to accurately quantify
facet losses, we establish a comprehensive loss and phase-noise model that captures the
distributed nature of squeezing generation. Using this framework, we infer a record
on-chip squeezing of -18.06±0.43 dB and anti-squeezing of +20.64±0.35 dB among
all waveguide and resonator-based platforms. At the 95% confidence level, the on-chip
squeezing lies in the range [-18.96, -17.25] dB. To our knowledge, this is the first work
to employ a distributed and bidirectional model to infer on-chip squeezing with such
high accuracies. Notably, at such high squeezing levels, even sub-percent optical losses
and phase noise on the order of tens of milliradians are found to play a non-negligible
role, highlighting the critical importance of distributed loss and noise engineering in
traveling-wave squeezing systems.
3


# Page 4

Input light - 2ω
q
p
p
q
Squeezed light - ω
LiNbO3
Inverted Domain
SiO2
Si
ω
ω
2ω
OPA
a
PPLN waveguide
1000 µm
10 µm
b
c d
Figure 1: Concept and design of the TFLN PPLN waveguide for on-chip squeezed-
vacuum generation.a, Schematic of the PPLN nanowaveguide generating squeezed
light at frequencyω(red, output) from a pump at 2ω(blue, input) via aχ (2) nonlinear
interaction.b, Optical micrograph of the squeezer chip containing multiple adaptively
poled waveguides of length 1.6 cm (highlighted by the red dashed box). The lower
panel shows a two-photon microscope image revealing the periodically poled domains.
c, Blue: measured thickness variation along the nanowaveguide obtained via spectro-
scopic reflectometry. Red: corresponding adjustment of the poling period along the
waveguide length to preserve the QPM condition at a fixed wavelength.d, Measured
SHG spectrum (solid line) of the PPLN waveguide showing a single dominant peak en-
abled by the adaptive poling design, along with the simulated spectrum (dashed line).
Note that both curves are normalized with respect to their own peak efficiency.
2 Results
We generate squeezed vacuum using a straight PPLN waveguide, as shown in fig. 1a.
The device is fabricated on a 600-nm-thick MgO-doped X-cut TFLN wafer. fig. 1b shows
an optical microscope image of the squeezer chip featuring multiple waveguides with
1.6 cm-long PPLN sections. The lower panel of fig. 1b shows a two-photon microscope
image of a PPLN waveguide, revealing uniform domain inversion along the entire length.
Although longer poling lengths can, in principle, yield higher squeezing, nanometer-
scale thickness variations in the LN film limit the nonlinear efficiency of TFLN waveg-
uides. To mitigate this, we first map the TFLN wafer thickness and then adjust the
4


# Page 5

local poling period to maintain a constant quasi-phase-matching (QPM) wavelength, as
illustrated in fig. 1c. The waveguides are fabricated by etching 350 nm of LN after peri-
odic poling. After cleaving the chip to expose the facets, a 200 nm-thick oxide cladding
is deposited to reduce coupling losses. More details on the fabrication procedure can
be found in the supplementary material SM Sec. I.
The PPLN waveguide width is chosen to be 2µm in order to maintain low propa-
gation loss at both telecom and visible wavelengths. We measure the intrinsic quality
factors of the PPLN microresonators to be 3.2 million and 2.0 million around 1570 nm
and 785 nm, corresponding to propagation losses of 0.12 and 0.40 dB/cm, respectively.
The effectiveness of the adaptive poling design is verified by the SHG spectrum shown
in fig. 1d, which exhibits minimal deviation from the ideal sinc-squared response. Fig-
ure 2a shows the optical characterization setup used to measure squeezing. A near-
infrared (NIR) laser is amplified and subsequently split into two paths. The first path
is directed to a bulk PPLN SHG module to generate the pump light at 2ω(786.1 nm),
while the second path serves as the local oscillator. Squeezed light atω(1572.2 nm)
is generated in the PPLN waveguide through an optical parametric amplification pro-
cess. For homodyne detection, the squeezed field is interfered with the LO using a
fiber beam splitter connected to balanced photodetectors (BPD), achieving an interfer-
ence visibility of 97 %. The noise variance of the squeezed vacuum is recorded using a
radio-frequency spectrum analyzer (RSA), while the LO phase is scanned using a phase
modulator (Thorlabs, LN65S-FC) driven by a 20 Hz triangular waveform.
Figure 2b shows the measured noise of the squeezed light at a sideband frequency
of 5 MHz. The signal is normalized to the shot-noise level, obtained by blocking the
squeezed-light path. We observe−0.66 dB±0.35 dB of squeezing and +13.22 dB±
0.44 dB of anti-squeezing at an input on-chip pump power of 205 mW. The relation
between on-chip squeezing/anti-squeezing and the measured value is given by:
G±,meas = (ηG±,onchip + 1−η) cos 2(∆θ)
+ (ηG∓,onchip + 1−η) sin 2(∆θ), (1)
whereG − andG + are the squeezing and anti-squeezing level, respectively,ηis the
total effective detection efficiency and ∆θcharacterizes the phase noise in the inter-
ferometer between the squeezing generator path and the LO path. Consequently, the
measured squeezing is primarily limited by detection losses, including the output chip
facet loss and losses from subsequent optical components. The relative phase noise in
the fiber interferometer further lowers the measured squeezing due to the laser phase
noise fluctuation, fiber length fluctuation, as well as any path length difference between
the squeezed and LO signals. Phase noise causes the anti-squeezed quadrature to mix
into the measured squeezed quadrature, thereby substantially degrading the observed
squeezing at high squeezing levels. Consequently, the maximum measured squeezing of
-1.11 dB occurs at a lower pump power, as shown in fig. 2c. fig. 2d illustrates this effect.
By incorporating 50 mrad of laser phase noise into eq. (1), we reproduce the reduction
in observed squeezing at higher pump powers.
While optical component loss can be measured directly using sensitive power me-
ters, chip facet loss and interferometer phase noise are fundamentally challenging to
determine since one can not simply measure the optical transmission before and after a
certain chip facet and the interferometer involves frequency conversion in the squeezing
5


# Page 6

generation arm, which can lead to inaccurate estimation ofG ±,onchip. Moreover, we
note that on chip propagation loss is no longer negligible in a high squeezing regime
since it mixes vacuum noise as the squeezed light is generated and propagates along
the waveguide (see fig. 3a). In previous demonstrations, this effect has typically been
approximated as a lumped loss combined with off-chip losses, which can lead to signifi-
cant errors in inferred squeezing values. Here, we adopt a distributed loss-and-squeezing
model to accurately capture these dynamics. For a straight PPLN waveguide of length
Lwith SHG efficencyη SHG , the on-chip squeezing/anti-squeezing for incident power
Ppump,onchip at 2ωis expressed using our model:
G∓,onchip = r±se −(r±s)L
r±s
(2)
wheres= 2
p
ηSHG ηA,vPpump is the squeezing gain andris the propagation loss per
unit length along the waveguide atω. The detailed derivation can be found in the
the supplementary material SM Sec. V. We extract a waveguide propagation loss of
0.1±0.02 dB/cm, extracted from quality factor measurements of PPLN microresonators
fabricated under identical process conditions (2.5-3.5 million at near 1570 nm). We also
observe similar intrinsic quality factors between PPLN microresonators and non-poled
TFLN microresonators with identical geometries, indicating that the poling process
does not introduce measurable additional propagation loss.
To avoid uncertainty in estimation of individual facet losses and phase noise, we
propose a robust model to evaluate the essential parameters needed to infer on-chip
squeezing. Our method relies on three key elements: measuring the chip transmission,
deriving theoretical model for on-chip squeezing, and performing bi-directional SHG
efficiency measurements.
To track edge coupling losses, we label the input and output facets as A and B,
respectively. Coupling losses at telecom (t) and visible (v) wavelengths are denoted
ηA,t,η B,t,η A,v andη B,v. The total detection efficiency for the squeezing measurement
in eq. (1) isη=η B,tηcomp, whereη comp accounts for the losses in optical components
after the chip. The total transmission loss of the squeezer chip atω(1572.2 nm) and
2ω(786.1 nm) is expressed in terms of the facet loss:
ηA,tηB,t = 10−Losst/10 (3)
ηA,vηB,v = 10−Lossv/10 (4)
whereLoss t andLoss v are measured in dB.
6


# Page 7

13.22 dB
-0.66 dB
PM
BS
RSACOL
Dichroic
BPD
L-band 
amp
NIR 
laser
SHG 
module
PPLN waveguidea
b
7.20 dB
-1.11 dB
c
No phase noise
50 mrad phase noise
d
Figure 2: Observation of squeezing from the PPLN nanowaveguide.a, Experimental
setup for the squeezing measurement. The NIR laser is amplified and split into two
paths for squeezing generation and the local oscillator (LO), which are subsequently
recombined at the balanced homodyne detector. PM: phase modulator; COL: collima-
tor; BS: beam splitter; BPD: balanced photodetector; RSA: radio-frequency spectrum
analyzer.b, Normalized quantum noise (blue) measured at 205 mW pump power while
sweeping the squeezing angle. The black curve indicates the vacuum noise level ob-
tained by blocking the signal path.c, Normalized quantum noise (blue) measured at
87 mW pump power.d, Measured squeezing vs. on-chip squeezing for 50 mrad laser
phase noise and no phase noise. Experimental data is represented by red dots.
To measureη SHG , we used an optical fiber setup, where a tunable NIR laser output
is coupled into the squeezer chip and the converted second-harmonic signal is measured
using a visible photo detector (Thorlabs PDA100A2) after WDM filtering. The on-chip
SHG efficiency is characterized for both forward and backward propagation, as shown in
fig. 3b. In the forward direction, the fundamental wave (ω) is injected via facet A, and
the second-harmonic signal (2ω) is monitored at facet B. In the reverse configuration,
7


# Page 8

the input and collection ports are swapped to assess the symmetry. The SHG efficiency
in forward (ηSHGf ) and backward (ηSHGb) directions is calculated as:
ηSHGf = PB,v/ηB,v
 
PA,tηA,t
2 ,
ηSHGb = PA,v/ηA,v
 
PB,tηB,t
2 ,
(5)
where theP A,t andP B,v are the incident telecom and output visible power in forward
propagation andP B,t andP A,v represent the incident telecom and ouptut visible power
in backward propagation. Since the on-chip SHG is theoretically reciprocal,η SHGf
should equalη SHGb. Equations (1) to (5) form a set of non-linear equations that we
solve to determine the chip facet losses and the phase noise. We implement a Levenberg-
Marquardt (LM) algorithm for iterative solution, starting with an initial guess of sym-
metric facet losses. fig. 3c shows the evolution of the facet losses at each iteration.
The corresponding SHG efficiencies in forward and backward directions converge to a
single consistent value, as shown in fig. 3d. Monte Carlo simulations embedded within
the solver provide uncertainty estimates for all parameters, yielding an SHG efficiency
of 1065.35±51.14 %/(W cm 2). The converged solutions are provided in table 1. All
other parameters includingLoss t,Loss v,P A,t,P B,t,P A,v, andP B,v in these equations
are direct power measurements with known error bars (see SM Sec. III). Notably, our
model does not assume symmetric facet losses, and instead predicts realistic asymmetric
coupling at the input and output facets across both fundamental and second-harmonic
wavelength bands. This enables accurate extraction of the on-chip SHG efficiency (in
%/W/cm2), which is otherwise highly sensitive to facet-loss assumptions, and provides
a reliable means to assess the true poling quality.
Table 1: Predicted values by non-linear equation solver at 205 mW pump power
Parameter Predicted Mean
95%
confidence interval
ηA,t (dB) 3.02 [2.68, 3.38]
ηA,v (dB) 4.68 [4.77, 5.56]
ηB,t (dB) 5.15 [4.19, 5.25]
ηB,v (dB) 6.46 [5.87, 6.95]
∆θ(mrad) 37 [2.3 , 55]
ηSHG ( %
Wcm2 ) 1065.35 [947.212, 1165.64]
G−,onchip (dB) -18.06 [-18.96, -17.25]
G+,onchip (dB) 20.64 [19.96, 21.35]
The lower measured efficiency compared with our theoretical prediction of 3200
%W −1cm−2 (calculated by using analysis provided in [34]) is attributed to incomplete
poling depth (supplementary material SM Sec. II) and cladding non-uniformity, which
also explains the deviations from the ideal sinc-squared SHG spectrum in fig. 1e. fig. 3e
shows the percentage conversion into the second-harmonic for both forward and back-
ward propagation directions as a function of input telecom power. Additionally, the
predicted laser phase noise is 0.037±0.011 radian which is close to the measured value
of 0.062 radian from an independent experiment using a similar interferometer without
8


# Page 9

Forward SHG 
Backward SHG 
PA, Telecom PB, Visible
PA, Visible PB, Telecom
Facet A Facet B
Facet BFacet A
b
Visible Pump
L
dl
p
q
p
q
p
q
Gain = e-sdl
Loss = e-rdl
G-,on-chip(l)
Vacuum noise
a
l
PPLN waveguide
G-,on-chip(l+dl)+
𝜂𝐴,𝑇𝑒𝑙𝑒𝑐𝑜𝑚
𝜂B,𝑇𝑒𝑙𝑒𝑐𝑜𝑚
𝜂A,Visible
𝜂B,Visible
Efficiency = 2741.13 %/ W
Efficiency = 2741.24 %/ W
c d e
f g h
Figure 3: Prediction of on-chip squeezing/anti-squeezing using non-linear equation
solver.a, Evolution of continuous-wave squeezing along the PPLN waveguide. As
the field propagates, nonlinear interaction generates squeezing while optical loss intro-
duces vacuum noise, progressively mixing with the squeezed state.b, Schematic of the
bidirectional SHG measurement used to accurately characterize the telecom and visible
coupling losses at both facets.c, Iteration history of the four unknown facet losses.
Starting from an initial assumption of symmetric losses, the parameters are iteratively
updated using a nonlinear solver until the residual falls below a predefined tolerance,
indicating convergence. The iterations to the right of the x-axis break include Monte
Carlo simulations, where the solid line represents the floating-point average and the
shaded region denotes the statistical spread.d, Evolution of the SHG efficiency in the
forward (purple) and backward (green) direction calculated by using the facet loss values
in c.e, Linearly fitted SHG efficiency for forward propagation (top) and the backward
propagation (bottom) using the final facet losses obtained from the non-linear solver.
Probability density distribution of the inferred squeezing valuesf, and anti-squeezing
g, with the shaded region indicating the 95% confidence interval and the dotted line
denoting the mean.h, Joint distribution of inferred squeezing and anti-squeezing from
all Monte Carlo trials, illustrating the correlation between the two inferred parameters
arising from propagated experimental uncertainties.
9


# Page 10

the squeezing generation (supplementary material SM Sec. VII). The squeezing/anti-
squeezing used to compute the facet losses in fig. 3c were obtained at the highest pump
power.
Using this method we infer a maximum on-chip squeezing of−18.06±0.43 dB
and on-chip anti-squeezing of +20.64±0.35 dB at 205 mW pump power. The full
probability distributions of the inferred squeezing and anti-squeezing obtained from
Monte Carlo simulations are shown in fig. 3(f–h). Detailed solutions for multiple power
measurements can be found in the supplementary material SM Sec. VI. fig. 4a shows the
measured squeezing and antisqueezing at various pump powers, alongside the theoretical
predictions ofG ±,onchip andG ±,meas using solved facet losses and phase noise. The
experimental results show excellent agreement with the model across the full pump-
power range.
a
- 18.06 dB
b
This work
Saturated G-,on-chip =  - 23.5 dB
Saturated G-,on-chip =  - 32.3 dB
Saturated G-,on-chip=  - 21.1 dB
Figure 4: Estimation of on-chip squeezing using the distributed loss model.a, Mea-
sured squeezing and anti-squeezing values (circles) at different pump powers are plotted
along with the theoretical model (dashed line) incorporating the estimated SHG con-
version efficiency, various loss mechanisms, and relative phase noise. From this anal-
ysis, we infer a maximum on-chip squeezing of−18.06±0.43 dB and anti-squeezing
of +20.64±0.35 dB (solid lines).b, Predicted squeezing vs. waveguide length using
distributed loss model forη SHG = 1065.35 %W −1cm−2 and 0.1 dB/cm loss (current
device),η SHG = 3200 %W −1cm−2 (theoretical maximum) and 0.1 dB/cm loss, &η SHG
= 3200 %W −1cm−2 and 1.3 dB/m loss (improved fabrication).
10


# Page 11

3 Conclusion
To summarize, we have demonstrated a promising approach for generating on-chip
quantum squeezing using TFLN- based PICs. Our PPLN waveguide achieves measured/on-
chip continuous wave squeezing and anti-squeezing of -0.66/-18.06 dB and +13.22/+20.64
dB at telecommunication wavelength near 1570 nm using 205 mW pump power. Us-
ing a non-linear coupled equation solver combined with Monte Carlo simulations, we
infer an on-chip squeezing level with a 95% confidence interval of [−18.96,−17.25] dB.
Among all integrated platforms, we achieve the highest measured anti-squeezing and
the highest inferred on-chip squeezing. The high squeezing gain is enabled by adap-
tive poling strategy and low propagation loss, which together preserves high non-linear
efficiency in a 1.6-cm-long PP-TFLN waveguides. We also demonstrate the longest
TFLN waveguide reported to date for use as a non-resonant squeezer. Compared to
pulsed pumping schemes, our device achieves higher on-chip squeezing at an order of
magnitude lower pump peak power. Furthermore, the OPA gain bandwidth in TFLN
can extend over several terahertz, making it a promising platform for broadband and
two-mode squeezing protocols.
Looking ahead, extending the current PPLN waveguide length to 2 cm could fur-
ther improve the squeezing to -19.9 dB, approaching the saturated value of -21.1 dB
(fig. 4b). In addition, achieving an SHG efficiency close to the theoretical limit of 3200
%W −1cm−2 could enable up to−23 dB of on-chip squeezing. Further improvements in
waveguide propagation loss to around 1.3 dB/m (corresponding to an intrinsic Q-factor
of 30 million [46]) can increase the squeezing to−32 dB (fig. 4b). Further improvements
in poling depth through techniques such as side-wall poling [47] or high-temperature
poling [48] could enhance the achievable squeezing levels. In addition, reducing facet loss
using high-efficiency mode size converters [49] would significantly improve the measured
squeezing level, which is currently limited by the detection losses. Beyond squeezed
light generation, adaptively poled TFLN waveguides can provide parametric amplifi-
cation for emerging integrated photonic computing architectures [50]. Moreover, this
non-resonant squeezing approach simplifies the experimental implementation by elimi-
nating the need for precise cavity locking and Pound–Drever–Hall stabilization, which
are typically required in resonant systems, thereby making it more suitable for practical
deployment. More broadly, this work establishes a powerful framework for extracting
both linear and nonlinear device parameters, which have historically been difficult to
access using conventional lumped or symmetric-loss models.
Data availability
The datasets generated and analyzed in the current study are available from the corre-
sponding authors on reasonable request.
Acknowledgements
This work is supported by the DARPA INSPIRED program (HR001123S0052), the
DARPA Young Faculty Award (D23AP00252-02) and the Air Force Office of Scientific
Research under award number FA9550-24-1-0349. Two-photon imaging experiments
11


# Page 12

were conducted at the CRL Molecular Imaging Center, RRID: SCR017852, supported
by NIH grant S10OD025063. Device fabrication was performed at the John O’Brien
Nanofabrication Laboratory at University of Southern California, Marvell Nanofabri-
cation Laboratory at University of California, Berkeley, University of California Los
Angeles Nanolab and Molecular Foundry at Lawrence Berkeley National Laboratory.
M.Y., Y.Y. and T.S.K. are supported by the U.S. Department of Energy, Office of
Science, Basic Energy Sciences, Materials Sciences and Engineering Division under
Contract No. DE-AC02-05CH11231 within the Quantum Coherent Systems Program
KCAS26. The views, opinions and/or findings expressed are those of the authors and
should not be interpreted as representing the official views or policies of the Department
of Defense or the U.S. Government.
Author contributions
M.Y. conceived the idea. T.K. designed the chip with the help of R.K. and C.-H.L..
C.-H.L. and T.K. fabricated the devices and developed the fabrication processes with
the help of K. K., K. K., C.C., I.C. and Y.Y.. X.R., T.K. and M.C. carried out the
experiments and analyzed the data with help from R.K. and J.W. carried out the laser
phase noise measurements.
B.-H.W., S.-Y.M., M.J.M., and S.K.V. performed theoretical calculations, super-
vised by D.E.. Q.Z. developed the theoretical model for inferred squeezing. T.K., X.R.
and M.Y. wrote the manuscript with contributions from all authors. M.Y. and Z.C.
supervised the project.
Competing interests
C.-H.L., Z.C. and M.Y. are involved in developing lithium niobate technologies at Op-
ticore Inc.
References
[1] Horace P Yuen. Two-photon coherent states of the radiation field.Physical Review
A, 13(6):2226, 1976.
[2] Daniel F Walls. Squeezed states of light.Nature, 306(5939):141–146, 1983.
[3] D. Ganapathy, W. Jia, M. Nakano, V. Xu, N. Aritomi, T. Cullen, N. Kijbun-
choo, S. E. Dwyer, A. Mullavey, L. McCuller, and LIGO O4 Detector Collabora-
tion. Broadband Quantum Enhancement of the LIGO Detectors with Frequency-
Dependent Squeezing.Physical Review X, 13(4):041021, October 2023.
[4] Yuhang Zhao, Naoki Aritomi, Eleonora Capocasa, Matteo Leonardi, Marc Eisen-
mann, Yuefan Guo, Eleonora Polini, Akihiro Tomura, Koji Arai, Yoichi Aso, Yao-
Chin Huang, Ray-Kuang Lee, Harald L¨ uck, Osamu Miyakawa, Pierre Prat, Ayaka
Shoda, Matteo Tacca, Ryutaro Takahashi, Henning Vahlbruch, Marco Vardaro,
Chien-Ming Wu, Matteo Barsuglia, and Raffaele Flaminio. Frequency-Dependent
12


# Page 13

Squeezed Vacuum Source for Broadband Quantum Noise Reduction in Advanced
Gravitational-Wave Detectors.Physical Review Letters, 124(17):171101, April
2020.
[5] Zheshen Zhang and Quntao Zhuang. Distributed quantum sensing.Quantum
Science and Technology, 6(4):043001, 2021.
[6] Catxere A. Casacio, Lars S. Madsen, Alex Terrasson, Muhammad Waleed, Kai
Barnscheidt, Boris Hage, Michael A. Taylor, and Warwick P. Bowen. Quantum-
enhanced nonlinear microscopy.Nature, 594(7862):201–206, June 2021.
[7] Michael A. Taylor, Jiri Janousek, Vincent Daria, Joachim Knittel, Boris Hage,
Hans-A. Bachor, and Warwick P. Bowen. Biological measurement beyond the
quantum limit.Nature Photonics, 7(3):229–233, March 2013.
[8] Pfister Olivier. Continuous-variable quantum computing in the quantum optical
frequency comb.Journal of Physics B, 53:012001, 2020.
[9] H. Aghaee Rad, T. Ainsworth, R. N. Alexander, B. Altieri, M. F. Askarani,
R. Baby, L. Banchi, B. Q. Baragiola, J. E. Bourassa, R. S. Chadwick, I. Cha-
rania, H. Chen, M. J. Collins, P. Contu, N. D’Arcy, G. Dauphinais, R. De Prins,
D. Deschenes, I. Di Luch, S. Duque, P. Edke, S. E. Fayer, S. Ferracin, H. Ferretti,
J. Gefaell, S. Glancy, C. Gonz´ alez-Arciniegas, T. Grainge, Z. Han, J. Hastrup,
L. G. Helt, T. Hillmann, J. Hundal, S. Izumi, T. Jaeken, M. Jonas, S. Kocsis,
I. Krasnokutska, M. V. Larsen, P. Laskowski, F. Laudenbach, J. Lavoie, M. Li,
E. Lomonte, C. E. Lopetegui, B. Luey, A. P. Lund, C. Ma, L. S. Madsen, D. H.
Mahler, L. Mantilla Calder´ on, M. Menotti, F. M. Miatto, B. Morrison, P. J. Nad-
karni, T. Nakamura, L. Neuhaus, Z. Niu, R. Noro, K. Papirov, A. Pesah, D. S.
Phillips, W. N. Plick, T. Rogalsky, F. Rortais, J. Sabines-Chesterking, S. Safavi-
Bayat, E. Sazhaev, M. Seymour, K. Rezaei Shad, M. Silverman, S. A. Srinivasan,
M. Stephan, Q. Y. Tang, J. F. Tasker, Y. S. Teo, R. B. Then, J. E. Tremblay,
I. Tzitrin, V. D. Vaidya, M. Vasmer, Z. Vernon, L. F. S. S. M. Villalobos, B. W.
Walshe, R. Weil, X. Xin, X. Yan, Y. Yao, M. Zamani Abnili, and Y. Zhang. Scal-
ing and networking a modular photonic quantum computer.Nature, 638:912–919,
January 2025.
[10] Shunya Konno, Warit Asavanant, Fumiya Hanamura, Hironari Nagayoshi, Kosuke
Fukui, Atsushi Sakaguchi, Ryuhoh Ide, Fumihiro China, Masahiro Yabuno, Shige-
hito Miki, Hirotaka Terai, Kan Takase, Mamoru Endo, Petr Marek, Radim Filip,
Peter van Loock, and Akira Furusawa. Logical states for fault-tolerant quantum
computation with propagating light.Science, 383(6680):289–293, January 2024.
[11] Daniel I. Herman, Mathieu Walsh, Molly Kate Kreider, Noah Lordi, Eugene J.
Tsao, Alexander J. Lind, Matthew Heyrich, Joshua Combes, J´ erˆ ome Genest, and
Scott A. Diddams. Squeezed dual-comb spectroscopy.Science, 387(6734):653–658,
February 2025.
[12] Abdulkarim Hariri, Shuai Liu, Haowei Shi, Quntao Zhuang, Xudong Fan, and
Zheshen Zhang. Entangled dual-comb spectroscopy.Phys. Rev. X, 15:041009, Oct
2025.
13


# Page 14

[13] Yi Xia, Aman R Agrawal, Christian M Pluchar, Anthony J Brady, Zhen Liu,
Quntao Zhuang, Dalziel J Wilson, and Zheshen Zhang. Entanglement-enhanced
optomechanical sensing.Nature Photonics, 17(6):470–477, 2023.
[14] Ran Yin, Yue Yu, Chunho Lee, Ian Christen, Zaijun Chen, and Mengjie Yu. Un-
cooled low-noise thin-film optomechanical resonator for thermal sensing on lithium
niobate.arXiv preprint, 2026.
[15] H. Vahlbruch, M. Mehmet, S. Chelkowski, B. Hage, A. Franzen, N. Lastzka,
S. Goßler, K. Danzmann, and R. Schnabel. Detection of 15 db squeezed states
of light and their application for the absolute calibration of photoelectric quantum
efficiency.Physical Review Letters, 117(11):110801, September 2016.
[16] Gregory S. Kanter, Prem Kumar, Rostislav V. Roussev, Jonathan Kurz, Krish-
nan R. Parameswaran, and Martin M. Fejer. Squeezing in a LiNbO 3 integrated
optical waveguide circuit.Optics Express, 10(3):177–182, February 2002.
[17] Andreas Eckstein, Andreas Christ, Peter J. Mosley, and Christine Silberhorn.
Highly Efficient Single-Pass Source of Pulsed Single-Mode Twin Beams of Light.
Physical Review Letters, 106(1):013603, January 2011.
[18] M. Stefszky, R. Ricken, C. Eigner, V. Quiring, H. Herrmann, and C. Silberhorn.
Waveguide Cavity Resonator as a Source of Optical Squeezing.Physical Review
Applied, 7(4):044026, April 2017.
[19] F. Mondain, T. Lunghi, A. Zavatta, E. Gouzien, F. Doutre, M. De Micheli,
S. Tanzilli, and V. D’Auria. Chip-based squeezing at a telecom wavelength.Pho-
tonics Research, 7(7):A36–A39, July 2019.
[20] Takahiro Kashiwazaki, Naoto Takanashi, Taichi Yamashima, Takushi Kazama,
Koji Enbutsu, Ryoichi Kasahara, Takeshi Umeki, and Akira Furusawa.
Continuous-wave 6-dB-squeezed light with 2.5-THz-bandwidth from single-mode
PPLN waveguide.APL Photonics, 5:036104, 2020.
[21] Kazuki Hirota, Takahiro Kashiwazaki, Taichi Ha, Gyeongmin Yamashima,
Pawaphat Jaturaphagorn, Takumi Suzuki, Kazuma Takahashi, Akito Kawasaki,
Asuka Inoue, Warit Asavanant, Mamoru Endo, Takeshi Umeki, and Akira Fu-
rusawa. Generation of 10-db squeezed light from a broadband waveguide opti-
cal parametric amplifier with improved phase locking method.Optics Express,
34(5):7958–7966, 2026.
[22] Alex Terrasson, Lars Madsen, Joel Q. Grim, and Warwick. P. Bowen. Bright pulsed
squeezed light for quantum-enhanced precision microscopy.arXiv preprint, 2026.
[23] Taewon Park, Hubert Stokowski, Vahid Ansari, Samuel Gyger, Kevin K. S. Mul-
tani, Oguz Tolga Celik, Alexander Y. Hwang, Devin J. Dean, Felix Mayor, Timo-
thy P. McKenna, Martin M. Fejer, and Amir Safavi-Naeini. Single-mode squeezed-
light generation and tomography with an integrated optical parametric oscillator.
Science Advances, 10:eadl1814, 2024.
14


# Page 15

[24] Tummas Napoleon Arge, Seongmin Jo, Huy Quang Nguyen, Francesco Lenzini,
Emma Lomonte, Jens Arnbak Holbøll Nielsen, Renato R. Domeneguetti,
Jonas Schou Neergaard-Nielsen, Wolfram Pernice, Tobias Gehring, and Ulrik Lund
Andersen. Demonstration of a squeezed light source on thin-film lithium niobate
with modal phase matching.Optica Quantum, 3(5):467–473, 2025.
[25] Xinyi Ren, Reshma Kopparapu, Tushar Sanjay Karnik, Chun-Ho Lee, Kiwon
Kwon, Clayton Cheung, Yue Yu, Shi-Yuan Ma, Bo-Han Wu, Ran Yin, Lian Zhou,
Quntao Zhuang, Dirk Englund, Zaijun Chen, and Mengjie Yu. Quantum squeez-
ing in an all-resonant periodically poled lithium niobate microresonator.arXiv
preprint, 2026.
[26] Avik Dutt, Kevin Luke, Sasikanth Manipatruni, Alexander L. Gaeta, Paulo
Nussenzveig, and Michal Lipson. On-Chip Optical Squeezing.Physical Review
Applied, 3(4):044005, April 2015.
[27] Yichen Shen, Ping-Yen Hsieh, Sashank Kaushik Sridhar, Samantha Feldman, You-
Chia Chang, Thomas A. Smith, and Avik Dutt. Strong nanophotonic quantum
squeezing exceeding 3.5 db in a foundry-compatible kerr microresonator.Optica,
12:302–308, 2025.
[28] A. Bensemhoun, S. Cassina, C. Gonzalez-Arciniegas, M. F. Melalkia, G. Pat-
era, J. Faugier-Tovar, Q. Wilmart, S. Olivier, A. Zavatta, A. Martin, J. Etesse,
L. Labont´ e, O. Pfister, V. D’Auria, and S. Tanzilli. Multipartite quantum corre-
lated bright frequency combs.Physical Review Research, 7:033173, 2025.
[29] Xinyu Jia, Chonghao Zhai, Xuezhi Zhu, Chang You, Yunyun Cao, Xuguang Zhang,
Yun Zheng, Zhaorong Fu, Jun Mao, Tianxiang Dai, Lin Chang, Xiaolong Su,
Qihuang Gong, and Jianwei Wang. Continuous-variable multipartite entanglement
in an integrated microcomb.Nature, 639:329–336, 2025.
[30] Zijiao Yang, Mandana Jahanbozorgi, Dongin Jeong, Shuman Sun, Olivier Pfister,
Hansuek Lee, and Xu Yi. A squeezed quantum microcomb on a chip.Nature
Communications, 12:4781, 2021.
[31] Y. Zhang, M. Menotti, K. Tan, V. D. Vaidya, D. H. Mahler, L. G. Helt, L. Zatti,
M. Liscidini, B. Morrison, and Z. Vernon. Squeezed light from a nanophotonic
molecule.Nature Communications, 12:2233, 2021.
[32] Nancy Aggarwal, Torrey J. Cullen, Jonathan Cripe, Garrett D. Cole, Robert
Lanza, Adam Libson, David Follman, Paula Heu, Thomas Corbitt, and Ner-
gis Mavalvala. Room-temperature optomechanical squeezing.Nature Physics,
16:784–788, 2020.
[33] Roman Schnabel. Squeezed states of light and their applications in laser interfer-
ometers.Physics Reports, 684:1–51, July 2017.
[34] Cheng Wang, Carsten†Langrock, Alireza Marandi, Marc Jankowski, Mian Zhang,
Boris Desiatov, Martin M. Fejer, and Marko Lonˇ car. Ultrahigh-efficiency wave-
length conversion in nanophotonic periodically poled lithium niobate waveguides.
Optica, 5:1438 – 1441, 2018.
15


# Page 16

[35] Juanjuan Lu, Ayed Al Sayem, Zheng Gong, Joshua B. Surya, Chang-Ling Zou, and
Hong X. Tang. Ultralow-threshold thin-film lithium niobate optical parametric
oscillator.Optica, 8(4):539–544, April 2021.
[36] Jost Kellner, Alessandra Sabatti, Andreas Maeder, and Rachel Grange. Low
threshold integrated optical parametric oscillator with a compact Bragg resonator.
Optica, 12(5):702–707, May 2025.
[37] Ran Yin, Yue Yu, Chunho Lee, Ian Christen, Zaijun Chen, and Mengjie Yu. Fun-
damental phase noise in thin film lithium niobate resonators.arXiv preprint, 2025.
[38] Xinyi Ren, Chun-Ho Lee, Kaiwen Xue, Shaoyuan Ou, Yue Yu, Zaijun Chen, and
Mengjie Yu. Photorefractive and pyroelectric photonic memory and long-term
stability in thin-film lithium niobate microresonators.npj Nanophotonics, 2:1,
2025.
[39] Rajveer Nehra, Ryoto Sekine, Luis Ledezma, Qiushi Guo, Robert M. Gray,
Arkadev Roy, and Alireza Marandi. Few-cycle vacuum squeezing in nanophotonics.
Science, 377(6612):1333–1337, September 2022.
[40] Pao-Kang Chen, Ian Briggs, Songyan Hou, and Linran Fan. Ultra-broadband
quadrature squeezing with thin-film lithium niobate nanophotonics.Optics Letters,
47(6):1506–1509, March 2022.
[41] Hubert S. Stokowski, Timothy P. McKenna, Taewon Park, Alexander Y. Hwang,
Devin J. Dean, Oguz Tolga Celik, Vahid Ansari, Martin M. Fejer, and Amir H.
Safavi-Naeini. Integrated quantum optical phase sensor in thin film lithium nio-
bate.Nature Communications, 14(1):3355, June 2023.
[42] Xiaodong Shi, Angela Anna Baiju, Xu Chen, Sakthi Sanjeev Mohanraj, Sihao
Wang, Veerendra Dhyani, Biveen Shajilal, Mengyao Zhao, Ran Yang, Yue Li,
Guangxing Wu, Hao Hao, Victor Leong, Ping Koy Lam, and Di Zhu. Squeezed light
generation in periodically poled thin-film lithium niobate waveguides.Nanopho-
tonics, 14(26):4721–4727, 2025.
[43] Pao-Kang Chen, Ian Briggs, Chaohan Cui, Liang Zhang, Manav Shah, and Linran
Fan. Adapted poling to break the nonlinear efficiency limit in nanophotonic lithium
niobate waveguides.Nature Nanotechnology, 19:44–50, 2024.
[44] C. J. Xin, Shengyuan Lu, Jiayu Yang, Amirhassan Shams-Ansari, Boris De-
siatov, Let´ ıcia S. Magalh˜ aes, Soumya S. Ghosh, Erin McGee, Dylan Renaud,
Nicholas Achuthan, Arseniy Zvyagintsev, David Barton III, Neil Sinclair, and
Marko Lonˇ car. Wavelength-accurate and wafer-scale process for nonlinear fre-
quency mixers in thin-film lithium niobate.Communications Physics, 8:136, 2025.
[45] Bo-Han Wu, Mahmoud Jalali Mehrabad, Mengjie Yu, and Dirk Englund. Breaking
on/off-coupling loss degeneracies via bidirectional nonlinear optics.arXiv preprint,
2026.
16


# Page 17

[46] Yunxiang Song, Let´ ıcia Magalh˜ aes, Amirhassan Shams-Ansari, Andrea Cordaro,
Neil Sinclair, and Marko Lonˇ car. Twenty-nine million intrinsic q-factor monolithic
microresonators on thin-film lithium niobate.Photonics Research, 12:A63 – A68,
2024.
[47] C. A. A. Franken, S. S. Ghosh, C. C. Rodrigues, J. Yang, C. J. Xin, S. Lu, D. Witt,
G. Joe, G. S. Wiederhecker, K.-J. Boller, and M. Lonˇ car. Milliwatt-level uv gen-
eration using sidewall poled lithium niobate.Nature Communications, 17:3651,
2026.
[48] Sagar P. Doshi, Gavin N. West, Dodd Gray, and Rajeev J. Ram. Thermal enhance-
ment of defect motion for optimizing periodic poling of x-cut thin-film lithium
niobate niobate waveguides.Applied Physics Letters, 125:261103, 2024.
[49] Lingyan He, Mian Zhang, Amirhassan Shams-Ansari, Rongrong Zhu, Cheng Wang,
and Marko Lonˇ car. Low-loss fiber-to-chip interface for lithium niobate photonic
integrated circuits.Optics Letters, 44:2314–2317, 2019.
[50] Shaoyuan Ou, Kaiwen Xue, Lian Zhou, Chun-ho Lee, Alexander Sludds, Ryan
Hamerly, Ke Zhang, Hanke Feng, Yue Yu, Reshma Kopparapu, Eric Zhong, Cheng
Wang, Dirk Englund, Mengjie Yu, and Zaijun Chen. Hypermultiplexed integrated
photonics–based optical tensor processor.Science Advances, 11:adu0228, 2025.
17
