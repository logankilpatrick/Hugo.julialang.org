---
layout: single
title:  Scientific Projects – Summer of Code
---

# {{ page.title }}

## Quantum Computation: Simualation of Noisy Circuits

[Noisy Intermediate-Scale Quantum (NISQ) technology will be available in the near future.](https://arxiv.org/abs/1801.00862) However, it would be much more convenient if we could test our algorithm with noise and simulate our quantum algorithm on noisy circuits to explore their stability, efficiency. To assist the research of NISQ, enhance the quantum circuit simulator in Julia [Yao.jl](https://github.com/QuantumBFS/Yao.jl) with noisy circuit simulation would be quite useful. We are planning to implement the algorithm in a recent paper as our SoC project: [Efficient classical simulation of noisy quantum computation](https://arxiv.org/pdf/1810.03176.pdf).

**Recommended Skills**: Background knowledge in quantum information and tensor networks and the ability of coding with Julia.

**Expected Results**: Provide Yao.jl an extension package that defines different kinds of noise and provide Yao.jl with the ability to simulate certain kind of noisy circuits efficiently.

**Mentors**: [Roger Luo](https://github.com/Roger-luo/)

## Quantum Computation: Visualization of Quantum Circuits

Although, there is already a pretty printing for quantum circuits in [Yao.jl](https://github.com/QuantumBFS/Yao.jl) as a tree, we are still lack of visualizing a quantum circuit defined as [block tree](hhttps://docs.yaoquantum.org/dev/man/blocks.html). And we have already had basic plotting utilities in Julia, like [Luxor.jl](https://github.com/JuliaGraphics/Luxor.jl). It would be great and more convenient to provide multiple theme for plotting a quantum circuit with Yao.jl to various formats.

**Recommended Skills**: Basic knowledge in programatic visualization. Experienced with Luxor.jl is preferred but can be learned along the way.

**Expected Results**: Provide Yao.jl an extension package that converts a block tree to an image, which contains not only the circuit but also mark of composite blocks, users should be able to change theme for paper or multi-media use.

**Mentors**: [Roger Luo](https://github.com/Roger-luo/)

**References**: some demo image can be found in Yao.jl's [doc](https://docs.yaoquantum.org/dev/index.html)


## Quantum Computation: Funny Tensor Networks

A Tensor network is a contraction of tensors, it has wide applications in both physics and machine learning fields, it can represent a quantum wave function, a probabilistic model and even a quantum circuit simulation. Now we are going to borrow state of the art technics from both fields to build our new **Julia** tensor network package with **automatic differentiation** and **GPU support**!

**Recommended Skills:** Basic knowledge about Julia language and linear algebra is required. Students who has experience with tensor networks are preferred.

**Expected Results:** A high performance Julia tensor network package with GPU and autodiff support.

**Mentors:** [JinGuo Liu](https://github.com/GiggleLiu)

**References:**

Don't be scared by these fancy terms, Julia has strong support to [tensor operations](https://github.com/Jutho/TensorOperations.jl), writing [native CUDA code in Julia](https://julialang.org/blog/2017/03/cudanative) has similar experience as CPU programming. Also the hard bit - [autodiff for svd](https://github.com/FluxML/Flux.jl/pull/474) has already got a PR in FLux.jl.

In this paper, we have got a PyTorch implementation of "MPS + GPU + autodiff"

> Unsupervised Generative Modeling Using Matrix Product States
>
> Zhao-Yu Han, Jun Wang, Heng Fan, Lei Wang, and Pan Zhang
>
> [Phys. Rev. X 8, 031012](https://journals.aps.org/prx/abstract/10.1103/PhysRevX.8.031012)

Tutorial for tensor networks:

* [Hand-waving and Interpretive Dance: An Introductory Course on Tensor Networks](https://arxiv.org/abs/1603.03039)


## Computational methods using zonotopes

Zonotopes are representations of extended use in set-based analysis, since linear transformations and Minkowski sums can be computed efficiently. However, they are are not closed under intersections. In the literature there exist different alternatives for overapproximation of zonotope intersections with other set types. The package [LazySets.jl](https://github.com/JuliaReach/LazySets.jl) already offers support for zonotopes but lacks some of the state-of-the-art methods.

Zonotopes provide a very good middle ground between hyperrectangular approximations and general polyhedral approximations in terms of performance and accuracy. Applications of this project are the verification of hybrid dynamical systems (see [juliareach.org](juliareach.org)) and in neural network verification (see [AI2](https://ieeexplore.ieee.org/document/8418593) and [NeuralVerification.jl](https://github.com/sisl/NeuralVerification.jl) project).

**Recommended Skills:** Basic knowledge on convex geometry and polyhedral computations is preferred but can be learned along the way. A taste for writing efficient code. 

**Expected Results:** Some possibilities are: overapproximation of zonotopes with polytopes, zonotope-polytope intersections, order reduction metods, Minkowski difference of zonotopes.

**Mentors:** [Marcelo Forets](http://github.com/mforets) and [Christian Schilling](https://github.com/schillic).

**References:** See [Reachability.jl#Publications](https://juliareach.github.io/Reachability.jl/stable/publications/) and references therein, or contact us in the [gitter channel](https://gitter.im/JuliaReach/Lobby).
