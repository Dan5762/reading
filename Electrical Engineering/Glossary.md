# Electrical Engineering Glossary — Foundations for Solar and Grid Infrastructure

A unified reference covering the core concepts needed before diving deeper into solar energy production, power systems, and grid infrastructure.

---

## 1. Circuit Fundamentals

- **Voltage**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

- **Current**
  The flow of electric charge through a conductor, measured in amperes (A). Conventional current flows from positive to negative potential, while electron flow is in the opposite direction. In AC systems, current alternates direction sinusoidally, and its magnitude and phase relationship to voltage determine how power is transferred. Current is the primary quantity that causes heating in conductors (via I²R losses) and is the basis for most protection system operation.

- **Resistance**
  The opposition to current flow in a conductor, measured in ohms (Ω). It arises from collisions between charge carriers and the atomic lattice of the material, converting electrical energy into heat. Resistance is a purely real quantity: it dissipates energy and does not store it. In power systems, cable resistance is a key factor in voltage drop calculations and power losses, and increases with temperature, which creates a feedback loop under heavy loading.

- **Impedance**
  The AC generalisation of resistance, expressed as a complex number Z = R + jX in ohms (Ω). The real part R represents resistance (energy dissipation) and the imaginary part X represents reactance (energy storage and release). The magnitude |Z| gives the ratio of voltage amplitude to current amplitude, while the phase angle gives the time shift between them. Impedance is the central concept in AC circuit analysis and power system modelling: every cable, transformer, generator, and load is characterised by its impedance.

- **Reactance (inductive and capacitive)**
  The component of impedance that stores and returns energy rather than dissipating it, measured in ohms (Ω). Inductive reactance (X_L = ωL) arises from magnetic energy storage in coils and increases with frequency, causing current to lag voltage. Capacitive reactance (X_C = 1/ωC) arises from electric field energy storage and decreases with frequency, causing current to lead voltage. In power systems, the balance between inductive and capacitive reactance on a network determines voltage profiles and reactive power flows.

- **Admittance**
  The reciprocal of impedance, Y = 1/Z = G + jB, measured in siemens (S). It represents how easily current flows through a circuit element at a given voltage. Admittance is used extensively in power system load flow analysis because the admittance matrix (Y-bus) of a network is sparse and computationally efficient to construct. The real part is conductance (G) and the imaginary part is susceptance (B).

- **Conductance**
  The real part of admittance, measured in siemens (S), representing the component of current that is in phase with voltage. It is the reciprocal of resistance for a purely resistive element. In the admittance formulation of power networks, conductance represents the resistive losses in lines and transformers. It is always positive and corresponds to real power dissipation.

- **Susceptance**
  The imaginary part of admittance, measured in siemens (S), representing the component of current that is 90° out of phase with voltage. Positive susceptance corresponds to capacitive behaviour (current leads voltage) and negative susceptance to inductive behaviour (current lags voltage). In power system models, the shunt susceptance of cables and overhead lines represents their capacitance to ground, which becomes significant at higher voltages and longer distances. This is the quantity that causes the Ferranti effect on lightly loaded long lines.

- **Ohm's Law (DC and AC forms)**
  In DC circuits, Ohm's law states V = IR: the voltage across a resistor equals the product of current and resistance. In AC circuits, this generalises to V = IZ, where V, I, and Z are complex quantities (phasors and impedance). The AC form encodes both the amplitude relationship and the phase relationship between voltage and current in a single equation. This generalisation is the foundation of all AC circuit analysis, from simple RLC circuits to entire power networks.

- **Kirchhoff's Current Law (KCL)**
  States that the algebraic sum of all currents entering and leaving any node in a circuit must equal zero. This is a direct consequence of charge conservation: charge cannot accumulate at a node. In power system analysis, KCL is applied at every bus to relate the injected power (from generators and loads) to the power flowing through connected branches. It is one of the two fundamental laws (alongside KVL) from which all circuit analysis methods are derived.

- **Kirchhoff's Voltage Law (KVL)**
  States that the algebraic sum of all voltages around any closed loop in a circuit must equal zero. This is a consequence of energy conservation: a charge returning to its starting point must have the same potential energy. In power systems, KVL governs the relationship between bus voltages and the voltage drops across line impedances. Together with KCL, it forms the mathematical basis for load flow equations and fault analysis.

- **Thevenin's Theorem**
  A theorem stating that any linear circuit, as seen from two terminals, can be replaced by a single voltage source (V_Th) in series with a single impedance (Z_Th). V_Th is the open-circuit voltage at the terminals, and Z_Th is the impedance seen from the terminals with all independent sources deactivated. This is enormously useful in power systems: the fault level at a bus is determined by the Thevenin impedance looking into the network from that bus. It simplifies complex networks into a single source-impedance pair for analysis of loading, faults, and voltage regulation.

- **Norton's Theorem**
  The dual of Thevenin's theorem: any linear circuit can be replaced by a current source (I_N) in parallel with an impedance (Z_N). I_N is the short-circuit current at the terminals, and Z_N equals the Thevenin impedance. Norton and Thevenin equivalents are interconvertible via I_N = V_Th/Z_Th. The Norton form is often more convenient when working with admittance-based formulations, as used in the Y-bus representation of power networks.

- **Superposition Theorem**
  A principle stating that in a linear circuit with multiple sources, the response (voltage or current) at any point is the sum of the responses due to each source acting alone. To apply it, you deactivate all sources except one (replacing voltage sources with short circuits and current sources with open circuits), solve, and repeat for each source. It is valid only for linear circuits and does not apply directly to power calculations (since power is a nonlinear function of voltage and current). In power systems, superposition is used in fault analysis to separate the pre-fault load flow from the fault-induced components.

- **Maximum Power Transfer Theorem**

- **Complex Power**
  The product of voltage phasor and the conjugate of current phasor, S = VI*, measured in volt-amperes (VA). It encapsulates all power information in a single complex number: S = P + jQ, where P is real power and Q is reactive power. The magnitude |S| is apparent power. Complex power is the most compact way to describe the power state at any point in an AC network and is the quantity conserved across ideal transformers.

- **Real Power (Active Power)**
  The component of power that performs useful work or is irreversibly dissipated as heat, measured in watts (W). It is the time-averaged product of voltage and the component of current in phase with it: P = VI cos(φ). Real power is what generators must ultimately supply and what consumers pay for. In a power system, real power must be balanced instantaneously between generation and demand; any imbalance causes frequency to deviate from 50 Hz.

- **Reactive Power**
  The component of power that oscillates between source and load without performing net work, measured in volt-amperes reactive (VAr). It arises from energy being alternately stored in and released from magnetic fields (inductive loads) or electric fields (capacitive loads): Q = VI sin(φ). Reactive power is essential for maintaining voltage levels across the network, since voltage at a bus is strongly influenced by the local reactive power balance. Although it does no net work, it increases the current flowing through conductors and therefore increases losses.

- **Apparent Power**
  The product of RMS voltage and RMS current magnitudes, |S| = |V||I|, measured in volt-amperes (VA). It represents the total current-carrying capacity required to deliver a given combination of real and reactive power. Equipment (transformers, cables, generators) is rated in VA or MVA because their thermal limits depend on current magnitude regardless of power factor. Apparent power relates to real and reactive power by |S|² = P² + Q².

- **Power Factor**
  The ratio of real power to apparent power, cos(φ) = P/|S|, ranging from 0 to 1. A power factor of 1 means all current is doing useful work; a power factor of 0.5 means the equipment must carry twice the current needed for the actual power delivered. Low power factor increases losses and requires oversized equipment. Industrial consumers are often penalised for low power factor, and power factor correction (typically via capacitor banks) is a routine part of electrical installation design.

- **Power Triangle**
  A right-angled triangle relating real power (P, horizontal), reactive power (Q, vertical), and apparent power (|S|, hypotenuse). The angle between P and |S| is the power factor angle φ. It provides an intuitive geometric representation of how the three power quantities relate, and makes it easy to see the effect of adding capacitive or inductive compensation. The power triangle is a standard tool for sizing equipment and designing power factor correction.

- **Phasor**
  A complex number representing the magnitude and phase of a sinusoidal quantity at a fixed frequency. A voltage v(t) = V_m cos(ωt + φ) is represented as the phasor V = V_m∠φ (or equivalently V_m e^{jφ}). Phasors eliminate the need to work with time-domain trigonometric functions, reducing AC circuit analysis to complex algebra. They are valid only for sinusoidal steady-state analysis at a single frequency, but this covers the vast majority of power system operating conditions.

- **Phasor Diagram**
  A graphical representation showing voltage and current phasors as arrows in the complex plane, with length proportional to magnitude and angle representing phase. It makes the phase relationships between different quantities immediately visible: for example, you can see at a glance whether current leads or lags voltage. Phasor diagrams are used extensively in power system analysis to understand generator operation, transformer behaviour, and the effect of compensation equipment. They are particularly useful for visualising the voltage drop across a line as the vector sum of resistive and reactive components.

- **RMS (Root Mean Square)**
  A method of computing the effective value of a time-varying signal, defined as the square root of the mean of the squared instantaneous values over one period. For a sinusoidal waveform with peak value V_m, the RMS value is V_m/√2. RMS values are used because they give the equivalent DC value that would produce the same heating in a resistor: a 230V RMS supply delivers the same power as a 230V DC supply into a resistive load. All standard voltage and current ratings in power systems are RMS values unless explicitly stated otherwise.

- **Peak vs RMS Voltage**
  Peak voltage is the maximum instantaneous value of a sinusoidal waveform, while RMS voltage is the effective value used for power calculations. They are related by V_peak = √2 × V_RMS, so a 230V RMS mains supply has a peak voltage of approximately 325V. This distinction matters for insulation design (which must withstand peak voltage) and for power electronics (where switching devices see peak values). Confusion between peak and RMS is a common source of errors in circuit design and measurement.

- **Series and Parallel Impedance**
  Impedances in series add directly (Z_total = Z_1 + Z_2), just like resistances in DC, but with complex arithmetic. Impedances in parallel combine as 1/Z_total = 1/Z_1 + 1/Z_2, or equivalently Z_total = Z_1Z_2/(Z_1 + Z_2). These rules are the foundation of circuit reduction and network simplification. In power systems, series impedance of lines and transformers causes voltage drop, while parallel paths through the network share current according to their impedance ratios.

- **Voltage Divider**
  A circuit where two impedances in series share the source voltage in proportion to their individual impedances: V_2 = V_source × Z_2/(Z_1 + Z_2). This is the basis for understanding voltage drop along a feeder: the cable impedance and the load impedance form a voltage divider, and the load voltage is always less than the source voltage. In power distribution, the voltage divider effect of cable impedance is the primary reason that voltage regulation degrades with distance from the substation. The concept extends naturally to AC circuits using complex impedances.

- **Current Divider**
  When two impedances are in parallel, the total current divides between them inversely proportional to their impedances: I_1 = I_total × Z_2/(Z_1 + Z_2). More current flows through the lower impedance path. In power systems, current dividers describe how fault current distributes between parallel feeders, how load current splits between parallel transformers, and how harmonic currents divide between the supply and filter paths. The principle is the dual of the voltage divider and equally fundamental to circuit analysis.

- **Source Impedance**
  The internal impedance of a source (generator, grid supply, or Thevenin equivalent), which determines how much the terminal voltage drops under load. A low source impedance means the source is "stiff" and can supply large currents without significant voltage drop. The source impedance of the grid at a particular point determines the fault level at that point, the voltage regulation under varying load, and the harmonic voltage distortion caused by nonlinear loads. For domestic supplies in the UK, the source impedance at the meter is typically 0.2-0.8 Ω.

- **Load Impedance**
  The impedance presented by the equipment consuming power. It determines how much current the load draws at a given voltage, and the power factor at which it operates. Load impedance can be resistive (heaters, incandescent lamps), inductive (motors, transformers), capacitive (power factor correction), or a complex combination. In power system studies, loads are often modelled as constant power, constant current, or constant impedance, depending on which approximation best captures their behaviour.

