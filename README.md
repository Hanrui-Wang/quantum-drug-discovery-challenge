# ICCAD 2023 Quantum Computing for Drug Discovery Challenge

Team MIT-EPiQC-CMU-Duke

Hanrui Wang*, Pengyu Liu*, Junyao Zhang, Pingzhi Li, Shreya Chaudhary, Tianlong Chen, Yiran Chen, Frederic T. Chong, Song Han

### Overview
In our work, we perform optimization on four aspects:

**(1) Ansatz Design**: 
  * (A) We propose to first use hardware-efficient ansatz with native gates of the targeted device and compatible with coupling map to directly construct the ansatz. 
  * (B) We further leverage the QuantumNAS technique to search for an ansatz that is sufficient (in terms of depth and number of parameters) for the given Hamiltonian. 
  
**(2) Parameter Training**: 
  * (A) We first propose a brand new technique -- ResilienQ, that performs noise-aware parameter training with feedback from the noisy simulator. 
  * (B) We also perform quantum gate pruning that remove the gates with close to zero rotation angles. Additionally, if the gate has an angle close to 180 degrees, we also replace it with the corresponding non-parameterized gate, such as replacing RX(pi) with X to reduce depth. 

**(3) Noise Mitigation** 
  * (A) We perform noise-aware qubit mapping to select the best qubit set according to the noise calibration information. 
  * (B) We also perform measurement noise mitigation with the 0-1 measurement error matrix obtained from noise calibration.
  * (C) Zero Noise Extrapolation technique is also applied to further reduce the incoherence errors.

**(4) VQE-Specific Optimizations** 
  * (A) We first adopt the Pauli string grouping technique to reduce the number of required measurements.
  * (B) We propose a new technique that allocates the shots according to the coefficient of the Pauli strings to minimize the overall result variance.
  * (C) Motivated by the observation that many coefficients are very close to zero and the JigSaw and VarSaw papers, we also propose Pauli string pruning where some groups with small coefficients are removed.

### How to run the code
Please use our evaluation [notebook](./noisy_eval.ipynb) to obtain the evaluation results.

### Contact
Hanrui Wang (hanrui@mit.edu)
