# Page 1

Quantum squeezing in an all-resonant periodically
poled lithium niobate microresonator
Xinyi Ren∗1,2, Reshma Kopparapu∗1,2, Tushar Sanjay Karnik∗1,4, Chun-Ho Lee∗1,2,
Kiwon Kwon1, Clayton Cheung1,2, Yue Yu1,2,4, Shi-Yuan Ma3, Bo-Han Wu3, Ran
Yin1,2, Lian Zhou1,2, Quntao Zhuang2, Dirk Englund3, Zaijun Chen1,2, and Mengjie
Yu†1,2,4
1Department of Electrical Engineering and Computer Sciences, University of California,
Berkeley, CA 94720, USA
2Ming Hsieh Department of Electrical and Computer Engineering, University of Southern
California, Los Angeles, CA 90089, USA
3Research Laboratory of Electronics, MIT, Cambridge, MA 02139, USA
4Materials Sciences Division, Lawrence Berkeley National Laboratory, Berkeley, CA 94720,
USA
Abstract
Quantum noise limits the sensitivity of optical measurements, but squeezed
states of light enable quantum-enhanced metrology, sensing, and information
processing. Most on-chip squeezed-light sources rely on Kerr (χ (3)) nonlinear-
ities, remain limited by pump power and excess loss constraints. Quadratic
(χ(2)) platforms instead provide stronger parametric interactions, lower pump
power requirements, and greater spectral engineering flexibility. Here, we demon-
strate strong, broadband squeezed-light generation on a thin-film lithium niobate
(TFLN) photonic chip using a dual-resonant optical parametric amplifier imple-
mented in a single periodically poled LN (PPLN) microresonator. Near-full-depth
domain inversion is achieved simultaneously with highly over-coupled resonances,
exhibiting escape efficiencies exceeding 90% and intrinsic quality factors above 2.5
million in a 0.6 mm 2 X-cut TF-PPLN resonator, enabling efficient squeezing at
1587 nm when pumped at 793.5 nm. Operating in the continuous-wave regime,
we directly measure−0.81 dB of squeezing below the shot-noise limit with a
pump power of 27 mW, together with +4.29 dB of anti-squeezing. From these
measurements, we infer an on-chip squeezing level of−7.52 dB±0.22 dB (95%
confidence interval: [−7.96,−7.10] dB), and an on-chip anti-squeezing level of
+9.62 dB±0.25 dB . We demonstrate single-mode squeezing at degeneracy with
a squeezed-light spectrum exceeding 10.3 THz. This work reports the highest
squeezing ratio among integratedχ (2) cavity platforms and the first quasi-phase-
matched, fully resonantχ (2) cavity squeezer on chip, establishing a scalable route
to fully integrated power-efficient squeezed-light sources for quantum-enhanced
sensing and metrology.
∗These authors contributed equally.
†Corresponding author: mengjie.yu@berkeley.edu
1
arXiv:2602.22693v1  [physics.optics]  26 Feb 2026


# Page 2

1 Introduction
Squeezed states of light [1, 2], in which quantum noise in one field quadrature is sup-
pressed below the shot-noise limit, are indispensable resources for continuous-variable
quantum technologies. By reducing measurement uncertainty beyond the standard
quantum limit, squeezing has enabled breakthroughs in quantum sensing [3], includ-
ing acoustic frequency sensing [4], gravitational-wave detection [5, 6, 7, 8], quantum
imaging [9, 10], dual-comb spectroscopy [11, 12] and distributed quantum sensing [13,
14, 15, 16], as well as applications in quantum communication and secure key distribu-
tion [17, 18]. Furthermore, squeezed vacuum and multimode squeezed combs [19, 20]
underpin many architectures for continuous-variable quantum computation and sim-
ulation [21, 22]. Although bulk optical parametric oscillators (OPOs) have long pro-
vided squeezing [23, 24], these systems are large-scale, alignment-sensitive, and power-
intensive, limiting their practicality in scalable quantum networks. A major goal of
modern photonics is therefore to realize compact and scalable squeezed light sources
directly on photonic chips. Integrated photonic platforms offer compelling advantages:
they can leverage strong optical nonlinearities in tightly confined waveguides and mi-
croresonators to dramatically reduce the required pump power and to achieve broad-
band squeezing bandwidth via powerful dispersion engineering [25, 26].
Over the past decade, motivated by these advantages, integrated photonics has
emerged as a versatile platform for squeezed light generation, encompassing both quadratic
χ(2) and Kerrχ (3) nonlinearities, as well as waveguide- and resonator-based implemen-
tations operating in pulsed and continuous-wave (CW) regimes. Early demonstrations
of on-chip squeezing were achieved in silicon nitride microring resonators based on
Kerr nonlinearity [26], followed by substantial development in oscillation threshold re-
duction, bandwidth extension, and near-degenerate operation [27, 28, 29, 30, 31, 32,
33, 34, 35, 36, 20]. Despite these advances, Kerr-based platforms face intrinsic lim-
itations. Owing to the higher-order nature of the Kerr interaction, achieving strong
squeezing typically requires high pump power or extreme cavity quality (Q) factors,
which in turn introduce broadband excess noise or parasitic nonlinear processes, such as
thermo-refractive fluctuations and spontaneous Raman scattering [36, 29]. In resonant
devices, the close spectral proximity of the pump and squeezed fields enforces unfavor-
able trade-offs between escape efficiency and pump power, as overcoupling the squeezing
resonance rapidly increases the required pump power [31, 35]. This property further
necessitates high–extinction-ratio pump filtering for homodyne detection, introducing
additional optical loss that directly degrades observable squeezing [31, 35, 28, 30, 26].
In addition, competing nonlinear processes such as non-degenerate four-wave mixing
and Bragg scattering can be readily phase-matched and, when driven at high pump
power, lead to parasitic mode coupling and excess noise that degrade squeezing purity
and operational robustness [28, 29, 30].
These challenges have motivated increasing interest in quadratic (χ (2)) nonlinear
platforms, where the substantially stronger interaction enables efficient parametric pro-
cesses at reduced pump power. In practice, integratedχ (2) squeezed-light generation
has been realized almost exclusively in lithium niobate, owing to its large second-order
nonlinearity, low optical loss, and quasi-phase-matching technology. Thin-film lithium
niobate (TFLN) further combines these material advantages with high optical con-
finement and scalable nanofabrication, making it a leading platform for integrated
2