- **Impedance Matching**
  The practice of designing the load impedance to equal the complex conjugate of the source impedance in order to maximise power transfer. In power systems, impedance matching is generally not a goal because maximising power transfer also means dissipating half the power in the source impedance, which is unacceptably inefficient. However, the concept is important in communications, measurement, and some power electronics applications. In power delivery, the objective is instead to minimise losses, which means making source impedance as low as possible relative to load impedance.

## 2. AC Circuit Theory

- **Sinusoidal Steady State**
  The condition in which all voltages and currents in a linear circuit are sinusoidal at the same frequency, with constant amplitudes and fixed phase relationships. This occurs after all transients have died away following any switching event or disturbance. The vast majority of power system analysis assumes sinusoidal steady state, which is what allows the use of phasors and impedance. Deviations from this assumption (harmonics, transients, faults) require more advanced analysis techniques.

- **Angular Frequency**
  The rate of change of the phase angle of a sinusoidal waveform, ω = 2πf, measured in radians per second. For a 50 Hz power system, ω = 314.16 rad/s. Angular frequency appears in the expressions for inductive reactance (X_L = ωL) and capacitive reactance (X_C = 1/ωC), so it directly determines the impedance of energy storage elements. It is the natural unit for expressing frequency in mathematical analysis because it avoids the constant factor of 2π.

- **Phase Angle**
  The angular displacement of a sinusoidal waveform relative to a reference, measured in degrees or radians. In power systems, the phase angle between voltage and current at a load determines the power factor. The phase angle between voltages at two buses determines the real power flow between them (power flows from the leading bus to the lagging bus). Phase angles are the primary unknown variables in load flow analysis.

- **Phase Shift**
  The difference in phase angle between two sinusoidal waveforms of the same frequency. A phase shift can be introduced by reactive elements (inductors and capacitors), by transformers (depending on vector group), or by deliberate control action. In power electronics, phase shift between switching signals is used to control power flow in dual active bridge converters. The concept is distinct from the absolute phase angle: it is always relative.

