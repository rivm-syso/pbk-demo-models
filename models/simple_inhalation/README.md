# Simple inhalation model

Simple PBK model modelling the inhalation exposure route via alveolar air. This modelling of the inhalation route is similar to that of the EuroMix PBK model by Tebby et al. (2020).

## Considerations

* In this model, the alveolar air compartment explicitly models the alveolar air, which is only part of the total air in the lungs.
* Transfer from alveolar air to blood (inhalation) is modelled as perfusion limited (using blood flow rate).
* Transfer from blood to alveolar air (exhalation) is modelled as ventilation limited (using alveolar ventilation rate).
* Tebby et al. (2020) used an alveolar ventilation rate of 2220 L/h in the EuroMix PBK model, which was based on Brown et al. (1997). This seems to be unrealistically high. Therefore instead, an alternative value of 252 L/h was used as model default, based on the following consideration: 
    * alveolar ventilation rate = (Tidal volume – dead space volume) x respiratory rate
    * alveolar ventilation rate = (500 ml (male)/400 mL (female) – 150 mL) x 12 breaths/minute = 4200 mL/min = 252 L/h (male)


## References

* Tebby, C., van der Voet, H., de Sousa, G., Rorije, E., Kumar, V., de Boer, W., Kruisselbrink, J. W., Bois, F. Y., Faniband, M., Moretto, A., & Brochot, C. (2020). A generic PBTK model implemented in the MCRA platform: Predictive performance and uses in risk assessment of chemicals. Food and chemical toxicology : an international journal published for the British Industrial Biological Research Association, 142, 111440. https://doi.org/10.1016/j.fct.2020.111440
* Brown, R. P., Delp, M. D., Lindstedt, S. L., Rhomberg, L. R., & Beliles, R. P. (1997). Physiological parameter values for physiologically based pharmacokinetic models. Toxicology and industrial health, 13(4), 407-484.