# Page 3

continuous-variable quantum photonics. Ultra-broadband pulsed vacuum squeezing
has also been demonstrated in nanophotonicχ (2) waveguides, highlighting the strong
nonlinear capability of this platform [37]. Initial demonstrations of squeezed-light gen-
eration in TFLN have primarily relied on non-resonant periodically poled lithium nio-
bate (PPLN) waveguides, which require large device footprints and are pumped by
either pulsed or continuous-wave lasers at high optical power. While such platforms
enable terahertz-bandwidth squeezing, they often require tens to hundreds of milli-
watts of pump power [38, 39, 40, 41] and are susceptible to waveguide damage and
laser noise. Moreover, achieving uniform quasi-phase matching over centimeter-scale
interaction lengths remains technically challenging, as poling nonuniformity directly
degrades squeezing efficiency and spectral purity. Cavity-enhanced TFLN approaches
offer a promising route to lowering the pump threshold by resonantly enhancing the non-
linear interaction while reducing the device footprint; however, simultaneously achiev-
ing strong light–matter interaction through high-fidelity poling and large Purcell en-
hancement, while optimizing the resonance conditions and coupling strengths for both
the pump and squeezed modes, remains a central challenge for realizing robust, low-
threshold continuous-wave squeezing on chip [42, 43, 44]. To date, squeezing achieved
in TFLN resonators include an integrated OPO demonstrating 0.55 dB squeezing and
1.55 dB anti-squeezing, where only the fundamental field is resonant with 35 % escape
efficiency [45] or using modal phase matching with 1.5 dB inferred squeezing [46].
In this work, we demonstrate quadrature squeezing, for the first time, using an
all-resonant quasi-phase-matched optical parametric amplifier fabricated on the TFLN.
Leveraging advanced nanofabrication and device co-design, we realize a TF-PPLN mi-
croresonator with the highest intrinsic quality factor of 2.6 million reported to date for
a PPLN cavity, together with near-full-depth domain inversion and a poling duty cy-
cle approaching 50%, all achieved in an extremely over-coupled resonance implemented
with a 200-µm coupling length. This enables strong and reproducible resonant enhance-
ment of theχ (2) interaction. Operating below threshold at a pump power of 27 mW
and precise thermal control of a co-resonance condition, we observe a noise suppression
of−0.81 dB±0.04 dB relative to shot noise, together with +4.29 dB±0.10 dB of anti-
squeezing. We infer an on-chip squeezing of−7.52 dB±0.22 dB and anti-squeezing of
+4.29 dB±0.10 dB from both loss tracking and photon flux methods. The generated
squeezed light exhibits a broadband spectrum with a squeezing bandwidth of 10.3 THz,
corresponding to 244 correlated signal–idler mode pairs and an on-chip squeezed-light
power of 320 pW at degeneracy.
2 Results
The squeezed vacuum is generated on a photonic integrated circuit (PIC) featuring
a single-ring resonator equipped with PPLN, as shown in fig. 1a. The microring is
designed to be resonant at both the near-793.5-nm second-harmonic (SH) and near-
1587-nm fundamental-harmonic (FH) wavelengths, thereby enabling efficientχ (2) op-
tical parametric interaction. The racetrack resonator is fabricated on a 600-nm-thick
X-cut TFLN wafer with an etch depth of 350 nm after periodic poling on one straight
waveguide arm and followed by cladding with a 800-nm-thick silicon dioxide layer. The
cavity path length of 3177µm corresponds to a free spectral range (FSR) of approx-
3


# Page 4

Figure 1: Concept and design of the integrated dual-resonant on-chip squeezer based on
TF-PPLN.a, Schematic of the microring resonator with PPLN on a nanophotonic chip.
The device generates squeezed light at the FH frequencyω(red, output) from a SH fre-
quency at 2ω(blue, input) through aχ (2) nonlinear interaction.b, Optical micrograph
of the microring with the 0.9 mm-long periodical-poled section highlighted. A SEM im-
age of the anti-reflection–coated chip facet is shown on the top right. The bottom panel
shows its microscope image of the poled domain pattern inside the resonator.c, SHG
efficiency calibration of a nearby poled waveguide, yielding 2516 %/W/cm 2.d, Pulley
coupler design illustrating phase matching of TE 0 modes between bus and resonator
waveguides. The FH mode is intentionally over-coupled to enable efficient external
coupling.e,f, Experimental transmission spectra at FH (e) and SH (f) wavelengths,
showing agreement with the coupled-mode design with the extracted externalQ-factors
ofQ e = 2.4×10 5, while intrinsicQ-factors areQ i = 2.1×10 6 (SH) andQ i = 2.6×10 6
(FH). The over-coupled FH resonance yields an escape efficiency of∼91.5%. Insets
show the simulated spatial mode profiles, confirming that both FH and SH modes are
supported within the same waveguide, enabling dual-resonant operation.
imately 42.2 GHz (fig. 1a). Due to the device dispersion and finite cavity linewidth,
only a subset of cavity resonances pairs across the FH and SH spectral bands satisfy
co-resonance condition where both light with frequencyωand 2ωcan simultaneously be
resonantly enhanced. In fig. 1b, the top panel shows a microscope image of the micror-
ing resonator. The region marked by white boxicorresponds to the scanning electron
microscope (SEM) image of chip facets, which are coated with optimized anti-reflection
layers to suppress Fresnel reflections and parasitic etalon effects for the squeezing light
output.
Quasi-phase-matching (QPM) is achieved through electric-field-assisted periodic
poling with a period of 4.742µm, chosen to generate the squeezed light at wavelength
within the 1540–1610 nm band based on the device dimension. White boxiihighlights
the region designated for periodic poling. High-voltage pulses with a few milliseconds
in duration, are applied across lithographically defined electrodes to invert ferroelectric
domains prior to waveguide etching. The bottom panel of fig. 1b shows a portion of the
4


# Page 5

