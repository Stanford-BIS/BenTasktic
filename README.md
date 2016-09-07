# BenTasktic - Tasks for Ben

# Braindrop

Tasks for (*hopefully :'-(* ) November run

## Master Bias Generator (PTAT)
  - [ ] Test and validate schematic
    - [ ] Resistor value & dropped voltage
    - [ ] PSRR
      - [ ] SPICE (AC analysis)
    - [ ] Generated current range (200pA stepped down to 100fA through four mirrors)
      - [Note:] A single stage mirror needs about 25 Tx on each side to get 95% within +/- 10%. So, for about 1/15 gain per stage, we have a transistor ratio of ~ 375:25 per stage.
    - [ ] PTAT performance across corners
  - [ ] Layout

## DAC
  - [x] Schematic
  - [ ] Layout
    - [x] Analog core
    - [ ] Trim metal
    - [ ] Short and drive duplicate wires

## Voltage Buffer
  - [ ] Test and validate schematic
    - [x] Size transistors
    - [ ] Test for NMOS and PMOS biases
    - [ ] Test across corners

## Neuron
### Synapse
  - [ ] See if I can use MOM (1-8) cap, block all the metal up to 8 and get the same capacitance as the MIM (9-10).
  
### Soma
