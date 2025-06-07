ID: 20924305
Name: Gia Muhammad Agusta

# 1. Mind Map and Concept Map:
# Implementasi Estimasi Debit Air Sungai berbasis *AI* pada sistem *Edge-Computing*
# Implementation of River Water Debt Estimation AI based on Edge-Computing system
# Mindmap

```mermaid
mindmap
  root((Water Debt<br />Estimation))
    Problem
      Production Cost
      Automation.<br />Data and Operator Intervention
      Production Mass Complexity
      Damage Probability
      Computational Cost
    GAP
      Not all previous<br />study measure Water Debt
      Not implemented on Edge-Computing
      Lack of Accuracy<br />due to illuminance or<br />others condition 
    Measurement
      Water Flow Velocity
        AI-Based
          Recurrent All Pairs Field Transformer
          RivVideoFlow
        Non-AI
          Propeler or Hardware Based
          Optical Flow<br />Algorithm
      Water Depth
        Sonar Based
        Depth Sensor
          Stereo Vision
          Structured Light
      Cross Sectional Area
        Normal Distribution<br />Assumption
        Manual Measurement
      Water Debt
        Integrating<br />all measurement
    Existing Method
      Intrusive
        Vertical Stilling Wells
        Acoustic Doppler Velocimeters
      Non-Intrusive
        Remote Sensing
        High Frequence Doppler
        Edge-Computing
```

# ConceptMap
```mermaid
flowchart TD
    XXX[Hydrology Water Management] ==> A
    A[Water Debt<br />Estimation] --> | Calculate | B(Measurement)
    B --> | Water Flow/Speed | C(Meter<br />per<br />second) --> | Integration | D(Debt<br />m^3/s)
    B --> | Water Depth | E(Meter) --> | Integration | F(Debt<br />m^3/s)
    B --> | Cross Sectional Area | G(Meter) --> | Integration | H(Debt<br />m^3/s)

    A[Water Debt<br />Estimation] --> | Design | I[System]
    I --> | Architecture | J[System<br />and<br />Instrument]
    J --> | use edge-computing | K(Raspberry Pi-4)
    K --> | to run existing model of | L(RAFT)
    L --> | to get prediction of | P(Water Flow)
    K --> | use | M(RGB Sensor)
    M --> | to get | O(Real Time<br />Image)
    K --> | to run | N(Perspective<br />Projection)
    N --> | to get | R(Normalized Image)
    J --> | use sensor | Q(ASUS Xtion<br />Camera Sensor)
    Q --> | use method | S(Structured Light)
    S --> | to get | T(Depth)
    I --> | Integration | U[Custom Integration<br />Formula]
    U --> | to get | V(Water Debt)
    A[Water Debt<br />Estimation] --> | Evaluate | W(System<br />and<br />Measurement)
    W --> | comparing | X(Accuracy)
    W --> | calculate cost of | Y(Computation)
    W --> | calculate cost of | Z(Infrastructure)
```