0.9 mm-long poled section. By processing the 2-photon microscope image, we estimate
a poling duty cycle of 0.54±0.01 and an intensity contrast of 1.03±0.04 between the
poled and unpoled sections (see supplementary material SM Sec. II) . Based upon these
inferred values, our simulations predict a second-harmonic generation (SHG) efficiency
of 2570 %/W/cm2 which is in good agreement with the experimentally measured value
of 2516 %/W/cm2 obtained from an adjacent poled waveguide (fig. 1c).
The optical pulley coupler in the racetrack resonator is designed using dielectric per-
turbation theory. Along the ring waveguide path, the waveguide width is varied: the
straight sections at the top and bottom are set to 2µm to enhance nonlinear mode con-
finement and reduce loss, while tapering adiabatically to a narrower width of 1µm
when entering the curved sections with Euler bends. This design enables efficient
phase matching between the TE 0 modes of the bus and ring waveguides while sup-
pressing coupling to undesired higher-order modes, and provides over-coupling at the
FH wavelength to maximize the escape efficiency of the squeezed light. As shown in
fig. 1d, the pulley-coupler is designed to yield an externalQ-factorQ e ≈1.3×10 5
for the FH mode (star marker). The measured resonances closely match this design.
From the FH transmission spectrum in fig. 1e, we extract an externalQ-factor of
Qe = 2.4×10 5, indicating a strongly overcoupled cavity and yielding an escape effi-
ciency ofη esc =Q i/(Qi +Qe) = 91.5%. The intrinsicQ-factors extracted from fig. 1(e,f)
areQ i = 2.6×10 6 for the FH mode andQ i = 2.1×10 6 for the SH mode. To our knowl-
edge, it is the highest escape efficiency andQi ever achieved in the TF-PPLN resonators,
as a result of precise coupling engineering and co-design with low-loss nanofabrication
processes (see SM Sec. I). In previously reported on-chip resonators, pushing toward
strong overcoupling often leads to substantial degradation of intrinsic quality factor due
to parasitic coupling to undesired modes and additional scattering loss introduced in
the coupling region [47, 48]. In a resonant squeezing platform, high escape efficiency
ensures that the majority of the generated nonclassical field is extracted into the mea-
surement channel rather than dissipated internally, making it a key requirement for
achieving large observable squeezing.
We first characterize the nonlinear performance of our squeezer chip by measuring
its SHG spectrum using the setup shown in fig. 2a (see SM Sec. III for details). The
chip is mounted on a thermoelectric controller (TEC) for temperature tuning and sta-
bilization. Although the SHG occurs across the entire QPM bandwidth of 20 nm (3 dB)
centered around 1587 nm, only the light of the wavelength satisfying the co-resonance
condition can build up inside the cavity and consequently produce a significant SH
output. As shown in fig. 2b, several discrete SHG peaks appear within the QPM
range, with a spacing determined by the resonator FSRs of the FH and SH modes.
This co-resonance condition can be further optimized by temperature, exploiting the
different thermo-optic coefficients of the FH and SH modes, as shown in Figure 2c. De-
spite these changes in the discrete spectral peaks, the global spectral envelope remains
the same and closely matches the simulated QPM response of the poled waveguide,
confirming that the underlying nonlinear interaction and domain structure are uni-
form. The strong agreement between the measured envelope and the model further
verifies the high fidelity of the periodic poling. The simulated envelope is obtained
from a first-order quasi-phase-matched waveguide model using the numerically com-
puted effective-index dispersionn eff(λ) of the guided mode. We calculate the phase
mismatch ∆k(λ) =k 2ω(λ/2)−2k ω(λ), include the grating wavevector 2π/Λ associ-
5


# Page 6

Figure 2: SHG characterization of the on-chipχ (2) squeezer.a, SHG measurement
setup. A tunable NIR laser is coupled into the squeezer chip with the generated visible
light collected by a visible PD.b, SHG peaks appear at discrete positions within the
QPM bandwidth, where the FH and SH resonances simultaneously align. The peak
spacing of approximately 4 nm arises from the resonator FSRs of the two modes.c, SHG
spectra measured at different temperatures with the overall envelope matching with the
simulated QPM response of the poled waveguide.d, Power-dependent SHG efficiency
showing a normalized on-chip conversion efficiency of 30 157×104 %/W, extracted from
a linear fit to experimental data.
ated with the uniform poling period Λ, and evaluate the normalized spectral response
∝sinc 2([∆k(λ)−2π/Λ]L/2) for a uniform interaction lengthL= 0.9 mm. This model
assumes undepleted pump, single-mode propagation, and uniform domain structure,
and therefore captures the global quasi-phase-matching envelope rather than the dis-
crete resonant mode structure. Figure 2d shows the SHG efficiency calibration per-
formed under the co-resonant condition. The visible pump wavelength is selected at
the peak of the measured SH spectrum. In the undepleted-pump regime, the generated
second-harmonic power increases linearly with the on-chip fundamental power. A linear
fit to the data yields a normalized SHG efficiency of 30,157 %/W.
To characterize the parametric emission process, we first inject both SH and FH
light and monitor their transmission while tuning the chip temperature to locate the
co-resonance condition (fig. 3a and b, also see SM Sec. IV). fig. 3b shows the NIR (FH)
and visible (SH) transmission spectra under optimal temperature tuning, corresponding
to near-zero relative detuning between the two modes. The NIR transmission fringes
are a result of a seeded phase-sensitive parametric amplification and de-amplification.
The FH input is then blocked and only the SH pump—near 793.5 nm—is launched into
the cavity. The resulting squeezed light spectrum is recorded using an optical spec-
trum analyzer (OSA). The underlying parametric process and the experimental results
are illustrated in fig. 3c and fig. 3d, respectively. Both degenerate and nondegenerate
parametric sidebands are generated, producing a broadband squeezed-light spectrum
with evenly spaced frequency components. The inset in fig. 3d shows the frequency
spacing matches the NIR FSR (FSR FH) of 42.2 GHz. The spontaneous degenerate
parametric sidebands are achieved at 1587 nm with an on-chip power of 320 pW over a
6


# Page 7

