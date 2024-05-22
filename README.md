# FDFK2D
Efficient two-dimensional teleseismic wavefiled hybrid simulation method for receiver function analysis. This software is written in Fortran with highly optimization and enable parallel computing using the OpenMP.

# Background
Until now, simulation of high-frerquency seismic wavefield in global-scale is still challenging even using large-scale computer clusters. One feasible way to mitigate this issue is to adopt a so-called hybrid method. This method usually computes the wavefield from source to the boundaries of the target heterogeneous media using a fast 1D wavefield sovler (such as AxiSEM, DSM, general Ray method, Normal mode, FK, etc.), which is referred to background wavefield. Then, the complex wavefield in the localized target heterogeneous media is computed using 2D/3D wavefield solver (such as finite difference method, pseduospectral method, finite element method, spectral element method, etc.) with the background wavefield as incident wavefield, which is referred to complete wavefield. In the boundaries of the target heterogenous model, a interface between background wavefield and complete wavefiled is applied. This method can simulate the interactions of incoming teleseismic wavefield with local heterogeneities but reducing these heterogeneities to much smaller local computational domain, which can significantly reduce the computing costs of high-frequency teleseismic wavefield with less computational resources. 

# About
Purpose: This software is a hybrid method of the FD and FK to simulate teleseismic wavefield.

FD: Seismic wavefield modeling using collocated grid finite difference method in two-dimensional elastic isotropic meida.

FK: Seismic wavefield modeling using the frequency-wavenumber or propagator matrix method in three-dimensional elastic isotropic media.

# Citation
If you use this software for your researches and prepare publications, please cciting one of the following papers:

- Youshan Liu, Chenglong Wu, Tao Xu, Liang Zhao, Jiwen Teng. 2024. Efficient two-dimensional teleseismic wavefield hybrid simulation method 
   for receiver function analysis. Seismological Research Letters, undergoing review.
- Chenglong Wu, Tao Xu, Xiaobo Tian, Ross N. Mitchell, Jiyan Lin, Jianfeng Yang, Xin Wang, Zhanwu Lu. 2024. Underthrusting of Tarim lover crust beneath the Tibetan Plateau revealed by receiver function imaging. Geophysical Research Letters, 51, e2024GL108220.

# Installation and Usuage
Before you run this software, you can copy the library files in the `lib` folder to `/usr/lib64` with root permission or add their directory to the environment variable by `export LD_LIBRARY_PATH=/your_path:$LD_LIBRARY_PATH`
Now, you can install this software.
- cd ./src
- make install
- cd ./Tests/test1
- ./run_this_example


# License
FDFK2D is a free software: you can redistribute it and/or modify it under the terms of the MIT License. A copy of this license is provided in LICENSE.
