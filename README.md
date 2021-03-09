# ENTERTAIN: machinE learNing-based surrogaTe modEl foR acceleraTing simulAtion drIven optimisatioN (To be completed) 


**Machine Learning-Based Surrogate Model for Accelerating Simulation-Driven Optimisation of Hydropower Kaplan Turbine**

[Shahroz Khan](https://www.shahrozkhan.info/)\*, [Zahid Masood](), [Li Qian]()

[[Paper]](-) [[Presentation]](-) [[Video]](-)


## Overview

This repository contains Matlab implementation of the algorithmic framework of the proposed data-driven approach for accelerating the typical shape optimisation process. 

### Extended Abstract
Extended Abstract:

In this work, a machine learning-based simulation-driven optimisation pipeline is proposed for efficient exploration of high-dimensional design space for optimal turbine design without running time-consuming CFD simulations. The proposed approach is initially driven with a baseline design of the runner bald profile, which is defined with a set of angles defined at the different location along its leading and trailing edges. These parameters are taken as design parameters, which defines a shape modification function and form a 10D design space that needs to explore for an optimal design. The proposed pipeline tackles the curse of dimensionality with a feature extraction approach, which, with the combination of design parameters, build a lower-dimensional subspace. At the discrete level, the feature extraction is similar to solving PCA for the eigendecomposition of a covariance matrix. After feature extraction, the reconstruction accuracy of designs from subspace to original high-dimensional design space is visually validated using Hausdorff distance.
 
Afterwards, the lower-dimensional subspace is utilised to build a surrogate model using the GPR, which is used to infer the difference of relative-tangential velocities of Kaplan turbine at its leading and trailing edges.  Similar to optimisation, the computational complexity for building a surrogate model increases with the dimensionality of the problem mainly because the high-dimensional problem requires a large training dataset, which, especially in engineering design, has to be synthesised by labelling the data with time-consuming physics-based simulations. Therefore, to keep the number of required training instances low we used extracted features as independent parameters during model training. As these features capture maximum geometric variability of designs in the original design space and form a lower-dimensional subspace, therefore, the final trained model has improved prediction accuracy even with few training instances. Furthermore, we used a high-fidelity sampling approach to approximate the design space with few samples, which are increased gradually during the training. Moreover, different kernel functions are tested for GPR and among which squared exponential showed better accuracy. The performance of the GPR is also compared with different machine learning approaches. 
    
For shape optimisation, the final trained surrogate model is connected with a metaheuristic optimiser, which searched the subspace for optimal design with increased efficiency from 56.9867\% to 90.7378\%.  Furthermore, the significance of the design parameters on the turbine’s relative-tangential velocity is evaluated with variance-based sensitivity analysis performed on the subspace, whose results showed that the first two latent variables are the most significant. Afterwards, the correlation between significant latent variables and original design parameters is determined to identify the contribution of design parameters towards relative-tangential velocity. Subsequently, to evaluate the influence of significant latent variables, a 2D surrogate model is developed, which interestingly shows better performance, however, the reconstruction accuracy of design from 2D subspace to original 10D designs space is less than the reconstruction from 4D subspace. 

Finally, the performance of the proposed approach is compared with ASM, which follows the similar strategy of building the surrogate model from a lower-dimensional subspace, but unlike the proposed approach, ASM extracts the functional features based on the gradients. The comparative study performed in this work shows that the proposed approach outperforms AMS in terms of the accuracy of the surrogate model. 