Figure 3: Squeezed light spectrum characterization of the on-chipχ (2) squeezer.a,
Measurement setup. A visible pump laser near 793.5 nmdrives the squeezer chip un-
der the dual-resonant condition. An OSA records the output spectrum.b, Trans-
mission spectra of the two modes recorded, showing alternating amplification and de-
amplification features when the resonances overlap.c, When the pump excites the
co-resonant SH and FH modes, both degenerate and nondegenerate mode pairs are
generated, producing a broadband squeezed light spectrum with evenly spaced side-
bands.d, Measured on-chip quantum frequency comb spectrum, revealing broadband
parametric generation around 1587 nm. The inset shows zoomed-in cavity resonances
with uniform spacing matching the FSR FH.
cavity linewidth of 1.36 GHz, corresponding to 2.05 photon number per Hz which can
be also used to infer on-chip squeezing (see SM Sec. VII). Furthermore, the output
spontaneous parametric spectrum features more than 85 nW from 1512 nm to 1655 nm
and a 3-dB bandwidth over 10.3 THz consisting of 244 mode pairs. The high bright-
ness and the large spectral coverage of the parametric spectrum are a result of the
high escape efficiency, as well as the low group velocity dispersion (GVD,β 2) and the
compact poling length enabled by our dispersion-engineered PPLN resonator, respec-
tively. The platform allows for both near-degenerate single-mode and non-degenerate
two-mode squeezing operation in the same device simply by configuring only the local
oscillators. Leveraging the large Purcell enhancement factor in a cavity, the resonant
squeezer breaks the trade-off between squeezing ratio and bandwidth typically present
in a single-pass waveguide based device, though the squeezing comes at a form of dis-
crete frequency pairs. We further analyze the squeezed light spectra under different
pump–cavity detuning conditions and find that the squeezing power and the paramet-
ric gain are maximized at a near-zero detuning (SM Sec. VI). Such a dual-resonant
operation is therefore critical for achieving a strong parametric interaction and under-
pins the squeezing measurements discussed in subsequent sections.
To observe quadrature squeezing and measure the corresponding reduction in quan-
tum noise, the chip output is then interfered with a strong local oscilator (LO) us-
ing a balanced photodetector with a measured external quantum efficiency of 96 %
(fig. 4a). The fiber-based interferometer yields a balanced-homodyne interference with
17 milliradian relative phase stability and 91.5 % visibility. Phase control between the
7


# Page 8

Figure 4: Observation of squeezing from the dual-resonant integrated squeezer.a,
Layout of the experimental setup. The NIR laser is split into two paths of squeezing
generation and local oscillator before merging at the balanced homodyne detector. NIR:
near-infrared; LO: local oscillator; PM: phase modulator; COL: collimator; BS: beam
splitter; RSA: radio-frequency spectrum analyzer.b, Normalized quantum noise under
the sweeping of the squeezing angle, as shown in the lower trace of the phase-modulator
drive.−0.81 dB±0.04 dB squeezing and +4.29 dB±0.10 dB anti-squeezing are observed.
squeezed vacuum and the LO is implemented using an electro-optic phase modulator
(Thorlabs, LN65S-FC) in the LO path. Sweeping the squeezing angle over 0-πenables
the readout of the squeezed and anti-squeezed quadratures, corresponding to a reduced
and enhanced quantum noise. In our experiment, the triangular scan from−4 V to
+4 V corresponds to a full 2πphase sweep at 20 Hz. fig. 4b shows the detected noise
power at a sideband frequency of 20 MHz, normalized such that the shot noise corre-
sponds to 0 dB. We observe−0.81 dB±0.04 dB of squeezing and +4.29 dB±0.10 dB
of anti-squeezing at the input on-chip pump power of 27 mW. The dark noise of the
photodetector is 20 dB lower than the shot noise level, and the total detection loss
from the chip output to the BPD is 6.84 dB. While the observed squeezing is primarily
limited by the off-chip loss, the on-chip squeezing could also be further improved by in-
creasing the visible pump power to approach the limit of−10.6 dB posted by the device
escape efficiency if operating near the OPO threshold. We infer the on-chip squeezing
level using two complementary analyses based on loss tracking and photon-flux estima-
tion (see SM Sec. VII). In the loss-tracking analysis (SM Sec. VIIA), the measured
squeezing and anti-squeezing are related to the on-chip values through the output facet
transmission and the independently measured off-chip losses, including propagation
loss, mode-overlap visibility, and photodiode quantum efficiency. Solving the resulting
coupled nonlinear equations yields an output facet loss of 4.44 dB, and on-chip squeez-
ing and anti-squeezing levels of−7.52 dB and +9.62 dB, respectively. The extracted
8


# Page 9

output facet loss implies slightly asymmetric coupling losses between the input and
output facets, since the independently measured total input–output transmission loss
is 9 dB. Notably, this result demonstrates that quadrature variance measurements pro-
vide a practical method to extract the output facet loss of photonic integrated circuits,
which is otherwise difficult to access directly. Additionally, we estimate the on-chip
squeezing using a photon-flux model based on the measured squeezed-light power at
degeneracy (SM Sec. VIIB), obtaining−7.56 dB and +9.70 dB for squeezing and anti-
squeezing, respectively, in good agreement with the loss-tracking analysis. Uncertainty
analysis is performed via Monte Carlo error propagation based on the measurement
uncertainties of the relevant physical parameters, including the measured squeezing
(±0.04 dB), anti-squeezing (±0.10 dB), effective off-chip transmission (±0.2 dB), and
escape efficiency (±0.04 dB). This yields inferred on-chip squeezing and anti-squeezing
values of−7.52 dB±0.22 dB with 95% confidence interval of [−7.96,−7.10] dB and
+9.62 dB±0.25 dB with 95% confidence interval of [9.13,10.12] dB, respectively (de-
tails see SM Sec. VIIA)
Compared to the state-of-art integrated squeezed light generators, our dual-resonant
thin-film lithium niobate squeezer operates at pump power well below all previously
demonstratedχ (3) integrated squeezers, achieves the highest squeezing ratio and broad-
est parametric spectrum reported for cavity-basedχ (2) devices, and simultaneously
offers a far smaller footprint than waveguide-based implementations (fig. 5). High-
fidelity quasi-phase matching enables access to the largest effectiveχ (2) nonlinearity
in lithium niobate and supports a broader squeezing bandwidth compared with modal
phase-matching approaches. When combined with simultaneous resonance at both
the pump and squeezed wavelengths, this architecture dramatically reduces the re-
quired pump power, thereby mitigating the impact of excess laser noise and the risk
of optical-induced damage. In contrast toχ (3)-based demonstrations, which require
ultrahigh optical quality factors to reach appreciable squeezing, our platform achieves
large squeezing at a relaxed cavityQof only a few million, substantially easing fabri-
cation tolerances and improving scalability. The use of distinct pump and squeezing
wavelengths further allows independent control of the resonant conditions, enabling
operation in an extremely overcoupled regime exclusively at the squeezing wavelength
while maintaining optimal pump enhancement. Moreover, this work constitutes the
first demonstration to simultaneously overcome the high optical loss typically associ-
ated with domain-inversion-induced scattering, parasitic mode coupling, and etching
loss in long coupling regions, while preserving strong nonlinear interaction. The result-
ing compact, dispersion-engineered cavity supports an extended squeezing bandwidth,
providing a scalable route toward two-mode squeezing protocols spanning bandwidths
exceeding 10 THz.
3 Conclusion
In conclusion, we have demonstrated a chip-scale, dual-resonantχ (2) thin-film PPLN
squeezer that achieves continuous-wave squeezing and anti-squeezing of−0.81 dB±
0.04 dB and +4.29 dB±0.10 dB (−7.52 dB±0.22 dB and +9.62 dB±0.25 dB inferred on
chip) at unprecedentedly low pump power of 27 mW while maintaining high escape effi-
ciency of 91.5%, compact footprint of 0.6 mm2, and engineered spectral support of over
9