- **Leading and Lagging Current**
  Describes whether current reaches its peak before or after voltage in each cycle. Current is said to lead voltage in capacitive circuits (the capacitor's stored charge drives current ahead of the voltage change) and lag voltage in inductive circuits (the inductor opposes changes in current). In power system convention, generators typically produce lagging current (they export reactive power to inductive loads). The distinction is crucial for understanding reactive power flow and for specifying power factor correction equipment.

- **Resonance (series and parallel)**
  Occurs when the inductive and capacitive reactances in a circuit are equal, causing them to cancel. In a series RLC circuit, resonance minimises impedance to just R, maximising current for a given voltage. In a parallel RLC circuit, resonance maximises impedance, minimising current drawn from the source. Resonance is critically important in power systems because the interaction between cable capacitance and transformer inductance can create resonant frequencies that amplify harmonics, potentially causing equipment damage or protection malfunction.

- **Quality factor (Q factor)**
  A dimensionless measure of how underdamped a resonant circuit is, defined as the ratio of energy stored to energy dissipated per cycle. For a series RLC circuit, Q = (1/R)√(L/C). A high Q means a sharp resonance peak and large amplification of signals near the resonant frequency. In power systems, high-Q resonances in the network are dangerous because they can amplify harmonic voltages far beyond expected levels, and are a common cause of unexplained equipment failures.

- **Bandwidth**
  The range of frequencies over which a circuit or system responds within a specified fraction of its peak response, typically defined as the -3 dB points. For a resonant circuit, bandwidth is inversely proportional to Q factor: BW = f_0/Q. In power electronics, the bandwidth of a control loop determines how quickly an inverter can respond to grid disturbances. In filter design, bandwidth determines which harmonic frequencies are attenuated and which pass through.

- **Cutoff frequency**
  The frequency at which a filter's output power drops to half (-3 dB) of its passband value. For a simple RC low-pass filter, f_c = 1/(2πRC). In power electronics, the cutoff frequency of the output LC filter determines how effectively switching harmonics are attenuated. In control systems, it defines the boundary between frequencies that the controller can track and those it cannot, which directly impacts inverter performance during grid transients.

- **Transfer function**
  A mathematical representation of the input-output relationship of a linear system in the frequency domain, typically expressed as a ratio of polynomials in s (Laplace variable) or jω. It encodes the gain and phase shift that the system applies to each frequency component of the input. In power systems, transfer functions describe how generators, inverter controllers, and protection systems respond to disturbances. Analysing the poles and zeros of the transfer function reveals the system's stability and transient behaviour.

- **Bode plot**
  A pair of graphs showing the magnitude (in dB) and phase (in degrees) of a transfer function as a function of frequency on a logarithmic scale. They provide an intuitive visual representation of how a system amplifies or attenuates different frequencies and how much phase shift it introduces. In power electronics, Bode plots are used to design and tune inverter control loops, ensuring adequate gain at low frequencies (for good tracking) and sufficient phase margin at the crossover frequency (for stability). They are the primary tool for loop shaping in classical control design.

- **Frequency response**
  The complete characterisation of how a system's output amplitude and phase vary with input frequency. It is the information contained in a Bode plot or, equivalently, the transfer function evaluated along the imaginary axis (s = jω). In power systems, frequency response has a dual meaning: at the component level, it describes filter and controller behaviour; at the system level, it describes how grid frequency changes in response to power imbalances. Both meanings are central to grid integration of inverter-based resources.

- **Damping ratio**
  A dimensionless parameter (ζ) that describes how oscillations in a second-order system decay over time. ζ < 1 gives underdamped oscillations, ζ = 1 is critically damped (fastest return without overshoot), and ζ > 1 is overdamped. In power systems, the damping ratio of electromechanical oscillations between generators determines how quickly the system settles after a disturbance. Low damping ratios can lead to sustained or growing oscillations, which is a key concern as synchronous generators are replaced by inverter-based resources with different damping characteristics.

- **Natural frequency**
  The frequency at which a system oscillates when disturbed, in the absence of external driving or damping. For a simple LC circuit, f_n = 1/(2π√(LC)). In power systems, the natural frequency of electromechanical modes (typically 0.2-2 Hz) determines the oscillation period after a fault or sudden load change. In power electronics, the natural frequency of the output LC filter must be well below the switching frequency to effectively attenuate harmonics, but well above the grid frequency to allow adequate control bandwidth.

- **Time constant**
  The characteristic time for an exponential process to reach approximately 63% of its final value (or decay to 37% of its initial value). For an RC circuit, τ = RC; for an RL circuit, τ = L/R. It quantifies how quickly a circuit responds to a step change. In power systems, the DC time constant of a fault circuit (L/R of the faulted path) determines how long the DC offset component of fault current persists, which affects circuit breaker duties and protection timing.

- **Transient response**
  The behaviour of a circuit or system during the period after a sudden change (switching, fault, load step) and before it settles into a new steady state. Transients involve the exchange of energy between inductors, capacitors, and resistors, and are governed by the circuit's natural frequencies and damping. In power systems, transient behaviour determines whether a system survives a fault (transient stability), how inverters ride through voltage dips, and whether protection operates correctly. Transient analysis requires time-domain simulation rather than phasor methods.

- **Steady-state response**
  The behaviour of a circuit or system after all transients have decayed, when voltages and currents are periodic (for AC systems) or constant (for DC systems). Phasor analysis, impedance, and power factor are all steady-state concepts. Most power system planning and operation deals with steady-state conditions: load flow, voltage regulation, and power factor correction are all steady-state analyses. The steady state is the operating point around which transient disturbances occur.

## 3. Electromagnetism

- **Electric field**
  A vector field that describes the force per unit charge experienced by a test charge at any point in space, measured in volts per metre (V/m). It is the gradient of electric potential: E = -∇V. In power engineering, electric field strength determines insulation requirements: the dielectric breakdown of air is approximately 3 MV/m, and insulation design ensures that electric fields remain below this threshold under all operating and fault conditions. High electric field concentrations at sharp edges or contaminated surfaces are a primary cause of insulation failure.

- **Magnetic field**
  A vector field produced by moving charges (currents) and magnetic materials, which exerts forces on other moving charges and magnetic materials. In power systems, magnetic fields are the medium through which energy is stored in inductors, coupled between transformer windings, and converted between electrical and mechanical forms in rotating machines. The magnetic field strength H (in A/m) and the magnetic flux density B (in tesla) are related by the permeability of the medium: B = μH. Managing magnetic fields is central to the design of every electromagnetic device in the power system.

- **Magnetic flux**
  The total magnetic field passing through a surface, Φ = ∫B·dA, measured in webers (Wb). It is the quantity that, when changing in time, induces voltage according to Faraday's law. In transformers, the alternating magnetic flux in the core links the primary and secondary windings, transferring energy between them. In generators, the rotating magnetic flux from the rotor cuts the stator windings to produce the output voltage.

- **Magnetic flux density**
  The magnetic field strength at a point, measured in tesla (T), representing the force per unit length per unit current on a conductor at that point. It is the "B" in B = μH and in the force equation F = BIL. Transformer and machine designers work directly with flux density because the core material has a saturation limit (typically 1.6-2.0 T for silicon steel) beyond which increasing the field requires disproportionately large magnetising current. Flux density also determines core losses, which are proportional to B² and to frequency.

- **Inductance (self and mutual)**
  Self-inductance (L) is the ratio of magnetic flux linked by a coil to the current producing it, measured in henries (H). It quantifies a coil's ability to store energy in its magnetic field: E = ½LI². Mutual inductance (M) describes the magnetic coupling between two coils: a changing current in one induces a voltage in the other, V₂ = M(dI₁/dt). Mutual inductance is the operating principle of transformers and is also responsible for crosstalk between parallel conductors. In power system models, both self and mutual inductance appear in the impedance matrices of transmission lines and multi-winding transformers.

- **Capacitance**
  The ability of a system to store energy in an electric field, defined as the ratio of charge stored to voltage applied, C = Q/V, measured in farads (F). Energy stored is E = ½CV². In power systems, capacitance exists between conductors and between conductors and ground, arising from the geometry of cables and overhead lines. Cable capacitance is much larger than overhead line capacitance (due to the close spacing and dielectric of the insulation) and becomes the dominant shunt element in underground networks, causing significant charging currents and voltage rise on lightly loaded feeders.

- **Faraday's law of induction**
  States that the electromotive force (EMF) induced in a loop is equal to the negative rate of change of magnetic flux through the loop: EMF = -dΦ/dt. This is the fundamental law governing all electromagnetic energy conversion: generators, transformers, and inductors all operate on this principle. The negative sign (Lenz's law) ensures that the induced EMF opposes the change that caused it, which is the physical basis for inductors resisting changes in current. Faraday's law connects the time-varying magnetic world to the electrical circuit world.

- **Lenz's law**
  A consequence of Faraday's law stating that the direction of an induced current is such that its magnetic field opposes the change in flux that produced it. This is a manifestation of energy conservation: if the induced current reinforced the change, it would create energy from nothing. In practical terms, Lenz's law explains why inductors resist changes in current, why eddy currents create drag forces, and why a short-circuited transformer winding opposes flux changes in the core. It is the reason that inductive loads cause current to lag voltage.

- **Ampere's law**
  States that the line integral of the magnetic field around a closed path equals the total current enclosed: ∮H·dl = I_enclosed (in the magnetostatic case). It relates current to the magnetic field it produces and is the basis for calculating fields in solenoids, toroids, and transformer cores. In its generalised form (with Maxwell's displacement current term), it is one of the four Maxwell's equations. In power engineering, Ampere's law is used to design magnetic circuits and to calculate the magnetising current required by transformer and machine cores.

- **Electromagnetic induction**
  The physical phenomenon by which a changing magnetic field produces an electric field (and hence a voltage), as described by Faraday's law. It is the operating principle of generators (where mechanical rotation changes the flux through stator windings), transformers (where alternating current in one winding changes the flux through another), and induction motors (where the rotating stator field induces currents in the rotor). Electromagnetic induction is the single most important physical mechanism in electrical power engineering, enabling the generation, transformation, and utilisation of AC power.

- **Eddy currents**
  Circulating currents induced within a conductor by a changing magnetic field, as predicted by Faraday's law. They flow in closed loops within the material, perpendicular to the direction of the magnetic flux. Eddy currents cause resistive heating (eddy current losses) in transformer cores, machine laminations, and any conductive material exposed to time-varying fields. To minimise these losses, transformer and machine cores are built from thin laminations with insulating coatings, which break up the eddy current paths and increase their resistance.

- **Hysteresis**
  The phenomenon where the magnetisation of a ferromagnetic material lags behind the applied magnetic field, forming a B-H loop when the field is cycled. The area enclosed by the hysteresis loop represents the energy lost per cycle per unit volume of the material. In transformer and machine cores, hysteresis losses (proportional to frequency and to approximately B^1.6) are a significant component of total core losses. The shape of the hysteresis loop also determines how much magnetising current is needed and affects the harmonic content of the magnetising current waveform.

- **Core losses**
  The total power dissipated in the magnetic core of a transformer or machine, comprising hysteresis losses and eddy current losses. They are present whenever the core is energised, regardless of the load current, and are therefore sometimes called "no-load losses" or "iron losses." Core losses depend on the flux density and frequency: hysteresis losses scale roughly as f × B^1.6, and eddy current losses as f² × B². Minimising core losses is a major objective in transformer design, achieved through material selection (grain-oriented silicon steel, amorphous metals) and thin lamination.

- **Skin effect**
  The tendency of AC current to concentrate near the surface of a conductor at higher frequencies, reducing the effective cross-sectional area and increasing the effective resistance. The skin depth δ = √(2ρ/ωμ) characterises the exponential decay of current density from the surface. At 50 Hz in copper, the skin depth is approximately 9.3 mm, which is comparable to the radius of large power conductors. Skin effect is the reason that large power cables use stranded or segmented conductors, and why busbars are made as flat strips rather than round rods.

- **Proximity effect**
  The redistribution of current within a conductor caused by the magnetic field of nearby conductors carrying AC current. Current tends to crowd toward the side of the conductor nearest to or farthest from the adjacent conductor (depending on current direction), increasing the effective resistance. The proximity effect is typically more significant than the skin effect in closely spaced conductors such as transformer windings and bundled cables. It is frequency-dependent and increases with the number and closeness of neighbouring conductors, making it a critical factor in the design of high-current busbars and compact equipment.

- **Permeability**

- **Reluctance**

- **Magnetic Circuit**
  A vector field produced by moving charges (currents) and magnetic materials, which exerts forces on other moving charges and magnetic materials. In power systems, magnetic fields are the medium through which energy is stored in inductors, coupled between transformer windings, and converted between electrical and mechanical forms in rotating machines. The magnetic field strength H (in A/m) and the magnetic flux density B (in tesla) are related by the permeability of the medium: B = μH. Managing magnetic fields is central to the design of every electromagnetic device in the power system.

- **Magnetic Saturation**
  The nonlinear region of a ferromagnetic core's B-H curve where incremental permeability drops sharply, meaning further increases in magnetising current produce diminishing increases in flux density. In a transformer, saturation occurs when the core flux exceeds the design value, causing the magnetising current to spike dramatically with large harmonic content. Saturation can be caused by overvoltage, by DC offset in the current (e.g., from geomagnetically induced currents), or during transformer energisation (inrush). It is a key constraint in transformer design: the core must be large enough to avoid saturation under the worst-case operating voltage and frequency.

## Rotating Machines

## 4. Semiconductor Physics and Devices

- **Band Theory (Valence Band, Conduction Band, Band Gap)**

- **Fermi Level**

- **Doping (n-type, p-type)**

- **Carrier Concentration**

- **Drift and Diffusion**

- **Recombination (Radiative, Auger, Shockley-Read-Hall)**

- **Carrier Lifetime**

- **Mobility**

- **p-n Junction**

- **Depletion Region**

- **Built-in Potential**

- **Forward Bias / Reverse Bias**

- **Diode I-V Characteristic**
  A semiconductor device that conducts current in one direction (forward-biased) and blocks it in the other (reverse-biased). In power electronics, diodes are used in rectifier circuits to convert AC to DC, in freewheeling paths to provide current continuity for inductive loads, and in voltage clamping circuits. Power diodes are characterised by their forward voltage drop (typically 0.7-1.5V), reverse blocking voltage, current rating, and reverse recovery time. The forward voltage drop multiplied by the current represents the diode's conduction loss.

- **MOSFET (Enhancement, Depletion)**
  A metal-oxide-semiconductor field-effect transistor used in power electronics for lower-power, higher-frequency switching applications. MOSFETs have very fast switching speeds and low switching losses, but their conduction losses increase significantly with voltage rating. They dominate applications below about 1 kV and several kW, such as DC-DC converters, low-power inverters, and power supplies. Wide-bandgap MOSFETs (silicon carbide, gallium nitride) are extending the MOSFET's reach into higher power and voltage ranges, challenging the IGBT in solar inverters and EV chargers.

- **IGBT (Insulated Gate Bipolar Transistor)**
  The insulated-gate bipolar transistor: a semiconductor switch that combines the easy voltage-controlled turn-on of a MOSFET with the low conduction losses of a bipolar transistor. IGBTs can be turned both on and off by gate voltage, enabling fully controllable switching at frequencies up to tens of kHz. They are the dominant device in modern power electronics for applications from 1 kW to several hundred MW, including inverters for solar and wind, motor drives, battery chargers, and voltage-source HVDC converters. Their switching losses are higher than thyristors but the controllability enables much more sophisticated converter topologies.

- **Thyristor / SCR (Silicon Controlled Rectifier)**

- **Zener Diode**

- **Photodiode**

- **Wide Bandgap Semiconductors (SiC, GaN)**

## 5. Photovoltaic Theory

- **Photovoltaic Effect**

- **Spectral Irradiance**

- **Air Mass (AM0, AM1.5)**

- **Standard Test Conditions (STC)**

- **Shockley-Queisser Limit**

- **Short-Circuit Current (Isc)**
  The flow of electric charge through a conductor, measured in amperes (A). Conventional current flows from positive to negative potential, while electron flow is in the opposite direction. In AC systems, current alternates direction sinusoidally, and its magnitude and phase relationship to voltage determine how power is transferred. Current is the primary quantity that causes heating in conductors (via I²R losses) and is the basis for most protection system operation.

- **Open-Circuit Voltage (Voc)**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

- **Fill Factor**

- **Maximum Power Point (MPP)**

- **I-V Curve (Current-Voltage Characteristic)**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

- **P-V Curve (Power-Voltage Characteristic)**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

- **Series Resistance (Rs) and Shunt Resistance (Rsh)**
  The opposition to current flow in a conductor, measured in ohms (Ω). It arises from collisions between charge carriers and the atomic lattice of the material, converting electrical energy into heat. Resistance is a purely real quantity: it dissipates energy and does not store it. In power systems, cable resistance is a key factor in voltage drop calculations and power losses, and increases with temperature, which creates a feedback loop under heavy loading.

- **Single-Diode Model**
  A semiconductor device that conducts current in one direction (forward-biased) and blocks it in the other (reverse-biased). In power electronics, diodes are used in rectifier circuits to convert AC to DC, in freewheeling paths to provide current continuity for inductive loads, and in voltage clamping circuits. Power diodes are characterised by their forward voltage drop (typically 0.7-1.5V), reverse blocking voltage, current rating, and reverse recovery time. The forward voltage drop multiplied by the current represents the diode's conduction loss.

- **Ideality Factor**

- **Dark Current / Saturation Current**
  The flow of electric charge through a conductor, measured in amperes (A). Conventional current flows from positive to negative potential, while electron flow is in the opposite direction. In AC systems, current alternates direction sinusoidally, and its magnitude and phase relationship to voltage determine how power is transferred. Current is the primary quantity that causes heating in conductors (via I²R losses) and is the basis for most protection system operation.

- **External Quantum Efficiency (EQE)**

- **Spectral Response**

- **Temperature Coefficient (of Voc, Isc, Power)**

- **Nominal Operating Cell Temperature (NOCT)**

- **Cell Efficiency vs Module Efficiency vs System Efficiency**

- **Degradation Rate**

- **Light-Induced Degradation (LID)**

- **Potential-Induced Degradation (PID)**

- **Hotspot**

- **Bypass Diode**
  A semiconductor device that conducts current in one direction (forward-biased) and blocks it in the other (reverse-biased). In power electronics, diodes are used in rectifier circuits to convert AC to DC, in freewheeling paths to provide current continuity for inductive loads, and in voltage clamping circuits. Power diodes are characterised by their forward voltage drop (typically 0.7-1.5V), reverse blocking voltage, current rating, and reverse recovery time. The forward voltage drop multiplied by the current represents the diode's conduction loss.

- **Cell Mismatch**

- **String (Series Connection of Cells)**

- **Anti-Reflection Coating**

- **Surface Passivation**

- **PERC (Passivated Emitter and Rear Cell)**

- **TOPCon (Tunnel Oxide Passivated Contact)**

- **Heterojunction (HJT)**

- **Tandem Cell**

- **Perovskite**

- **Bifacial Module**

- **Albedo (in bifacial context)**

- **Bifaciality Factor**

- **Thin-Film PV (CdTe, CIGS, a-Si)**

## 6. PV System Design

- **Irradiance (GHI, DNI, DHI)**

- **Insolation**

- **Peak Sun Hours**
  Peak voltage is the maximum instantaneous value of a sinusoidal waveform, while RMS voltage is the effective value used for power calculations. They are related by V_peak = √2 × V_RMS, so a 230V RMS mains supply has a peak voltage of approximately 325V. This distinction matters for insulation design (which must withstand peak voltage) and for power electronics (where switching devices see peak values). Confusion between peak and RMS is a common source of errors in circuit design and measurement.

- **Solar Resource Assessment**

- **Tilt Angle and Azimuth**

- **Tracking Systems (Single-Axis, Dual-Axis)**

- **Shading Analysis**

- **String Sizing**

- **Array Configuration**

- **DC/AC Ratio (Inverter Loading Ratio)**

- **Performance Ratio**

- **Specific Yield (kWh/kWp)**

- **Capacity Factor**

- **System Losses (Soiling, Clipping, Wiring, Mismatch)**

- **Energy Yield Simulation**

- **P50 / P90 Energy Estimates**

- **Levelised Cost of Energy (LCOE)**

- **Balance of System (BOS)**

- **Mounting Systems (Ground-Mount, Rooftop, Floating)**

- **Combiner Box**

- **DC Disconnect / AC Disconnect**

- **Rapid Shutdown**

- **Arc Fault Detection**
  The current that flows through the point of a fault (short circuit), determined by the driving voltage and the impedance of the path from the sources to the fault location. It is typically 10-50 times the normal load current and comprises both AC and DC components. The AC component is driven by the system generators and is limited by the combined source impedances. Fault current magnitude determines the required breaking capacity of circuit breakers and the settings of protective relays.

- **Ground Fault Protection**

- **Module-Level Power Electronics (MLPE)**

## 7. Power Electronics

- **Rectifier (Half-Wave, Full-Wave, Bridge)**

- **Inverter (Single-Phase, Three-Phase)**

- **DC-DC Converters (Buck, Boost, Buck-Boost)**

- **Voltage Source Inverter (VSI)**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

- **Multilevel Inverter**

- **String Inverter**

- **Central Inverter**

- **Microinverter**

- **Pulse Width Modulation (PWM)**

- **Duty Cycle**

- **Switching Frequency**
  The frequency at which a power electronic switch (IGBT, MOSFET) is turned on and off, typically in the range of 1-100 kHz for power conversion applications. Higher switching frequency allows smaller and lighte

- **Gate Driver**

- **Conduction Losses and Switching Losses**

- **Total Harmonic Distortion (THD)**

- **Power Quality**
  The ratio of real power to apparent power, cos(φ) = P/|S|, ranging from 0 to 1. A power factor of 1 means all current is doing useful work; a power factor of 0.5 means the equipment must carry twice the current needed for the actual power delivered. Low power factor increases losses and requires oversized equipment. Industrial consumers are often penalised for low power factor, and power factor correction (typically via capacitor banks) is a routine part of electrical installation design.

- **Maximum Power Point Tracking (MPPT)**

  - Perturb and Observe (P&O)
  - Incremental Conductance
- **Anti-Islanding**
  A condition where a portion of the power system becomes electrically separated from the main grid but continues to be energised by local generation. Islanding can be intentional (microgrid operation, planned maintenance) or unintentional (following a fault or switching event). Unintentional islanding is dangerous because voltage and frequency in the island are no longer controlled by the main grid, the protection system may not operate correctly, and there is a risk of energising equipment that workers believe to be de-energised. Anti-islanding detection and protection is mandatory for all grid-connected distributed generation.

- **Grid-Following Inverter**

- **Grid-Forming Inverter**

- **Virtual Synchronous Machine**

## 8. Three-Phase Systems

- **Three-phase power**
  A system using three AC voltages of equal magnitude, each separated by 120° in phase, carried on three conductors. Three-phase power delivers constant instantaneous power (unlike single-phase, which pulsates at twice the supply frequency), enabling smoother operation of motors and generators. It also transmits more power for a given amount of conductor material than three separate single-phase circuits. Virtually all power generation, transmission, and industrial distribution uses three-phase systems.

- **Line voltage vs phase voltage**
  In a three-phase system, the phase voltage is measured between any one phase conductor and the neutral (or star point), while the line voltage is measured between any two phase conductors. In a star-connected system, V_line = √3 × V_phase. In the UK, the standard domestic supply is 230V phase voltage, corresponding to a 400V line voltage. The distinction is critical for correctly connecting loads and calculating power.

- **Line current vs phase current**
  Line current flows through the line conductors connecting the source to the load, while phase current flows through each individual phase of the source or load. In a star connection, line current equals phase current. In a delta connection, I_line = √3 × I_phase because each line feeds two phases. Confusion between line and phase quantities is a common source of errors in three-phase calculations, particularly when mixing star and delta-connected elements.

- **Star (wye) connection**
  A configuration where one end of each phase winding is connected to a common neutral point, forming a Y shape. The other three ends connect to the line conductors. Star connection provides access to two voltage levels (phase and line) and a neutral point for grounding, making it the standard configuration for generators and transformer secondaries serving mixed loads. The neutral carries the unbalanced component of the three phase currents; in a perfectly balanced system, the neutral current is zero.

- **Delta connection**
  A configuration where the three phase windings are connected end-to-end in a closed triangle. There is no neutral point, and only the line voltage is available. Delta connection is commonly used for transformer primaries, motor windings, and three-phase loads where a neutral is not needed. It has the useful property of trapping triplen harmonic currents (3rd, 9th, 15th, etc.) within the delta loop, preventing them from flowing into the line conductors and propagating through the network.

- **Star-delta transformation**
  A mathematical technique for converting a star (Y) connected impedance network to an equivalent delta (Δ) network, or vice versa. The transformation relationships are Z_delta = (Z_a × Z_b + Z_b × Z_c + Z_c × Z_a)/Z_opposite for star-to-delta, with the inverse for delta-to-star. This is essential for simplifying complex three-phase networks where star and delta elements are mixed. It is also used in motor starting: star-delta starters initially connect the motor in star (reducing the starting current by a factor of 3) and then switch to delta for normal running.

- **Balanced and unbalanced systems**
  A balanced three-phase system has equal voltage magnitudes and exactly 120° phase separation, with equal impedance in each phase. In practice, systems are always slightly unbalanced due to unequal loading, asymmetric line impedances, or unequal phase voltages. Unbalance creates negative and zero sequence components, which cause additional losses, motor heating, and protective relay complications. The degree of voltage unbalance is typically limited to 1-2% by grid codes and engineering standards.

- **Positive sequence**
  One of the three symmetrical components of a three-phase system, representing balanced voltages and currents rotating in the normal (A-B-C) phase order. It is the component that does useful work in motors and generators. In a perfectly balanced system, only positive sequence exists. Positive sequence impedance is what appears in standard single-phase equivalent circuits of balanced three-phase networks and is the basis for most power system analysis.

- **Negative sequence**
  The symmetrical component representing balanced voltages and currents rotating in the reverse (A-C-B) phase order. It arises from unbalanced conditions and produces a magnetic field in machines that rotates opposite to the rotor, inducing currents at approximately twice the supply frequency in the rotor. This causes significant heating and can damage generators and motors. Negative sequence current is monitored by protection systems, and generators have specific thermal limits for the negative sequence current they can withstand.

- **Zero sequence**
  The symmetrical component where all three phase voltages or currents are equal in magnitude and in phase with each other. Zero sequence currents can only flow if there is a return path (typically through the neutral conductor or ground). They are associated with ground faults and with triplen harmonics in systems with a neutral connection. Delta-connected windings block zero sequence currents because there is no path for in-phase currents to circulate into or out of a delta. Zero sequence impedance is significantly different from positive sequence impedance and must be considered separately in earth fault analysis.

- **Symmetrical components**
  A mathematical decomposition technique (devised by Fortescue) that resolves any unbalanced set of three-phase phasors into three balanced sets: positive, negative, and zero sequence. Each sequence component sees a different impedance in the network and can be analysed independently in separate single-phase equivalent circuits. The actual unbalanced voltages and currents are then recovered by superposition of the three sequence components. This method is the standard approach for analysing unbalanced faults, unbalanced loads, and the effect of system asymmetry.

- **Neutral current**
  The current flowing through the neutral conductor in a star-connected system, equal to the phasor sum of the three phase currents. In a balanced system, the neutral current is zero. Under unbalanced conditions, neutral current can be significant, particularly in networks with many single-phase loads (such as residential distribution). Triplen harmonics also sum in the neutral, meaning that in systems with significant nonlinear loads (computers, LED drivers, etc.), the neutral current can actually exceed the phase current, which has implications for conductor sizing and protection.

- **Phase imbalance**
  A condition where the three phases of a power system carry unequal currents or have unequal voltages. It creates negative sequence components, which increase losses (proportional to the square of the imbalance current), cause overheating in motors (due to double-frequency rotor currents), and reduce the useful capacity of transformers and cables. In the UK distribution network, phase imbalance is exacerbated by single-phase domestic solar installations, which may concentrate generation on one phase. DNOs monitor and manage phase imbalance as part of network planning.

- **Per-unit system**
  A method of normalising electrical quantities by dividing them by chosen base values (typically base power in MVA and base voltage in kV), producing dimensionless ratios. Once normalised, the per-unit impedance of a transformer is the same whether viewed from the high-voltage or low-voltage side, eliminating the need to refer impedances across voltage levels. This simplifies calculation enormously in systems with multiple voltage levels and many transformers. Nearly all power system analysis software and published data uses the per-unit system, with typical base values of 100 MVA for system studies.

- **Base Values**

## 9. Transformers

- **Transformer ratio**
  The ratio of primary voltage to secondary voltage in a transformer, determined by the ratio of turns in the primary and secondary windings. For an ideal transformer, V₁/V₂ = N₁/N₂, and the power is conserved: V₁I₁ = V₂I₂. The transformer ratio allows voltage to be stepped up for efficient long-distance transmission and stepped down for safe distribution and end use. Real transformers deviate slightly from the ideal ratio due to winding resistance, leakage reactance, and core losses.

- **Turns ratio**
  The ratio of the number of turns in the primary winding to the number of turns in the secondary winding, N₁/N₂. In an ideal transformer, it exactly equals the voltage ratio. The turns ratio is a physical design parameter that determines the nominal voltage transformation, and it is fixed for a given winding configuration. Fine adjustment of the effective ratio is achieved through tap changers, which switch in or out small numbers of turns to regulate the output voltage.

- **Equivalent Circuit of a Transformer**
  A circuit model that represents a real transformer's behaviour using ideal circuit elements. The standard model consists of an ideal transformer in the centre, with series impedances (R + jX) on each side representing winding resistance and leakage reactance, and a shunt branch across the primary representing core losses (as a resistance) and magnetising current (as a reactance). The secondary impedance can be "referred" to the primary side by multiplying by the square of the turns ratio, allowing the entire circuit to be reduced to a single loop. This equivalent circuit is the basis for calculating voltage regulation, efficiency, and fault current contribution.

- **Magnetising Current**
  The current drawn by a transformer's primary winding to establish the magnetic flux in the core, even when the secondary is open-circuited (no load). It is typically 1-5% of the rated full-load current and is highly nonlinear due to core saturation, containing significant odd harmonic components (especially the 3rd). Magnetising current represents the no-load losses and the reactive power needed to maintain the core flux. During transformer energisation (inrush), magnetising current can transiently reach 5-10 times the rated current due to core saturation and residual flux.

- **Leakage reactance**
  The reactance associated with magnetic flux that links one winding of a transformer but not the other, because it passes through air rather than the core. It is modelled as a series reactance in the transformer equivalent circuit and causes a voltage drop under load that is proportional to the load current and roughly 90° out of phase with it. Leakage reactance is a key design parameter: it limits fault current (higher leakage reactance means lower fault current contribution) but also causes greater voltage regulation under load. Typical values are 4-10% on the transformer's MVA base.

- **Copper losses**
  The I²R power dissipated as heat in the resistance of the transformer windings, proportional to the square of the load current. They are also called "load losses" because they vary with load. Copper losses increase with temperature (since conductor resistance increases), creating a positive feedback that can lead to thermal runaway if cooling is inadequate. In a well-designed transformer, copper losses at rated load are comparable in magnitude to core losses, as this minimises the total losses over a range of loading conditions.

- **Iron losses**
  The power dissipated in the magnetic core of a transformer, comprising hysteresis losses and eddy current losses. They are present whenever the transformer is energised, regardless of loading, and are also called "core losses" or "no-load losses." Iron losses depend on the core material, lamination thickness, operating flux density, and frequency. They represent a constant power drain and are a significant economic consideration in distribution transformers, which may be energised 24/7 at light load for much of their life.

- **Tap changer (on-load and off-load)**
  A mechanism that varies the transformer turns ratio by switching between different tapping points on a winding, thereby adjusting the output voltage. Off-load tap changers can only be operated when the transformer is de-energised and are used for seasonal or commissioning adjustments. On-load tap changers can change taps while the transformer is carrying load, using a make-before-break mechanism with transition resistors or reactors to avoid interrupting the current. On-load tap changers are essential for voltage regulation on distribution networks and are the primary means by which DNOs maintain voltage within statutory limits.

- **Auto-transformer**
  A transformer with a single winding that serves as both primary and secondary, with the secondary voltage tapped from a portion of the winding. Because part of the power is transferred conductively (not magnetically), an auto-transformer is smaller, lighter, and more efficient than a two-winding transformer of the same rating, provided the ratio is close to 1:1. Auto-transformers are commonly used for voltage regulation (such as variacs), for interconnecting transmission systems at similar voltage levels, and in motor starting circuits. Their disadvantage is that there is no galvanic isolation between primary and secondary.

- **Distribution transformer**
  A transformer that steps down voltage from the medium-voltage distribution network (typically 11 kV in the UK) to low voltage (400/230V) for delivery to end consumers. Distribution transformers are the most numerous transformers in the power system (there are hundreds of thousands in the UK) and are designed for high efficiency at low load, since they are often lightly loaded. They are typically rated from 25 kVA to 1 MVA, use oil or dry-type insulation, and operate with natural cooling. Their impedance (typically 4-5%) determines the fault level on the LV network.

- **Step-up and step-down**
  A step-up transformer increases voltage from primary to secondary (fewer primary turns than secondary turns), while a step-down transformer decreases it. Step-up transformers are used at power stations to raise the generator output voltage (typically 11-25 kV) to transmission voltage (132-400 kV) for efficient long-distance transfer. Step-down transformers are used at substations to progressively reduce voltage to distribution and utilisation levels. The choice of voltage level at each stage is an economic optimisation between insulation costs (which increase with voltage) and conductor losses (which decrease with voltage for a given power transfer).

- **Transformer equivalent circuit**
  A circuit model that represents a real transformer's behaviour using ideal circuit elements. The standard model consists of an ideal transformer in the centre, with series impedances (R + jX) on each side representing winding resistance and leakage reactance, and a shunt branch across the primary representing core losses (as a resistance) and magnetising current (as a reactance). The secondary impedance can be "referred" to the primary side by multiplying by the square of the turns ratio, allowing the entire circuit to be reduced to a single loop. This equivalent circuit is the basis for calculating voltage regulation, efficiency, and fault current contribution.

- **Nameplate rating**
  The maximum continuous power a transformer is designed to handle under specified conditions (ambient temperature, cooling method, altitude), expressed in kVA or MVA. It defines the thermal limit: the combination of copper and iron losses that the cooling system can dissipate without exceeding the rated winding hot-spot temperature. Operating above nameplate rating accelerates insulation ageing (the ageing rate roughly doubles for every 6-8°C above the rated temperature). Transformers can be temporarily overloaded above their nameplate rating provided the cumulative thermal ageing is managed.

- **Transformer impedance (percentage impedance)**
  The voltage (expressed as a percentage of rated voltage) required to circulate rated current through the transformer with the secondary short-circuited. A 5% impedance transformer needs 5% of rated voltage to drive rated current through its own leakage impedance. This value directly determines the fault current the transformer will deliver: I_fault = I_rated / (Z%), so a 5% transformer delivers 20 times rated current into a close-up fault. It also determines voltage regulation: a higher impedance transformer has more voltage drop under load but contributes less to downstream fault levels.

- **Saturation**
  The nonlinear region of a ferromagnetic core's B-H curve where incremental permeability drops sharply, meaning further increases in magnetising current produce diminishing increases in flux density. In a transformer, saturation occurs when the core flux exceeds the design value, causing the magnetising current to spike dramatically with large harmonic content. Saturation can be caused by overvoltage, by DC offset in the current (e.g., from geomagnetically induced currents), or during transformer energisation (inrush). It is a key constraint in transformer design: the core must be large enough to avoid saturation under the worst-case operating voltage and frequency.

- **Instrument Transformer (CT, VT/PT)**

## 10. Rotating Machines

- **Synchronous generator**
  A machine that converts mechanical energy into electrical energy by rotating a magnetic field (on the rotor) within a set of stationary windings (the stator), producing AC voltage at a frequency locked to the rotor speed. The output frequency is f = (N × p)/120, where N is speed in RPM and p is the number of poles. Synchronous generators are the backbone of conventional power systems: virtually all thermal, hydro, and nuclear plants use them. Their rotating mass provides physical inertia that stabilises grid frequency, and their excitation system can independently control reactive power output.

- **Synchronous speed**
  The speed at which a rotating magnetic field revolves in a machine, determined by the supply frequency and the number of poles: N_s = 120f/p RPM. For a 50 Hz system, a 2-pole machine has a synchronous speed of 3000 RPM and a 4-pole machine 1500 RPM. A synchronous generator must be driven at exactly synchronous speed to produce power at the system frequency. Deviation from synchronous speed causes the rotor angle to change, which changes the power output according to the power-angle relationship.

- **Rotor**
  The rotating part of an electric machine, which may carry either the field winding (in synchronous machines) or the secondary winding (in induction machines). In a synchronous generator, the rotor produces the rotating magnetic field via DC excitation or permanent magnets. In an induction motor, the rotor carries short-circuited bars (squirrel cage) or wound windings in which current is induced by the rotating stator field. The rotor's moment of inertia is the physical quantity that provides system inertia for frequency stability.

- **Stator**
  The stationary part of an electric machine, typically containing the armature windings in which the output voltage is induced (in generators) or which create the rotating magnetic field (in motors). The stator consists of a laminated iron core with slots containing copper or aluminium windings, arranged to produce a three-phase winding pattern. In large generators, the stator windings are the high-voltage, high-current components, and their insulation system is a critical life-limiting factor. Stator design determines the voltage rating, cooling capability, and harmonic content of the machine output.

- **Excitation**
  The process of supplying DC current to the field winding of a synchronous generator to create the rotor's magnetic field. The excitation current directly controls the strength of the magnetic field and therefore the magnitude of the induced voltage. By adjusting excitation, the operator controls the generator's reactive power output (and terminal voltage) independently of its real power output. Modern excitation systems use rotating or static rectifiers controlled by automatic voltage regulators (AVRs), which respond within milliseconds to maintain voltage and stability.

- **Armature**
  The winding in which the output voltage is generated (in a generator) or in which the input current flows to produce torque (in a motor). In most AC machines, the armature is on the stator, while the field is on the rotor, because it is easier to insulate and cool a stationary high-voltage winding. The armature winding carries the full load current and produces its own magnetic field (the armature reaction), which interacts with the main field and affects voltage regulation and stability. Armature resistance and leakage reactance contribute to the machine's internal impedance.

- **Back-EMF**
  The voltage induced in the armature of a motor by its own rotation through the magnetic field. Back-EMF opposes the applied voltage and is proportional to the speed of rotation. The net current drawn by the motor is determined by the difference between the applied voltage and the back-EMF divided by the armature impedance: I = (V - E_back)/Z. At no load, the motor speeds up until the back-EMF nearly equals the supply voltage and the current drops to just enough to overcome friction losses. Back-EMF is the mechanism by which a motor self-regulates its speed.

- **Power Angle (Load Angle)**
  The angular difference between the internal EMF phasor of a synchronous machine and the terminal voltage phasor, also called the load angle or torque angle. It determines the real power output of the generator: P = (EV/X)sin(δ), where E is the internal EMF, V is the terminal voltage, and X is the synchronous reactance. The power angle increases with load, reaching a maximum at 90° (for a cylindrical rotor machine). The power angle is the key state variable in transient stability analysis and represents the energy balance between mechanical input and electrical output.

- **Synchronous Reactance**
  The steady-state reactance of a synchronous generator after all transient effects have decayed, denoted X_d. It is the largest of the three reactances, typically 1.0-2.5 pu, and determines the generator's steady-state behaviour: its voltage regulation, reactive power capability, and the power-angle curve. Synchronous reactance is used in load flow analysis, steady-state stability assessment, and for calculating the sustained fault current contribution (which is much smaller than the initial fault current). It represents the ratio of induced EMF to armature current under balanced, steady-state conditions.

- **Slip**
  The fractional difference between the synchronous speed and the actual rotor speed of an induction motor: s = (N_s - N_r)/N_s. Slip is necessary for an induction motor to produce torque: if the rotor ran at synchronous speed, there would be no relative motion between the rotor and the stator field, no induced rotor current, and therefore no torque. Typical full-load slip is 2-5% for standard induction motors. Slip also determines the frequency of the rotor currents (f_rotor = s × f_supply), which affects rotor losses and heating.

- **Induction Motor / Generator**
  A machine in which the rotor current is produced by electromagnetic induction from the rotating stator field, rather than by external excitation. The rotor does not need electrical connections (in the squirrel cage type), making induction motors extremely robust, cheap, and low-maintenance. They are by far the most common type of motor in industrial and domestic applications, consuming approximately 40-50% of all electricity generated globally. Induction motors always run slightly below synchronous speed (they require slip to function) and their power factor is inherently lagging because they draw magnetising current from the supply.

- **Torque-Speed Characteristic**
  The curve showing how a motor's torque varies with speed, which is fundamental to matching the motor to its mechanical load. For an induction motor, torque is low at synchronous speed (zero slip), increases roughly proportionally with slip at low slip values, reaches a peak (pull-out torque), and then decreases at higher slip. The operating point is where the motor's torque-speed curve intersects the load's torque-speed curve. This characteristic determines starting behaviour, running efficiency, and stability of the mechanical drive system.

- **Doubly-Fed Induction Generator (DFIG)**

- **Permanent Magnet Synchronous Generator (PMSG)**

- **Mechanical Inertia**
  The property of a rotating mass that resists changes in rotational speed, quantified by the moment of inertia J (in kg·m²). The kinetic energy stored in a rotating machine is E = ½Jω², which acts as a short-term energy buffer: any imbalance between electrical power output and mechanical power input is initially absorbed by changes in rotational kinetic energy. This stored energy is what provides the grid with inertia, slowing down frequency deviations after disturbances. Large thermal and hydro generators typically have moments of inertia in the range of thousands to tens of thousands of kg·m².

- **Inertia Constant (H)**
  A normalised measure of the stored kinetic energy of a rotating machine, defined as H = ½Jω²/S_rated, expressed in seconds. It represents the time for which the machine could supply its rated power solely from its stored kinetic energy. Typical values are 2-4 seconds for gas turbines, 3-6 seconds for steam turbines, and 2-4 seconds for hydro units. The system-wide inertia constant (the MVA-weighted average of all connected generators) determines how quickly frequency changes after a power imbalance: lower H means faster frequency deviation.

- **Swing Equation**
  The fundamental equation of motion for a synchronous machine rotor: 2H(d²δ/dt²) = P_m - P_e, where δ is the rotor angle, P_m is mechanical power input, and P_e is electrical power output (all in per-unit). It describes how the rotor accelerates or decelerates in response to any imbalance between mechanical and electrical power. The swing equation is the basis for all transient stability analysis: solving it (usually numerically) after a fault determines whether the generator will regain synchronism or "swing out." The frequency dynamics of the entire power system emerge from the coupled swing equations of all connected generators.

## 11. Power System Analysis

- **Load Flow (Power Flow) Analysis**
  The calculation of steady-state voltages, currents, and power flows throughout a power network for a given set of generator outputs and load demands. It solves the nonlinear algebraic equations derived from KCL applied at every bus, using the admittance matrix of the network. Load flow is the most fundamental power system analysis: it determines whether voltages are within limits, whether lines and transformers are within their thermal ratings, and what the system losses are. Every other analysis (contingency, stability, protection coordination) begins with a converged load flow solution.

- **Bus, Busbar, Node**
  A node in a power system network model where one or more generators, loads, or transmission elements connect. In physical terms, a bus corresponds to a busbar in a substation. In the mathematical model, each bus has four associated quantities: real power (P), reactive power (Q), voltage magnitude (|V|), and voltage angle (δ). Two of these four are specified and the other two are calculated by the load flow solution, depending on the bus type.

- **Slack Bus (Swing Bus)**
  A reference bus in the load flow formulation where both voltage magnitude and angle are fixed (typically |V| = 1.0 pu, δ = 0°). The slack bus absorbs or supplies whatever real and reactive power is needed to balance the system, including network losses. It is necessary because the total system losses are not known until the load flow is solved, so one bus must be free to supply the difference. In practice, the slack bus usually represents the largest generator or the point of connection to the main grid.

- **PQ Bus**
  A bus in the load flow formulation where real power P and reactive power Q are specified, and the voltage magnitude and angle are calculated. Load buses are typically modelled as PQ buses because the consumer demand is known (or estimated) and the local voltage adjusts in response. Most buses in a power system model are PQ buses. The challenge is that the voltage at a PQ bus can fall outside acceptable limits if the demand is too high or the network is too weak, which the load flow solution will reveal.

- **PV Bus**
  A bus where real power P and voltage magnitude |V| are specified, and reactive power Q and voltage angle δ are calculated. Generator buses are typically modelled as PV buses because generators have automatic voltage regulators that hold terminal voltage constant by adjusting reactive power output. The PV bus model assumes the generator has unlimited reactive power capability, which is not true in practice: if the calculated Q exceeds the generator's reactive power limit, the bus is converted to a PQ bus with Q set at the limit, and the voltage is allowed to vary.

- **Newton-Raphson Method**
  An iterative numerical method for solving the nonlinear load flow equations, based on linearising the equations at each iteration using the Jacobian matrix. It typically converges in 3-5 iterations regardless of system size, making it the standard method for large-scale power system analysis. The Jacobian matrix relates small changes in power injections to small changes in voltages and angles, and is recomputed at each iteration. Newton-Raphson's quadratic convergence rate (errors decrease as the square of the previous error) makes it far superior to simpler methods like Gauss-Seidel for practical power system problems.

- **Gauss-Seidel Method**
  An older iterative method for load flow that solves for the voltage at each bus sequentially using the latest available values. It is simple to implement and has low memory requirements, but converges slowly (linearly) and may fail to converge for ill-conditioned systems. It requires many more iterations than Newton-Raphson (often 50-100+), and convergence degrades for large networks. It is now mainly used for small networks, for providing initial estimates to the Newton-Raphson method, or in educational contexts.

- **Admittance Matrix (Y-bus)**
  A square matrix of complex admittances that describes the electrical relationship between all buses in a power network. The diagonal element Y_ii is the sum of all admittances connected to bus i, and the off-diagonal element Y_ij is the negative of the admittance of the branch connecting buses i and j. The Y-bus is naturally sparse (most off-diagonal elements are zero because most buses are not directly connected) and is efficient to build and store. It is the fundamental network representation used in load flow, fault analysis, and stability studies.

- **Impedance Matrix (Z-bus)**
  The inverse of the admittance matrix, where element Z_ij represents the voltage at bus i caused by a unit current injection at bus j with all other injections zero. Unlike the Y-bus, the Z-bus is generally a full (dense) matrix, which makes it expensive to compute and store for large systems. However, the Z-bus is extremely useful for fault analysis because the fault current at any bus is simply the pre-fault voltage divided by the relevant diagonal element of the Z-bus. It can be built incrementally (bus by bus) without inverting the Y-bus.

- **One-Line Diagram (Single-Line Diagram)**

- **Optimal Power Flow (OPF)**
  An extension of the load flow that finds the generator dispatch and control settings (tap positions, reactive power sources) that minimise a specified objective function (usually total generation cost or total losses) while satisfying all network constraints (voltage limits, line ratings, generator limits). It is a nonlinear, non-convex optimisation problem, typically solved using interior point methods or sequential linear programming. Optimal power flow is the mathematical foundation for economic operation of power systems and electricity market clearing.

- **Economic Dispatch**
  The problem of allocating total demand among available generators to minimise total fuel cost while satisfying the system power balance constraint. The optimal solution requires that all dispatched generators operate at equal incremental cost (marginal cost of the most expensive MW from each must be the same). Economic dispatch is solved in real time by system operators and forms the basis of electricity wholesale market pricing. Network constraints add complexity: congestion can cause different prices at different locations.

- **Unit Commitment**
  The problem of deciding which generators to turn on (commit) over a planning horizon (typically 24-168 hours ahead) to meet the forecasted demand at minimum total cost, including start-up costs, no-load costs, and fuel costs. It must respect minimum up-time and down-time constraints, ramp rate limits, and reserve requirements. Unit commitment is a large-scale mixed-integer optimisation problem that is computationally challenging. It is solved daily by system operators and is the primary scheduling decision in power system operation.

- **Merit Order**
  The ranking of available generators from lowest to highest marginal cost of production. Generators are dispatched in merit order: the cheapest sources (nuclear, renewables with zero marginal cost) run first, followed by progressively more expensive sources (gas CCGT, gas peaking, oil), until demand is met. The marginal cost of the last unit dispatched sets the system marginal price. The merit order effect of renewables (which push more expensive generators off the margin) is one of the primary mechanisms by which renewable energy reduces wholesale electricity prices.

- **Marginal Cost**
  The cost of producing one additional unit (MWh) of electricity from a given generator, primarily determined by fuel cost and efficiency (heat rate). For a thermal plant, marginal cost = fuel price / (efficiency × energy content). Renewables have near-zero marginal cost because their "fuel" (sun, wind) is free. Marginal cost is the basis for economic dispatch and for setting wholesale electricity prices. It does not include capital costs, so generators with high capital costs but low marginal costs (nuclear, renewables) are dispatched first but need other revenue mechanisms to recover their investment.

- **Locational Marginal Pricing (LMP)**
  A pricing mechanism (used in many US markets and being considered elsewhere) where the electricity price at each bus in the network reflects the marginal cost of delivering an additional MW to that location, including the cost of generation, losses, and congestion. Prices differ across the network when transmission constraints bind: a congested line creates a price difference between the sending and receiving ends. Locational marginal pricing provides efficient economic signals for generation siting, demand response, and transmission investment. It is a direct output of the optimal power flow.

- **Contingency Analysis**
  The systematic evaluation of what happens to the power system when individual components (lines, transformers, generators) fail. Each failure scenario is a "contingency," and the system must be checked for voltage violations, thermal overloads, and stability problems under each one. Contingency analysis is the practical application of the N-1 criterion and is run continuously by system operators. It typically requires solving hundreds or thousands of modified load flows, which must be done quickly enough to keep pace with changing system conditions.

- **N-1 Criterion**
  A security standard requiring that the power system must be able to withstand the loss of any single component (generator, line, or transformer) without violating any operational limits. This means the system must be operated with sufficient margin that no single failure causes cascade overloads, voltage collapse, or loss of supply. The N-1 criterion is the fundamental planning and operating standard for transmission systems worldwide. More stringent criteria (N-2, N-1-1) are sometimes applied for critical infrastructure or extreme events.

- **State Estimation**
  The process of determining the most likely state (voltage magnitudes and angles at all buses) of the power system from a set of redundant, imperfect measurements (power flows, injections, voltage magnitudes from SCADA). It uses statistical techniques (typically weighted least squares) to find the state that best fits all measurements simultaneously, and can detect and identify bad measurements. State estimation runs every few minutes in control centres and provides the real-time network model on which all other operational analyses (contingency analysis, economic dispatch, etc.) are based.

## Power System Stability

## 12. Power System Stability and Control

- **Frequency Stability**
  The ability of the power system to maintain frequency within acceptable limits following a severe disturbance that causes a significant imbalance between generation and demand. Frequency stability depends on having sufficient generation reserves and adequate system inertia to limit the rate and depth of frequency excursions. It is the most fundamental stability concern: if frequency drops too low, generators trip on under-frequency protection, leading to cascading failures and potentially system-wide blackout. The increasing penetration of inverter-based resources (with no inherent inertia) is making frequency stability a growing challenge worldwide.

- **Voltage Stability**
  The ability of the power system to maintain acceptable voltages at all buses following a disturbance or a gradual increase in load. Voltage instability typically occurs when the system cannot supply sufficient reactive power to maintain voltages, often triggered by loss of a major reactive power source or by load increases on long, heavily loaded feeders. The mechanism involves a positive feedback loop: falling voltage increases current (for constant power loads), which increases reactive power losses, which further reduces voltage. Voltage collapse has caused several major blackouts worldwide.

- **Rotor Angle Stability**
  The ability of synchronous machines in the power system to maintain synchronism after a disturbance. Synchronism requires that all generators maintain a stable equilibrium of their rotor angles, which represent the balance between mechanical input and electrical output at each machine. Loss of rotor angle stability means one or more generators "swing out" and lose synchronism, requiring them to be disconnected. It is divided into transient stability (response to large disturbances like faults) and small-signal stability (response to small perturbations).

- **Transient Stability**
  The ability of the power system to maintain synchronism when subjected to a large disturbance, such as a three-phase fault followed by line disconnection. It depends on the severity and duration of the fault, the pre-fault operating condition (power angle), and the post-fault network configuration. Transient stability is assessed by solving the swing equations of all generators in the time domain for the first few seconds after a disturbance. The critical clearing time (the maximum fault duration for which the system remains stable) is a key metric. Faster fault clearance by protection systems directly improves transient stability.

- **Small-Signal Stability**
  The ability of the power system to return to equilibrium after a small perturbation, without sustained or growing oscillations. It is analysed by linearising the system equations around the operating point and examining the eigenvalues of the resulting state matrix. Each eigenvalue corresponds to a mode of oscillation: if all eigenvalues have negative real parts, the system is stable. Small-signal instability manifests as poorly damped electromechanical oscillations (typically 0.2-2 Hz), where groups of generators swing against each other. Power system stabilisers (PSSs) on generator excitation systems are the primary means of improving small-signal stability.

- **Rate of Change of Frequency (RoCoF)**
  The time derivative of system frequency, df/dt, measured in Hz/s. It is directly proportional to the power imbalance and inversely proportional to the system inertia: df/dt = Δf₀ΔP/(2HS). RoCoF is the earliest indicator of a generation-demand imbalance and is used by protection relays to detect islanding conditions and by fast-acting frequency response services to initiate corrective action. As system inertia decreases (due to displacement of synchronous generators by inverter-based resources), RoCoF following disturbances increases, tightening the time available for corrective action.

- **Frequency Nadir**
  The lowest point that system frequency reaches following a sudden loss of generation, before primary frequency response arrests the decline. The depth of the nadir depends on the size of the generation loss, the system inertia (which determines how fast frequency falls), and the speed and magnitude of primary frequency response. In the GB system, the nadir must be kept above 49.2 Hz to avoid triggering low-frequency demand disconnection. Predicting and managing the frequency nadir is one of the most critical real-time operational challenges for system operators.

- **Primary Frequency Response**
  The automatic, proportional increase in generator output (or decrease in load) in response to a fall in system frequency, governed by the droop characteristic of each participating generator or resource. It begins within seconds of a frequency deviation and acts to arrest the frequency decline and stabilise it at a new (lower) steady-state value. The amount of primary response is determined by the droop setting and the headroom available on each responding unit. Primary response does not restore frequency to nominal: that requires secondary response.

- **Secondary Frequency Response (AGC / Load Frequency Control)**
  The complete characterisation of how a system's output amplitude and phase vary with input frequency. It is the information contained in a Bode plot or, equivalently, the transfer function evaluated along the imaginary axis (s = jω). In power systems, frequency response has a dual meaning: at the component level, it describes filter and controller behaviour; at the system level, it describes how grid frequency changes in response to power imbalances. Both meanings are central to grid integration of inverter-based resources.

- **Tertiary Frequency Response**
  The manual or semi-automatic re-dispatch of generation and load to replace the secondary response reserves and ensure the system is prepared for any subsequent disturbance. It operates over minutes to hours and may involve starting or stopping generators, adjusting interchange schedules, or activating demand-side response. Tertiary response restores the system to a fully secure state with all reserves replenished. In market-based systems, tertiary response is often procured through the balancing mechanism or reserve markets.

- **Governor / Droop Control**
  A decentralised control strategy where each generator (or inverter) adjusts its power output in proportion to the local frequency deviation: ΔP = -ΔF/R, where R is the droop coefficient. Droop control enables stable load sharing between multiple generators without communication, because each unit responds independently to the same frequency signal. It is the default control mode for synchronous generators and is increasingly implemented in battery inverters and other distributed resources. The trade-off is that droop control results in a steady-state frequency error proportional to the total load change, which must be corrected by secondary control.

- **Droop Characteristic**
  A decentralised control strategy where each generator (or inverter) adjusts its power output in proportion to the local frequency deviation: ΔP = -ΔF/R, where R is the droop coefficient. Droop control enables stable load sharing between multiple generators without communication, because each unit responds independently to the same frequency signal. It is the default control mode for synchronous generators and is increasingly implemented in battery inverters and other distributed resources. The trade-off is that droop control results in a steady-state frequency error proportional to the total load change, which must be corrected by secondary control.

- **System Inertia**
  The total stored kinetic energy of all synchronous machines (generators and motors) connected to the power system, which provides a natural resistance to frequency changes. System inertia is quantified as the sum of the inertia constants H multiplied by the rated power of each machine. Higher inertia means that a given power imbalance causes a slower frequency deviation, providing more time for primary response to act. System inertia in the GB system has been declining as synchronous generation is replaced by wind and solar (which have no inherent inertia), creating new operational challenges.

- **Synthetic Inertia**
  An emulated inertial response provided by inverter-based resources that detect frequency changes (via RoCoF measurement) and inject or absorb power proportionally, mimicking the behaviour of a synchronous machine's stored kinetic energy. The energy for synthetic inertia must come from somewhere: typically the DC link capacitor, a battery, the kinetic energy of a wind turbine rotor, or curtailed generation capacity. Synthetic inertia can be faster than natural inertia (since the inverter can respond in milliseconds once a frequency change is detected) but introduces a measurement and processing delay that natural inertia does not have. It is being mandated in some grid codes for new wind and solar installations.

- **Fast Frequency Response**
  A service that provides rapid power injection (typically within 0.5-2 seconds) in response to a frequency deviation, faster than conventional primary response from thermal generators. It is typically provided by batteries, demand-side response, or inverter-based generation with headroom. Fast frequency response is particularly valuable in low-inertia systems where frequency falls rapidly after a disturbance. National Grid ESO procures fast frequency response through competitive markets as part of its strategy to operate the GB system with increasing levels of inverter-based generation.

- **Load Shedding (Under-Frequency)**
  The automatic disconnection of selected blocks of consumer demand when system frequency falls below predetermined thresholds, as a last-resort measure to arrest frequency decline and prevent total system collapse. In the UK, the Low Frequency Demand Disconnection (LFDD) scheme disconnects load in stages starting at 48.8 Hz. Load shedding is designed to balance the system by reducing demand to match the available generation. It is an emergency measure that indicates the system's normal control mechanisms (primary, secondary, tertiary response) have been insufficient, and it results in supply interruptions to affected consumers.

- **Islanding (Intentional and Unintentional)**
  A condition where a portion of the power system becomes electrically separated from the main grid but continues to be energised by local generation. Islanding can be intentional (microgrid operation, planned maintenance) or unintentional (following a fault or switching event). Unintentional islanding is dangerous because voltage and frequency in the island are no longer controlled by the main grid, the protection system may not operate correctly, and there is a risk of energising equipment that workers believe to be de-energised. Anti-islanding detection and protection is mandatory for all grid-connected distributed generation.

- **Black Start**
  The process of restoring a power system from a total or partial blackout, starting with generators that can self-start without an external power supply. Black start capability typically comes from hydro plants, gas turbines with battery or diesel starting systems, or dedicated black start diesel generators. The process involves energising sections of the network incrementally, synchronising additional generators, and progressively reconnecting load. Black start is one of the most complex and critical procedures in power system operation, and system operators maintain detailed black start plans that are regularly rehearsed.

- **Cascading Failure**
  A sequence of dependent failures in which the loss of one component causes overloads or voltage problems that trip additional components, leading to a widening chain of failures. The mechanism typically involves a line or generator tripping, redistributing power flows onto the remaining network, causing one or more additional elements to exceed their limits and trip, further concentrating flows and accelerating the cascade. Cascading failures are the cause of large-scale blackouts. They are extremely difficult to predict because they involve the interaction of power flow physics, protection system behaviour, and operator response.

## Fault Analysis

- **Automatic Voltage Regulator (AVR)**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

- **Power System Stabiliser (PSS)**

- **Equal Area Criterion**

- **Critical Clearing Time**

- **Microgrid**

## 13. Fault Analysis

- **Short Circuit**
  An abnormal low-impedance connection between two points in a circuit that are normally at different voltages, causing very large currents to flow. Short circuits can occur due to insulation failure, physical damage, contamination, or lightning strikes. The resulting fault current can be tens or hundreds of times the normal load current, causing severe mechanical stresses, heating, and potential equipment damage within milliseconds. Rapid detection and clearance of short circuits by the protection system is essential for equipment safety, personnel safety, and system stability.

- **Fault Current**
  The current that flows through the point of a fault (short circuit), determined by the driving voltage and the impedance of the path from the sources to the fault location. It is typically 10-50 times the normal load current and comprises both AC and DC components. The AC component is driven by the system generators and is limited by the combined source impedances. Fault current magnitude determines the required breaking capacity of circuit breakers and the settings of protective relays.

- **Symmetrical Fault (Three-Phase)**
  A balanced three-phase fault where all three phases are short-circuited simultaneously, typically through a negligible impedance. It is the simplest type to analyse because the system remains balanced and can be solved using a single-phase equivalent circuit with positive-sequence impedances only. Although the least common fault type in practice (approximately 5% of faults), the symmetrical fault produces the highest fault current magnitude and is therefore the basis for equipment ratings. It is the standard fault type used for circuit breaker specification.

- **Asymmetrical Faults (SLG, LL, DLG)**
  A balanced three-phase fault where all three phases are short-circuited simultaneously, typically through a negligible impedance. It is the simplest type to analyse because the system remains balanced and can be solved using a single-phase equivalent circuit with positive-sequence impedances only. Although the least common fault type in practice (approximately 5% of faults), the symmetrical fault produces the highest fault current magnitude and is therefore the basis for equipment ratings. It is the standard fault type used for circuit breaker specification.

- **Fault Level (MVA / Short Circuit Level)**
  An abnormal low-impedance connection between two points in a circuit that are normally at different voltages, causing very large currents to flow. Short circuits can occur due to insulation failure, physical damage, contamination, or lightning strikes. The resulting fault current can be tens or hundreds of times the normal load current, causing severe mechanical stresses, heating, and potential equipment damage within milliseconds. Rapid detection and clearance of short circuits by the protection system is essential for equipment safety, personnel safety, and system stability.

- **X/R Ratio**

- **Sub-Transient Reactance**
  The effective reactance of a synchronous generator during the first few cycles (approximately 10-30 ms) after a fault, denoted X"d. It is the lowest of the three generator reactances and produces the highest initial fault current. Sub-transient reactance represents the effect of currents induced in the rotor damper windings and the rotor body, which initially oppose the change in flux. Typical values are 0.1-0.25 pu. It is the reactance used for calculating the maximum (first-cycle) fault current for circuit breaker making capacity specification.

- **Transient Reactance**
  The effective reactance of a synchronous generator during the period from a few cycles to several seconds after a fault, denoted X'd. It is larger than the sub-transient reactance because the damper winding currents have decayed, but smaller than the synchronous reactance because the field winding current has not yet fully adjusted. Typical values are 0.2-0.4 pu. Transient reactance is used for calculating the interrupting current (at the time the circuit breaker opens, typically 3-5 cycles after the fault) and for transient stability analysis.

- **Synchronous Reactance**
  The steady-state reactance of a synchronous generator after all transient effects have decayed, denoted X_d. It is the largest of the three reactances, typically 1.0-2.5 pu, and determines the generator's steady-state behaviour: its voltage regulation, reactive power capability, and the power-angle curve. Synchronous reactance is used in load flow analysis, steady-state stability assessment, and for calculating the sustained fault current contribution (which is much smaller than the initial fault current). It represents the ratio of induced EMF to armature current under balanced, steady-state conditions.

- **DC Offset (in Fault Current)**
  A decaying DC component that appears in the fault current when a fault occurs at a point in the voltage cycle that does not match the steady-state current phase. Because the current in an inductive circuit cannot change instantaneously, the initial fault current includes a DC component that makes the total current asymmetrical, with one half-cycle peaks much larger than the other. The DC component decays exponentially with a time constant L/R of the faulted circuit (typically 30-100 ms for transmission faults). The DC offset increases the peak current and the asymmetrical RMS current during the first few cycles, which is critical for circuit breaker making capacity and for calculating mechanical forces on busbars and cables.

## Protection

- **Prospective Fault Current**
  The current that would flow at a given point in the network under fault conditions if the protective devices were replaced by conductors of negligible impedance. It represents the maximum possible fault current and is determined solely by the source impedances and the system voltage. Prospective fault current is the quantity used to specify circuit breaker and fuse ratings. It is calculated at the design stage for every point in the network where protective devices are installed.

## 14. Protection

- **Protective Relay**
  A device that monitors power system quantities (current, voltage, frequency, impedance) and initiates switching operations (typically circuit breaker tripping) when predetermined conditions are met. Modern numerical relays are essentially dedicated microprocessors that sample voltage and current waveforms at high frequency, compute the relevant quantities digitally, and apply complex logic to determine whether to trip. A single numerical relay can implement multiple protection functions (overcurrent, distance, differential, frequency) simultaneously and can communicate with SCADA systems, providing measurement, event recording, and remote control capabilities.

- **Overcurrent Relay (Inverse Time, Definite Time, Instantaneous)**
  The flow of electric charge through a conductor, measured in amperes (A). Conventional current flows from positive to negative potential, while electron flow is in the opposite direction. In AC systems, current alternates direction sinusoidally, and its magnitude and phase relationship to voltage determine how power is transferred. Current is the primary quantity that causes heating in conductors (via I²R losses) and is the basis for most protection system operation.

- **Directional Relay**
  A relay that can distinguish the direction of power flow or fault current, operating only for faults in one direction (typically forward, away from the source). It uses the phase relationship between voltage and current to determine direction. Directional relays are essential in networks with multiple sources (such as ring main distribution or transmission networks with generation at both ends) where an overcurrent relay alone cannot distinguish between forward and reverse faults. They are often combined with overcurrent or distance elements to create directional overcurrent or directional distance protection.

- **Distance Relay (Impedance Relay)**
  The AC generalisation of resistance, expressed as a complex number Z = R + jX in ohms (Ω). The real part R represents resistance (energy dissipation) and the imaginary part X represents reactance (energy storage and release). The magnitude |Z| gives the ratio of voltage amplitude to current amplitude, while the phase angle gives the time shift between them. Impedance is the central concept in AC circuit analysis and power system modelling: every cable, transformer, generator, and load is characterised by its impedance.

- **Differential Relay**
  A device that monitors power system quantities (current, voltage, frequency, impedance) and initiates switching operations (typically circuit breaker tripping) when predetermined conditions are met. Modern numerical relays are essentially dedicated microprocessors that sample voltage and current waveforms at high frequency, compute the relevant quantities digitally, and apply complex logic to determine whether to trip. A single numerical relay can implement multiple protection functions (overcurrent, distance, differential, frequency) simultaneously and can communicate with SCADA systems, providing measurement, event recording, and remote control capabilities.

- **Under/Over Voltage Relay**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

- **Under/Over Frequency Relay**
  A device that monitors power system quantities (current, voltage, frequency, impedance) and initiates switching operations (typically circuit breaker tripping) when predetermined conditions are met. Modern numerical relays are essentially dedicated microprocessors that sample voltage and current waveforms at high frequency, compute the relevant quantities digitally, and apply complex logic to determine whether to trip. A single numerical relay can implement multiple protection functions (overcurrent, distance, differential, frequency) simultaneously and can communicate with SCADA systems, providing measurement, event recording, and remote control capabilities.

- **RoCoF Relay**
  A device that monitors power system quantities (current, voltage, frequency, impedance) and initiates switching operations (typically circuit breaker tripping) when predetermined conditions are met. Modern numerical relays are essentially dedicated microprocessors that sample voltage and current waveforms at high frequency, compute the relevant quantities digitally, and apply complex logic to determine whether to trip. A single numerical relay can implement multiple protection functions (overcurrent, distance, differential, frequency) simultaneously and can communicate with SCADA systems, providing measurement, event recording, and remote control capabilities.

- **Fuse**
  A sacrificial protective device containing a conductor (the element) that melts when the current exceeds a certain value for a certain time, permanently breaking the circuit. Fuses are the simplest and cheapest protective devices, requiring no external power supply, and are widely used in LV and MV distribution networks. They have a naturally inverse time-current characteristic (higher fault current causes faster melting) and are inherently current-limiting because the element melts before the fault current reaches its prospective peak. The main disadvantage is that they are single-use: they must be replaced after operating, which means a site visit and extended outage.

- **Circuit Breaker (SF6, Vacuum, Oil, Air)**
  A mechanical switching device capable of making, carrying, and breaking currents under normal conditions, and also of making, carrying for a specified time, and breaking currents under specified abnormal conditions (such as short circuit). Unlike a fuse, a circuit breaker can be reset and reused after clearing a fault. Circuit breakers are characterised by their rated voltage, rated current, and breaking capacity. They use various arc-quenching media (SF6 gas, vacuum, oil) to extinguish the arc that forms when the contacts separate under fault current.

- **Protection Coordination / Grading**
  The process of designing protection settings so that the device nearest to a fault operates first, clearing the fault with minimum disruption to the rest of the system. If the nearest device fails, the next upstream device should operate as backup, but only after allowing sufficient time for the primary device to act. Coordination requires careful selection of current thresholds, time delays, and relay characteristics for all devices in the system. The addition of distributed generation makes coordination more complex because fault current contributions become bi-directional, potentially causing relays to see different currents than they were designed for.

- **Time-Current Characteristic**
  The curve showing the relationship between fault current magnitude and relay operating time, plotted on log-log axes. For inverse time overcurrent relays, higher fault currents result in faster operation, following a standardised curve shape (standard inverse, very inverse, extremely inverse) defined by IEC or IEEE standards. The time-current characteristic determines how the relay responds to different fault severities and is the primary tool for coordination between successive protection devices. Each relay's curve must be positioned to ensure it operates before the upstream relay for all fault currents within its zone.

- **Pickup Current**
  The minimum current at which a protection relay or fuse begins to operate (starts timing or initiates tripping). It must be set above the maximum expected load current (to avoid spurious tripping during normal operation) but below the minimum expected fault current (to ensure operation for all faults in the protected zone). The ratio of minimum fault current to pickup current is called the sensitivity, and must be greater than 1 for the protection to work. Setting the pickup current is one of the most important decisions in protection design, requiring knowledge of both maximum load and minimum fault conditions.

- **Zones of Protection (Zone 1, Zone 2, Zone 3)**

- **Primary Protection and Backup Protection**

- **Auto-Reclosing**
  The automatic re-energisation of a line after it has been tripped by protection, based on the expectation that many faults (particularly on overhead lines) are transient (caused by lightning, wind, or animals) and will have cleared by the time the line is re-energised. The reclosing sequence typically includes one or more attempts with increasing dead times between them. Auto-reclosing significantly improves supply continuity on overhead line networks, where 80-90% of faults are transient. However, it must be inhibited or used with care on cable networks (where faults are usually permanent) and where distributed generation is present (due to islanding risks).

- **Earth Fault Protection**
  Protection specifically designed to detect faults between a phase conductor and earth (ground), which may produce fault currents too small for conventional overcurrent protection to detect (particularly in high-impedance grounded or unearthed systems). Earth fault protection typically measures the residual current (the sum of the three phase currents, which is zero under balanced conditions but non-zero during an earth fault). It can use core balance current transformers (which directly measure the residual current) or calculated residual current from three individual CTs. Sensitive earth fault protection is essential for detecting high-impedance faults such as broken conductors lying on the ground.

- **Arc Flash**
  An explosive release of energy caused by an electric arc between conductors or between a conductor and ground, producing intense heat (up to 20,000°C), light, pressure waves, and potentially molten metal. Arc flash energy depends on the fault current magnitude, the clearing time of the protection, and the distance from the arc. It is a major electrical safety hazard for personnel working on live or potentially live equipment. Arc flash risk assessment and mitigation (through faster protection, reduced fault levels, engineering controls, and appropriate personal protective equipment) is a legal requirement in most jurisdictions.

## Power Electronics

- **Fault Ride-Through (FRT) / Low Voltage Ride-Through (LVRT)**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

## 15. Transmission and Distribution

- **Overhead Line**

- **Underground Cable**

- **Transmission Line Parameters (R, L, C, G per unit length)**

- **Characteristic Impedance (Surge Impedance)**
  The AC generalisation of resistance, expressed as a complex number Z = R + jX in ohms (Ω). The real part R represents resistance (energy dissipation) and the imaginary part X represents reactance (energy storage and release). The magnitude |Z| gives the ratio of voltage amplitude to current amplitude, while the phase angle gives the time shift between them. Impedance is the central concept in AC circuit analysis and power system modelling: every cable, transformer, generator, and load is characterised by its impedance.

- **Surge Impedance Loading (SIL)**
  The AC generalisation of resistance, expressed as a complex number Z = R + jX in ohms (Ω). The real part R represents resistance (energy dissipation) and the imaginary part X represents reactance (energy storage and release). The magnitude |Z| gives the ratio of voltage amplitude to current amplitude, while the phase angle gives the time shift between them. Impedance is the central concept in AC circuit analysis and power system modelling: every cable, transformer, generator, and load is characterised by its impedance.

- **Ferranti Effect**

- **Corona Discharge**

- **Bundled Conductors**

- **ACSR (Aluminium Conductor Steel Reinforced)**

- **Voltage Levels (LV, MV, HV, EHV)**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

- **Substation**

- **Switchgear**

- **Disconnect Switch (Isolator)**

- **Capacitor Bank**

- **Shunt Reactor**

- **Distribution Feeder**
  A transformer that steps down voltage from the medium-voltage distribution network (typically 11 kV in the UK) to low voltage (400/230V) for delivery to end consumers. Distribution transformers are the most numerous transformers in the power system (there are hundreds of thousands in the UK) and are designed for high efficiency at low load, since they are often lightly loaded. They are typically rated from 25 kVA to 1 MVA, use oil or dry-type insulation, and operate with natural cooling. Their impedance (typically 4-5%) determines the fault level on the LV network.

- **Radial Network**

- **Ring (Loop) Network**

- **Voltage Regulator**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

## 16. HVDC and FACTS

- **HVDC (High Voltage Direct Current)**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

- **Line-Commutated Converter (LCC)**

- **Voltage Source Converter (VSC)**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

- **Converter Station**

- **DC Link**

- **Monopole / Bipole Configuration**

- **FACTS (Flexible AC Transmission Systems)**

  - SVC (Static VAR Compensator)
  - STATCOM (Static Synchronous Compensator)
- **Reactive Power Compensation**
  The component of power that oscillates between source and load without performing net work, measured in volt-amperes reactive (VAr). It arises from energy being alternately stored in and released from magnetic fields (inductive loads) or electric fields (capacitive loads): Q = VI sin(φ). Reactive power is essential for maintaining voltage levels across the network, since voltage at a bus is strongly influenced by the local reactive power balance. Although it does no net work, it increases the current flowing through conductors and therefore increases losses.

- **Voltage Support**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

## 17. Energy Storage

- **Battery Energy Storage System (BESS)**

- **State of Charge (SoC)**
  The process of determining the most likely state (voltage magnitudes and angles at all buses) of the power system from a set of redundant, imperfect measurements (power flows, injections, voltage magnitudes from SCADA). It uses statistical techniques (typically weighted least squares) to find the state that best fits all measurements simultaneously, and can detect and identify bad measurements. State estimation runs every few minutes in control centres and provides the real-time network model on which all other operational analyses (contingency analysis, economic dispatch, etc.) are based.

## Power System Stability

- **State of Health (SoH)**
  The process of determining the most likely state (voltage magnitudes and angles at all buses) of the power system from a set of redundant, imperfect measurements (power flows, injections, voltage magnitudes from SCADA). It uses statistical techniques (typically weighted least squares) to find the state that best fits all measurements simultaneously, and can detect and identify bad measurements. State estimation runs every few minutes in control centres and provides the real-time network model on which all other operational analyses (contingency analysis, economic dispatch, etc.) are based.

## Power System Stability

- **Depth of Discharge (DoD)**

- **Cycle Life**

- **C-Rate**

- **Round-Trip Efficiency**

- **Energy Density vs Power Density**

- **Lithium-Ion (NMC, LFP, NCA)**

- **Flow Battery (Vanadium Redox)**

- **Pumped Hydro Storage**

- **Flywheel Energy Storage**

- **Compressed Air Energy Storage (CAES)**

- **Hydrogen (Electrolysis, Fuel Cell, Power-to-Gas)**

- **Battery Management System (BMS)**

- **Cell Balancing**

- **Thermal Runaway**

## 18. Grid Integration of Renewables

- **Grid Code**

- **Point of Common Coupling (PCC)**

- **Hosting Capacity**

- **Curtailment**

- **Capacity Firming**

- **Ramp Rate Control**

- **Reactive Power Capability**
  The component of power that oscillates between source and load without performing net work, measured in volt-amperes reactive (VAr). It arises from energy being alternately stored in and released from magnetic fields (inductive loads) or electric fields (capacitive loads): Q = VI sin(φ). Reactive power is essential for maintaining voltage levels across the network, since voltage at a bus is strongly influenced by the local reactive power balance. Although it does no net work, it increases the current flowing through conductors and therefore increases losses.

- **Voltage Regulation (at PCC)**
  The electric potential difference between two points in a circuit, measured in volts (V). It represents the energy per unit charge available to drive current through a conductor. In power systems, voltage levels are used to classify networks: low voltage (below 1 kV), medium voltage (1-33 kV), high voltage (33-275 kV), and extra-high voltage (275 kV+). Maintaining voltage within tight tolerances is one of the fundamental operational requirements of any electrical grid.

- **Harmonic Limits**

- **Interconnection Standards (IEEE 1547, G98/G99)**

- **Network Reinforcement**

- **Active Network Management (ANM)**

- **Demand-Side Response (DSR)**

- **Virtual Power Plant (VPP)**

- **Aggregator**

- **Distributed Energy Resource (DER)**

- **Distributed Generation (DG)**

- **Net Metering**

- **Feed-in Tariff**

- **Power Purchase Agreement (PPA)**

- **Renewable Energy Certificate (REC)**

- **Capacity Market**

- **Ancillary Services**

- **Balancing Mechanism**

- **Duck Curve**

- **Renewable Penetration Level**

- **System Non-Synchronous Penetration (SNSP)**

## 19. Smart Grid Basics

- **Smart Grid**

- **Smart Meter**

- **Advanced Metering Infrastructure (AMI)**

- **Phasor Measurement Unit (PMU)**
  A complex number representing the magnitude and phase of a sinusoidal quantity at a fixed frequency. A voltage v(t) = V_m cos(ωt + φ) is represented as the phasor V = V_m∠φ (or equivalently V_m e^{jφ}). Phasors eliminate the need to work with time-domain trigonometric functions, reducing AC circuit analysis to complex algebra. They are valid only for sinusoidal steady-state analysis at a single frequency, but this covers the vast majority of power system operating conditions.

- **SCADA (Supervisory Control and Data Acquisition)**

- **Energy Management System (EMS)**

- **Distribution Management System (DMS)**

- **IEC 61850**

- **Demand Response**

- **Time-of-Use Tariff**

- **Vehicle-to-Grid (V2G)**

## 20. Control Systems (Essentials)

- **Open-Loop vs Closed-Loop Control**

- **Feedback Control**

- **PID Controller (Proportional, Integral, Derivative)**

- **Phase-Locked Loop (PLL)**

- **dq0 Transform (Park Transform)**

- **Clarke Transform (alpha-beta)**

## 21. Reliability and Economics

- **Reliability Indices (SAIDI, SAIFI, CAIDI)**

- **Loss of Load Expectation (LOLE)**

- **N-1 Criterion**
  A security standard requiring that the power system must be able to withstand the loss of any single component (generator, line, or transformer) without violating any operational limits. This means the system must be operated with sufficient margin that no single failure causes cascade overloads, voltage collapse, or loss of supply. The N-1 criterion is the fundamental planning and operating standard for transmission systems worldwide. More stringent criteria (N-2, N-1-1) are sometimes applied for critical infrastructure or extreme events.

- **Reserve Margin**

- **Effective Load Carrying Capability (ELCC)**

- **De-rating Factor**

- **Transmission Loss Factor**

## 22. Emerging Topics

- **Grid-Forming vs Grid-Following Control**

- **100% Inverter-Based Resource Grid**

- **Weak Grid / Strong Grid (Short-Circuit Ratio)**

- **Agrivoltaics**

- **Building-Integrated PV (BIPV)**

- **Dynamic Line Rating**

- **Hybrid Power Plant (Solar + Wind + Storage)**

- **Co-located Storage**

- **DC Microgrid**

- **GaN and SiC Power Electronics**
  The ratio of real power to apparent power, cos(φ) = P/|S|, ranging from 0 to 1. A power factor of 1 means all current is doing useful work; a power factor of 0.5 means the equipment must carry twice the current needed for the actual power delivered. Low power factor increases losses and requires oversized equipment. Industrial consumers are often penalised for low power factor, and power factor correction (typically via capacitor banks) is a routine part of electrical installation design.

- **Sector Coupling (Power-to-Heat, Power-to-Hydrogen)**