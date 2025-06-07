### 1. Mind Map and Concept Map
### Judul: Implementasi Estimasi Debit Air Sungai berbasis *AI* pada sistem *Edge-Computing*
### Title: Implementation of River Water Debt Estimation AI based on Edge-Computing system
### ConceptMap
```mermaid
flowchart TD
    XXX[Hydrology Water Management] ==> A
    A[Water Debt<br />Estimation] --> | Calculate | B(Measurement)
    B --> | Water Flow/Speed | C(Meter<br />per<br />second) --> | Integration | D(Debt<br />m^3/s)
    B --> | Water Depth | E(Meter) --> | Integration | D(Debt<br />m^3/s)
    B --> | Cross Sectional Area | G(Meter) --> | Integration | D(Debt<br />m^3/s)

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