# Page 10

Figure 5: Literature comparison of integrated squeezed-light sources. Reported squeez-
ing and anti-squeezing levels are plotted against on-chip pump power for integrated
devices based onχ (2) (green) andχ (3) (magenta) nonlinearities. Marker shapes de-
note the device architecture of cavity (circle) and waveguide (cross). Preprint result
is indicated by an asterisk. Where available, reported squeezing or squeezed light
spectrum bandwidths are annotated next to the corresponding data points, including
multi-terahertz bandwidths for waveguide-based devices and a 10.3 THz spectral span
for our device. Our work occupies the low-power, high-squeezing regime near the left
side of the plot, underscoring the advantage of dual-resonant TFLN devices for efficient
squeezed-light generation. Ref. [45] is not included due to no inferred value (measured
−0.55 dB squeezing and 1.55 dB anti-squeezing).
10 THz within a single integrated device. Looking ahead, dispersion engineering enabled
by deeper etching and air cladding will reduce the GVD and thus further extend the
bandwidth of the squeezing spectrum, supporting ultra-broadband multi-terahertz two-
mode squeezing protocols. At the same time, poling-related etching loss can be further
reduced using etch-and-sidewall-poled fabrication approaches that avoids anisotropic
etching induced scattering [49]. The platform is intrinsically compatible with electro-
optic phase control, enabling fast modulation, Pound–Drever–Hall locking, and long-
term stabilization, and can be readily integrated with on-chip interferometric circuits.
At the same time, continued reduction of propagation and coupling losses through
optimized etching, sidewall smoothing, and low-loss fiber–chip interfaces will directly
increase the detectable squeezing. Reaching operation near the parametric oscillation
threshold—required for maximum gain and squeezing—will benefit from operation at
elevated temperature to suppress photorefractive–thermo-optic competition, providing
a pathway toward near-quantum-limited performance. Beyond squeezed-light genera-
tion, the dual-resonant architecture naturally supports low-noise parametric amplifica-
tion when operated in an overcoupled regime [50], quantum frequency combs [51, 52]
10


# Page 11

as well as high-brightness, high-rate spontaneous parametric down-conversion sources
using the same device geometry [53]. Together, these capabilities position thin-film
lithium niobate as a scalable and multifunctional platform for compact, power-efficient,
and broadband continuous-variable quantum photonics.
Data availability
The datasets generated and analyzed in the current study are available from the corre-
sponding authors on reasonable request.
Acknowledgements
This work is supported by the DARPA INSPIRED program (HR001123S0052) and the
DARPA Young Faculty Award (D23AP00252-02). We thank Wenxuan Jia for technical
advice on the fiber interferometer and phase noise analysis, Ian Christen for advice on
experimental stabilization, and Kamila Kunes for squeezing simulations. Two-photon
imaging experiments were conducted at the CRL Molecular Imaging Center, RRID:
SCR017852, supported by NIH grant S10OD025063. Device fabrication was performed
at the John O’Brien Nanofabrication Laboratory at University of Southern California
and Marvell Nanofabrication Laboratory at University of California, Berkeley. M.Y.,
Y.Y. and T.S.K. are supported by the U.S. Department of Energy, Office of Science,
Basic Energy Sciences, Materials Sciences and Engineering Division under Contract No.
DE-AC02-05CH11231 within the Quantum Coherent Systems Program KCAS26. The
views, opinions and/or findings expressed are those of the authors and should not be
interpreted as representing the official views or policies of the Department of Defense
or the U.S. Government.
Author contributions
M.Y. conceived the idea. C.-H.L. designed the chip with the help of X.R., R.K. and
T.K.. C.-H.L. and T.S.K. fabricated the devices and developed the fabrication processes
with the help of C.C. and Y.Y.. X.R. and R.K. carried out the experiments and
analyzed the data with help from K.K., R.Y., and L.Z.. S.-Y.M. and B.-H.W. performed
theoretical calculations, supervised by D.E.. Q.Z. developed the theoretical model for
inferred squeezing. X.R., R.K. and T.K. wrote the manuscript with contribution from
all authors. M.Y. and Z.C. supervised the project.
Competing interests
C.-H.L., L.Z., Z.C. and M.Y. are involved in developing lithium niobate technologies at
Opticore Inc.
11


# Page 12

