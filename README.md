# STeeg



# Startup
  - tPOR = 2^18 x tclk
  - tRST = 2 x tclk


# Form factor

 - To fit Takachi HEN110512 (S/B) external W111.2 x H54.7 x D120mm, internal 99.2W x H49.7 x D116mm.

# Configuration

  - Referential montage using SRB1 internally routed negative inputs.
  - Internal BIAS amplifier is used to reject interference and set patien common mode, components are chosen in bias amplifier feedback path to attain sufficient bandiwdth.
  - RC network on input is a low pass filter with differential capacitor to VREF, assuming fclk = 2.048MHz, the first alias is at fMOD = 1.024MHz and this should have good attenuation.



# Layout, power and passives.

  - AVDD and AVDD1 must be quiet. AVDD1 is the charge pump supply which may have switch transients. AVDD1 and AVSS1 should be starred, and each supply should be bypassed with 10u and 0.1u solid ceramic capacitors.
  - VCAP1 can be MLCC but for improved performance under vibration a tantalum or class 1 (C0G/NPO) should be used.
  - At output, provide VREF and VBIAS for differential capacitance and bias bpins
  - Decoupling capacitors and VCAP1 - VCAP4 should be as close as possible.
  - Optionally split analogue and digital planes, route over the appropriate plane
  - Use COG for differentials
  - 

# Architecture
 - 6-XV quiet input, isolated
 - 
# Component choices

 - Analogue LDO (TPS717 selected)
  - EVM uses TPS73225 on bipolar, 30uV (10-100kHz), 1% accuracy, 37dB @ 10kHz, 58dB @ 100Hz
  - TPS793 200mA, 70dB @ 10kHz, 112mv dropout, SOT-23
  - TPS77350, 55dB @ 1kHz, 30uV
  - TPS717XX, 70dB @ 1kHz, 67dB @100kHz, 30uV (100Hz - 100kHz), SOT-23




# Chaining multiple channels

# Notes

  - ADD LEDs
  - ADD Test Points
 - MICROCONTROLLER BOOT
 - MCU PROG
 - optional 3.3v external