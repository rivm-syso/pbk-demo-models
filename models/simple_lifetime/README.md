# Simple lifetime PBK model

Simple lifetime PBK model with body weight dynamically changing over time. The growth of the nominal body weight of an individual is modelled as:

$$\mathtt{BW}_{\mathtt{nom}}(\mathtt{age}) = \mathtt{BW}_{\mathtt{adult}} \cdot \exp \left ( \log \left( \frac{BW_\mathtt{birth}}{BW_\mathtt{adult}} \right ) \cdot \exp \left ( -k_{\mathtt{growth}} \cdot \mathtt{age} \right ) \right )$$

With:
- $\mathtt{BW}_{\mathtt{adult}}$: Nominal body weight of an adult in the population (in kg).
- $\mathtt{BW}_{\mathtt{birth}}$: Nominal body weight at birth in the population (in kg).
- $k_{\mathtt{growth}}$: Growth-rate constant (per hour).

For a simulated individual $i$ in the population, the body weight of the individual is calculated as:

$$\mathtt{BW}_{i}(\mathtt{age}) = \Delta_{\mathtt{BW}, i} \cdot \mathtt{BW}_{\mathtt{nom}}(\mathtt{age}) $$

Where $\Delta_{\mathtt{BW}, i}$ is a multiplicative factor representing the relative difference of the body weight of individual $i$ compared to the nominal value of the population.

For an individual $i$, $\Delta_{\mathtt{BW}, i}$ can be computed based from a single body weight measurement ($\mathtt{BW}_{\mathtt{ref}}$) at some age ($\mathtt{age}_{\mathtt{ref}}$) via:

$$\Delta_{\mathtt{BW}, i} = \frac{\mathtt{BW}_{\mathtt{ref}}}{\mathtt{BW}_{\mathtt{nom}}(\mathtt{age_{\mathtt{ref}}})}$$

The following model parameters control the age/body weight dynamics:
- `AgeInit`: Age at start of simulation (in years).
- `BWRef`: Reference body weight (in kg).
- `AgeRef`: Age of reference measurement (in years).
- `BWBirth`: population nominal body weight at birth (in kg).
- `BWAdult`: population nominal asymptotic/mature body weight (in kg).
- `kGrowth`: Growth-rate constant of body weight (per hour).

The model includes the following internal state-variables are part of the model (i.e., calculated during simulation):
- `Age`: Asymptotic/mature body weight (in years).
- `BW`: Asymptotic/mature body weight (in kg).
- `deltaBW`: Relative body weight of reference individual compared to population nominal body weight.

In this model, age is included as well, also updated using a similar rate rule. This is not strictly needed, but kept as reference.
