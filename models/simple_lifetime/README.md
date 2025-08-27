# Simple lifetime PBK model

Simple lifetime PBK model with bodyweight dynamically changing over time. The growth of body weight is modeled with a differential equation based on the **Gompertz growth model**:

$$\frac{dBW}{dt} = k_{\texttt{growth}} \cdot \ln\!\left(\frac{BW_{\texttt{adult}}}{BW}\right)\,BW$$

where:
- $BW$ = body weight at age $t$
- $BW_{\texttt{adult}}$ = mature (asymptotic) body weight
- $k_{\texttt{growth}}$ = growth-rate constant (per time unit)

The following model parameter control the BW dynamics:
- `BWInit`: Initial body weight (at start of simulation) (in kg).
- `BWAdult`: Asymptotic/mature body weight (in kg).
- `kGrowth`: Growth-rate constant (per hour).

In this model, age is included as well, also updated using a similar rate rule. This is not strictly needed, but kept as reference.