References
[1] Horace P Yuen. Two-photon coherent states of the radiation field.Physical Review
A, 13(6):2226, 1976.
[2] Daniel F Walls. Squeezed states of light.nature, 306(5939):141–146, 1983.
[3] Benjamin J Lawrie, Paul D Lett, Alberto M Marino, and Raphael C Pooser. Quan-
tum sensing with squeezed light.Acs Photonics, 6(6):1307–1318, 2019.
[4] Valeriy Novikov, Jun Jia, T´ ulio Brito Brasil, Andrea Grimaldi, Ma¨ ımouna Bocoum,
Mikhail Balabas, J¨ org Helge M¨ uller, Emil Zeuthen, and Eugene Simon Polzik.
Hybrid quantum network for sensing in the acoustic frequency range.Nature,
643(8073):955–960, July 2025.
[5] Wenxuan Jia, Victoria Xu, Kevin Kuns, Masayuki Nakano, Lisa Barsotti, Matthew
Evans, Nergis Mavalvala, and members of the LIGO Scientific Collaboration.
Squeezing the quantum noise of a gravitational-wave detector below the standard
quantum limit.Science, 385(6715):1318–1321, September 2024.
[6] D. Ganapathy, W. Jia, M. Nakano, V. Xu, N. Aritomi, T. Cullen, N. Kijbun-
choo, S. E. Dwyer, A. Mullavey, L. McCuller, and LIGO O4 Detector Collabora-
tion. Broadband Quantum Enhancement of the LIGO Detectors with Frequency-
Dependent Squeezing.Physical Review X, 13(4):041021, October 2023.
[7] Virgo Collaboration. Frequency-Dependent Squeezed Vacuum Source for
the Advanced Virgo Gravitational-Wave Detector.Physical Review Letters,
131(4):041403, July 2023.
[8] Yuhang Zhao, Naoki Aritomi, Eleonora Capocasa, Matteo Leonardi, Marc Eisen-
mann, Yuefan Guo, Eleonora Polini, Akihiro Tomura, Koji Arai, Yoichi Aso, Yao-
Chin Huang, Ray-Kuang Lee, Harald L¨ uck, Osamu Miyakawa, Pierre Prat, Ayaka
Shoda, Matteo Tacca, Ryutaro Takahashi, Henning Vahlbruch, Marco Vardaro,
Chien-Ming Wu, Matteo Barsuglia, and Raffaele Flaminio. Frequency-Dependent
Squeezed Vacuum Source for Broadband Quantum Noise Reduction in Advanced
Gravitational-Wave Detectors.Physical Review Letters, 124(17):171101, April
2020.
[9] Catxere A. Casacio, Lars S. Madsen, Alex Terrasson, Muhammad Waleed, Kai
Barnscheidt, Boris Hage, Michael A. Taylor, and Warwick P. Bowen. Quantum-
enhanced nonlinear microscopy.Nature, 594(7862):201–206, June 2021.
[10] Michael A. Taylor, Jiri Janousek, Vincent Daria, Joachim Knittel, Boris Hage,
Hans-A. Bachor, and Warwick P. Bowen. Biological measurement beyond the
quantum limit.Nature Photonics, 7(3):229–233, March 2013.
[11] Daniel I. Herman, Mathieu Walsh, Molly Kate Kreider, Noah Lordi, Eugene J.
Tsao, Alexander J. Lind, Matthew Heyrich, Joshua Combes, J´ erˆ ome Genest, and
Scott A. Diddams. Squeezed dual-comb spectroscopy.Science, 387(6734):653–658,
February 2025.
12


# Page 13

[12] Abdulkarim Hariri, Shuai Liu, Haowei Shi, Quntao Zhuang, Xudong Fan, and
Zheshen Zhang. Entangled dual-comb spectroscopy.Phys. Rev. X, 15:041009, Oct
2025.
[13] Zheshen Zhang and Quntao Zhuang. Distributed quantum sensing.Quantum
Science and Technology, 6(4):043001, 2021.
[14] Yi Xia, Wei Li, William Clark, Darlene Hart, Quntao Zhuang, and Zheshen Zhang.
Demonstration of a reconfigurable entangled radio-frequency photonic sensor net-
work.Physical Review Letters, 124(15):150502, 2020.
[15] Xueshi Guo, Casper R Breum, Johannes Borregaard, Shuro Izumi, Mikkel V
Larsen, Tobias Gehring, Matthias Christandl, Jonas S Neergaard-Nielsen, and Ul-
rik L Andersen. Distributed quantum sensing in a continuous-variable entangled
network.Nature Physics, 16(3):281–284, 2020.
[16] Yi Xia, Aman R Agrawal, Christian M Pluchar, Anthony J Brady, Zhen Liu,
Quntao Zhuang, Dalziel J Wilson, and Zheshen Zhang. Entanglement-enhanced
optomechanical sensing.Nature Photonics, 17(6):470–477, 2023.
[17] Florian Fesquet, Fabian Kronowetter, Michael Renger, Wun Kwan Yam, Simon
Gandorfer, Kunihiro Inomata, Yasunobu Nakamura, Achim Marx, Rudolf Gross,
and Kirill G. Fedorov. Demonstration of microwave single-shot quantum key dis-
tribution.Nature Communications, 15(1):7544, August 2024.
[18] Huy Q. Nguyen, Ivan Derkach, Adnan A. E. Hajomer, Hou-Man Chin, Akash nag
Oruganti, Ulrik L. Andersen, Vladyslav Usenko, and Tobias Gehring. Digital
reconstruction of squeezed light for quantum information processing.npj Quantum
Information, 11(1):71, May 2025.
[19] Melissa A. Guidry, Daniil M. Lukin, Ki Youl Yang, and Jelena Vuˇ ckovi´ c. Multi-
mode squeezing in soliton crystal microcombs.Optica, 10(6):694–701, June 2023.
[20] Ze Wang, Kangkang Li, Yue Wang, Xin Zhou, Yinke Cheng, Boxuan Jing, Fengxiao
Sun, Jincheng Li, Zhilin Li, Bingyan Wu, Qihuang Gong, Qiongyi He, Bei-Bei Li,
and Qi-Fan Yang. Large-scale cluster quantum microcombs.Light: Science &
Applications, 14(1):164, April 2025.
[21] Shunya Konno, Warit Asavanant, Fumiya Hanamura, Hironari Nagayoshi, Kosuke
Fukui, Atsushi Sakaguchi, Ryuhoh Ide, Fumihiro China, Masahiro Yabuno, Shige-
hito Miki, Hirotaka Terai, Kan Takase, Mamoru Endo, Petr Marek, Radim Filip,
Peter van Loock, and Akira Furusawa. Logical states for fault-tolerant quantum
computation with propagating light.Science, 383(6680):289–293, January 2024.
[22] H. Aghaee Rad, T. Ainsworth, R. N. Alexander, B. Altieri, M. F. Askarani,
R. Baby, L. Banchi, B. Q. Baragiola, J. E. Bourassa, R. S. Chadwick, I. Cha-
rania, H. Chen, M. J. Collins, P. Contu, N. D’Arcy, G. Dauphinais, R. De Prins,
D. Deschenes, I. Di Luch, S. Duque, P. Edke, S. E. Fayer, S. Ferracin, H. Ferretti,
J. Gefaell, S. Glancy, C. Gonz´ alez-Arciniegas, T. Grainge, Z. Han, J. Hastrup,
L. G. Helt, T. Hillmann, J. Hundal, S. Izumi, T. Jaeken, M. Jonas, S. Kocsis,
13


