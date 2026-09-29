# Engineering Validation

## Purpose

This document summarizes the engineering basis used for the POLAR PULSE prototype and scalable architecture.

## Primary Energy Model

The primary computational model evaluates a 30-day operating scenario at a 1-hour timestep.

### Model configuration

- 9 WEC arms
- 75 W rated generator per arm
- 100 W solar input model
- 12.8 V × 50 Ah battery
- 640 Wh nominal battery energy
- Hs = 0.5, 1, 2 and 3 m sea-state scenarios
- Normal / Low Energy / Storm Protection operating states

### Energy-flow basis

```text
Wave Height
     ↓
Arm Displacement
     ↓
Angular Displacement
     ↓
Angular Velocity
     ↓
Mechanical Power
     ↓
Drivetrain Efficiency
     ↓
Generator Efficiency
     ↓
Electrical WEC Power
     ↓
Battery / System Load Balance
```

## Mechanical Validation

Engineering checks include:

- Arm loading
- Shaft sizing
- Fatigue verification
- Bearing selection
- Oscillatory bearing life considerations

## Electrical Validation

Engineering checks include:

- Cable sizing
- Fuse and protection selection
- Connector sizing
- DC/DC conversion
- Voltage-drop assessment
- Thermal considerations
- Energy-budget analysis

## Protection Logic

The model includes energy-aware operating states:

**Normal → Low Energy → Storm Protection**

A conservative storm-protection rule is applied at **Hs ≥ 3 m** in the simulation model.

This is a modelled protection rule and should not be described as experimentally field-validated.

## Computational Tools

Python-based analysis using:

- NumPy
- Pandas
- Matplotlib
- Python dataclasses

## Validation Boundaries

Simulation results are engineering scenarios. They do not constitute physical sea trials, Antarctic field validation or certification.

Final deployment requires:

- Component-level testing
- Structural testing
- Environmental qualification
- Battery and thermal testing
- Communication testing
- Field trials

## Real-Data Experiments

ERA5 and Copernicus Marine workflows are maintained as experimental environmental-data integration paths.

These datasets provide environmental forcing/reanalysis and should not be described as direct prototype sensor measurements.
