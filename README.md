# BenTasktic - Tasks for Ben

# Braindrop

Tasks for October run

## Master Bias Generator (PTAT)
  - [ ] Need startup circuit?
  - [x] Test and validate schematic
    - [x] Finalize I_unit (inside the core FB circuit) [1pA]
    - [x] Finalize I_out: 1pA (along with V_CAS for each) as input to DAC
    - [x] Finalize resistance
      - 4.x MOhms & 50mV drop
    - [x] PTAT performance across corners
      - Error w.r.t. PTAT < +/- 0.5% over 20-30C
    - [x] Finalize transistor sizes (for mismatch)
      - *[Note] Gain stages are 2.5n x 1/10x1/250 = 1pA
      - *[Note] A single stage mirror needs about 25 Tx on each side to get 95% within +/- 10%*
      - *[Note] Have models in Mathematica that need to be optimized*
    - [x] PSRR
      - Small-signal analysis matches AC for mirrors.
      - With the voltage buffer, the bias generator starts peaking around 10KHz and has 0dB PSRR beyond that.
  - [ ] Layout

## DAC
  - [ ] Schematic
    - [x] Check linearity in SPICE
    - [ ] Custom additions to specific biases
      - [ ] Size global diode transistors (e.g., 4X if synapse's n-m = 4, add/subtract I_W from I_DC from two biases)
  - [ ] Layout
    - [x] Analog core
    - [x] Trim metal
    - [x] Short and drive duplicate wires
    - [x] Provide power landing pads [in M3]
    - [ ] Export LEF (and merge in Voltage Buffer)

## Voltage Buffer
  - [ ] Test and validate schematic
    - [x] Size transistors
    - [ ] Test for NMOS and PMOS biases
    - [ ] Test across corners
    - [ ] Merge with DAC
  - [ ] Layout

## Neuron
  - [ ] Schematic
    - Update 1 Synapse + 2x2 Soma tile
  - [ ] Layout
    - Export LEF
  - [ ] Plan global bias and power lines

### Synapse
  - [ ] See if I can use MOM (1-5) cap, block all the metal up to 8 and get the same capacitance as the MIM (9-10).
    - [x] Can use MOM for Synapse PE: 22.8fF with ~ 3.4𝜇mx4𝜇m area
  - [ ] Schematic
    - [ ] Finalize I_LK range (minimum I_LK = 100fA => maximum = 100pA)
    - [x] Finalize I_PE range [**for t_PE >= 10𝜇s or 500us period, use 1000pA to 20pA**]
    - [x] Finalize I_DC, +/- I_W range [**70pA +- 65pA**]
    - [ ] Finalize I_CM range (if synapse gain != 1)
    - [ ] Finalize capacitance (for tau <= 100ms and t_PE >= 20𝜇s)
      - [ ] C_tau
      - [x] C_PE: MOM cap M3-M5, 22.8fF, ~ 3.4𝜇mx4𝜇m area
    - [ ] Finalize initial transistor sizes (for mismatch), adjust if space available
  - [ ] Layout
  
### Soma
  - [ ] Schematic
    - [ ] Finalize I_REF range
    - [x] Finalize I_OFFSET range (100fA to 100pA) [if I_OFFSET not in Synapse]
    - [ ] Finalize I_R and I_G range
    - [x] Finalize gain & offset bits (if any) [gain = {1, 4}, offset = {-3, -2, -1, 0, 1, 2, 3}]
    - [ ] Finalize initial transistor sizes (for mismatch), adjust if space available
  - [ ] Layout