# Page 14

I. Krasnokutska, M. V. Larsen, P. Laskowski, F. Laudenbach, J. Lavoie, M. Li,
E. Lomonte, C. E. Lopetegui, B. Luey, A. P. Lund, C. Ma, L. S. Madsen, D. H.
Mahler, L. Mantilla Calder´ on, M. Menotti, F. M. Miatto, B. Morrison, P. J. Nad-
karni, T. Nakamura, L. Neuhaus, Z. Niu, R. Noro, K. Papirov, A. Pesah, D. S.
Phillips, W. N. Plick, T. Rogalsky, F. Rortais, J. Sabines-Chesterking, S. Safavi-
Bayat, E. Sazhaev, M. Seymour, K. Rezaei Shad, M. Silverman, S. A. Srinivasan,
M. Stephan, Q. Y. Tang, J. F. Tasker, Y. S. Teo, R. B. Then, J. E. Tremblay,
I. Tzitrin, V. D. Vaidya, M. Vasmer, Z. Vernon, L. F. S. S. M. Villalobos, B. W.
Walshe, R. Weil, X. Xin, X. Yan, Y. Yao, M. Zamani Abnili, and Y. Zhang. Scal-
ing and networking a modular photonic quantum computer.Nature, pages 1–8,
January 2025.
[23] H. Vahlbruch, M. Mehmet, S. Chelkowski, B. Hage, A. Franzen, N. Lastzka,
S. Goßler, K. Danzmann, and R. Schnabel. Detection of 15 db squeezed states
of light and their application for the absolute calibration of photoelectric quantum
efficiency.Physical Review Letters, 117(11):110801, September 2016.
[24] Roman Schnabel. Squeezed states of light and their applications in laser interfer-
ometers.Physics Reports, 684:1–51, July 2017.
[25] Ulrich B. Hoff, Bo M. Nielsen, and Ulrik L. Andersen. Integrated source of broad-
band quadrature squeezed light.Optics Express, 23(9):12013–12036, May 2015.
[26] Avik Dutt, Kevin Luke, Sasikanth Manipatruni, Alexander L. Gaeta, Paulo
Nussenzveig, and Michal Lipson. On-Chip Optical Squeezing.Physical Review
Applied, 3(4):044005, April 2015.
[27] Xiyuan Lu, Gregory Moille, Anshuman Singh, Qing Li, Daron A. Westly, Ashutosh
Rao, Su-Peng Yu, Travis C. Briles, Scott B. Papp, and Kartik Srinivasan.
Milliwatt-threshold visible–telecom optical parametric oscillation using silicon
nanophotonics.Optica, 6(12):1535–1541, December 2019.
[28] Yun Zhao, Yoshitomo Okawachi, Jae K. Jang, Xingchen Ji, Michal Lipson, and
Alexander L. Gaeta. Near-Degenerate Quadrature-Squeezed Vacuum Generation
on a Silicon-Nitride Chip.Physical Review Letters, 124(19):193601, May 2020.
[29] V. D. Vaidya, B. Morrison, L. G. Helt, R. Shahrokshahi, D. H. Mahler, M. J.
Collins, K. Tan, J. Lavoie, A. Repingon, M. Menotti, N. Quesada, R. C. Pooser,
A. E. Lita, T. Gerrits, S. W. Nam, and Z. Vernon. Broadband quadrature-squeezed
vacuum and nonclassical photon number correlations from a nanophotonic device.
Science Advances, 6(39):eaba9186, September 2020.
[30] Y. Zhang, M. Menotti, K. Tan, V. D. Vaidya, D. H. Mahler, L. G. Helt, L. Zatti,
M. Liscidini, B. Morrison, and Z. Vernon. Squeezed light from a nanophotonic
molecule.Nature Communications, 12(1):2233, April 2021.
[31] Zijiao Yang, Mandana Jahanbozorgi, Dongin Jeong, Shuman Sun, Olivier Pfister,
Hansuek Lee, and Xu Yi. A squeezed quantum microcomb on a chip.Nature
Communications, 12(1):4781, August 2021.
14


# Page 15

