# Advanced-EM

## Project discription
The aim of this project is to formulate, implement and test an inverse scattering solver that receives the measured scattered field as input and generates an image of the total electric field strength in the vicinity of the unknown scattering object as output. For highly conductive scatterers, this image can be used to estimate the shape of the object. We consider the scattering of TMz time-harmonic waves from perfectly electrically conducting (PEC) scatterers in the second dimension. The core of the calculations is a Galerkin method (Method of Moments, MoM). 

## Forward scattering
The input to the forward solver is the incident field, the PEC scattering limit ∂Ω and the trace Γ, while the output of the forward solver is the calculated intensity of the scattered electric field at Γ. In our case, we construct the forward solver using a Galerkin MoM with Dirac delta sources and point matching.
```math
E^{sca}(x) \approx \frac{\mu_0\omega}{4} \sum_{l = 1}^N H_0^{(2)}(k_0|\mathbf{x}- \mathbf{x'_l}|)J_z(\mathbf{x'_l})
```
```math
\sum_{l = 1}^N c_l H_0^{(2)}(k_0|\mathbf{x_m}- \mathbf{x'_l}|) = - E^{inc}(\mathbf{x_m})
```
## Inverse scattering