[32] Johann Riemensberger, Nikolai Kuznetsov, Junqiu Liu, Jijun He, Rui Ning Wang,
and Tobias J. Kippenberg. A photonic integrated continuous-travelling-wave para-
metric amplifier.Nature, 612(7938):56–61, December 2022.
[33] Yichen Shen, Ping-Yen Hsieh, Sashank Kaushik Sridhar, Samantha Feldman, You-
Chia Chang, Thomas A. Smith, and Avik Dutt. Strong nanophotonic quantum
squeezing exceeding 3.5 dB in a foundry-compatible Kerr microresonator.Optica,
12(3):302–308, March 2025.
[34] Yichen Shen, Ping-Yen Hsieh, Dhruv Srinivasan, Antoine Henry, Gregory Moille,
Sashank Kaushik Sridhar, Alessandro Restelli, You-Chia Chang, Kartik Srinivasan,
Thomas A. Smith, and Avik Dutt. Highly squeezed nanophotonic quantum mi-
crocombs with broadband frequency tunability, May 2025.
[35] Mandana Jahanbozorgi, Zijiao Yang, Shuman Sun, Haoran Chen, Ruxuan Liu,
Beichen Wang, and Xu Yi. Generation of squeezed quantum microcombs with
silicon nitride integrated photonic circuits.Optica, 10(8):1100–1101, August 2023.
[36] Robert Cernansky and Alberto Politi. Nanophotonic source of quadrature squeez-
ing via self-phase modulation.APL Photonics, 5:101303–1–101303–5, 2020.
[37] Rajveer Nehra, Ryoto Sekine, Luis Ledezma, Qiushi Guo, Robert M. Gray,
Arkadev Roy, and Alireza Marandi. Few-cycle vacuum squeezing in nanophotonics.
Science, 377(6612):1333–1337, September 2022.
[38] F. Mondain, T. Lunghi, A. Zavatta, E. Gouzien, F. Doutre, M. De Micheli,
S. Tanzilli, and V. D’Auria. Chip-based squeezing at a telecom wavelength.Pho-
tonics Research, 7(7):A36–A39, July 2019.
[39] Pao-Kang Chen, Ian Briggs, Songyan Hou, and Linran Fan. Ultra-broadband
quadrature squeezing with thin-film lithium niobate nanophotonics.Optics Letters,
47(6):1506–1509, March 2022.
[40] Xiaodong Shi, Angela Anna Baiju, Xu Chen, Sakthi Sanjeev Mohanraj, Sihao
Wang, Veerendra Dhyani, Biveen Shajilal, Mengyao Zhao, Ran Yang, Yue Li,
Guangxing Wu, Hao Hao, Victor Leong, Ping Koy Lam, and Di Zhu. Squeezed light
generation in periodically poled thin-film lithium niobate waveguides.Nanopho-
tonics, 14(26):4721–4727, 2025.
[41] Takahiro Kashiwazaki, Naoto Takanashi, Taichi Yamashima, Takushi Kazama,
Koji Enbutsu, Ryoichi Kasahara, Takeshi Umeki, and Akira Furusawa.
Continuous-wave 6-dB-squeezed light with 2.5-THz-bandwidth from single-mode
PPLN waveguide.APL Photonics, 5:036104–1–036104–5, 2020.
[42] Alexander W. Bruch, Xianwen Liu, Joshua B. Surya, Chang-Ling Zou, and Hong X.
Tang. On-chipχ(2) microring optical parametric oscillator.Optica, 6(10):1361–
1366, October 2019.
15


# Page 16

[43] Juanjuan Lu, Joshua B. Surya, Xianwen Liu, Alexander W. Bruch, Zheng Gong,
Yuntao Xu, and Hong X. Tang. Periodically poled thin-film lithium niobate mi-
croring resonators with a second-harmonic generation efficiency of 250,000%/W.
Optica, 6(12):1455–1460, December 2019.
[44] Juanjuan Lu, Ayed Al Sayem, Zheng Gong, Joshua B. Surya, Chang-Ling Zou, and
Hong X. Tang. Ultralow-threshold thin-film lithium niobate optical parametric
oscillator.Optica, 8(4):539–544, April 2021.
[45] Taewon Park, Hubert Stokowski, Vahid Ansari, Samuel Gyger, Kevin K. S. Mul-
tani, Oguz Tolga Celik, Alexander Y. Hwang, Devin J. Dean, Felix Mayor, Timo-
thy P. McKenna, Martin M. Fejer, and Amir Safavi-Naeini. Single-mode squeezed-
light generation and tomography with an integrated optical parametric oscillator.
Science Advances, 10(11):eadl1814, March 2024.
[46] Tummas Napoleon Arge, Seongmin Jo, Huy Quang Nguyen, Francesco Lenzini,
Emma Lomonte, Jens Arnbak Holbøll Nielsen, Renato R. Domeneguetti,
Jonas Schou Neergaard-Nielsen, Wolfram Pernice, Tobias Gehring, and Ulrik Lund
Andersen. Demonstration of a squeezed light source on thin-film lithium niobate
with modal phase matching.Optica Quantum, 3(5):467–473, 2025.
[47] Martin H. P. Pfeiffer, Junqiu Liu, Michael Geiselmann, and Tobias J. Kippenberg.
Coupling ideality of integrated planar high-q microresonators.Physical Review
Applied, 7(2):024026, 2017.
[48] Mark W. Puckett, Junqiu Liu, Kyle Nelson, and Kerry J. Vahala. 422 million
intrinsic quality factor planar integrated all-waveguide resonator with sub-mhz
linewidth.Nature Communications, 12:934, 2021.
[49] C. A. A. Franken, S. S. Ghosh, C. C. Rodrigues, J. Yang, C. J. Xin, S. Lu, D. Witt,
G. Joe, G. S. Wiederhecker, K.-J. Boller, and M. Lonˇ car. Milliwatt-level uv gen-
eration using sidewall poled lithium niobate.arXiv preprint, 2025.
[50] Yun Zhao, Jae K. Jang, Xingchen Ji, Yoshitomo Okawachi, Michal Lipson, and
Alexander L. Gaeta. Large regenerative parametric amplification on chip at ultra-
low pump powers.Optica, 10(7):819–825, 2023.
[51] Haowei Shi, Zaijun Chen, Scott E. Fraser, Mengjie Yu, Zheshen Zhang, and Quntao
Zhuang. Entanglement-enhanced dual-comb spectroscopy.npj Quantum Informa-
tion, 9(1):91, 2023.
[52] Michael Kues, Christian Reimer, Piotr Roztocki, Luis Romero Cort´ es, Stefania
Sciara, Benjamin Wetzel, Yanbing Zhang, Alfonso Cino, Sai T. Chu, Brent E.
Little, David J. Moss, Lucia Caspani, Jos´ e Aza˜ na, and Roberto Morandotti. On-
chip generation of high-dimensional entangled quantum states and their coherent
control.Nature, 546(7660):622–626, 2017.
[53] Zhaohui Ma, Jia-Yang Chen, Zhan Li, Chao Tang, Yong Meng Sua, Heng Fan, and
Yu-Ping Huang. Ultrabright quantum photon sources on chip.Physical Review
Letters, 125(26):263602, 2020.
16
