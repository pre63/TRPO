# Trust Region Policy Optimization Variants in Continuous Control

This repository investigates Trust Region Policy Optimization (TRPO) algorithms in continuous control settings. We extend TRPO with entropy regularization and eligibility traces to enhance exploration and advantage calculation, alongside comparisons with established baselines. The research draws on the foundational work of Schulman et al. (2015), who introduced TRPO as a robust policy optimization algorithm with monotonic improvement guarantees ([Schulman et al., 2015](https://doi.org/10.48550/arXiv.1502.05477)).

## Models

The repository includes several TRPO implementations. `EnTRPO` extends the standard TRPO by introducing entropy-based regularization to improve exploration and generalization. This approach is inspired by the work of Roostaie and Ebadzadeh (2021), who demonstrated the benefits of entropy regularization in policy optimization ([Roostaie and Ebadzadeh, 2021](https://doi.org/10.48550/arXiv.2110.13373)). The `EnTRPO3` variant adapts this method for compatibility with Stable Baselines3, leveraging the robust reinforcement learning implementations described by Raffin et al. (2021) ([Raffin et al., 2021](http://jmlr.org/papers/v22/20-1364.html)). Additionally, the `EnTRPOTrace` model incorporates eligibility traces to refine advantage calculation, offering a more experimental perspective. Baseline models include the original `TRPO` implementation and its Stable Baselines3 counterpart, `TRPO3`.

## Research Context

Experiments are conducted using Gymnasium environments, including Box2D, classic control, and Mujoco tasks, ensuring robust validation of the models across diverse control scenarios. The research focuses on hyperparameter sensitivity, sample efficiency, and reward stability. Metrics such as average rewards, reward variance, actor-critic loss, and KL divergence are used to evaluate performance and adherence to trust region constraints.

Entropy regularization, as implemented in `EnTRPO`, draws on its proven ability to encourage exploration and generalization by promoting stochastic policy behavior ([Roostaie and Ebadzadeh, 2021](https://doi.org/10.48550/arXiv.2110.13373)). The experiments are informed by foundational principles of TRPO, which emphasize iterative policy optimization under trust region constraints ([Schulman et al., 2015](https://doi.org/10.48550/arXiv.1502.05477)).

## Experimentation and Usage

The repository supports automated experimentation and hyperparameter tuning through cross-validation pipelines. Experiments, evaluations, and logs are managed via the Makefile, streamlining the execution of models such as `EnTRPO`, `EnTRPO3`, and `EnTRPOTrace`. For Stable Baselines3 variants, the implementation builds on the reliable and modular design described in the Stable Baselines3 framework ([Raffin et al., 2021](http://jmlr.org/papers/v22/20-1364.html)).

## Installation

To set up the environment, use the Makefile commands. Install dependencies and set up the virtual environment with `make install`, and clean up temporary files and caches using `make clean`. The provided setup ensures consistency and reproducibility across experiments.

## Results

Results are saved in organized folders containing logs, checkpoints, and metrics, providing a robust foundation for further analysis. This repository supports research into policy optimization techniques, drawing on key advances in TRPO ([Schulman et al., 2015](https://doi.org/10.48550/arXiv.1502.05477)), entropy-based exploration ([Roostaie and Ebadzadeh, 2021](https://doi.org/10.48550/arXiv.2110.13373)), and Stable Baselines3 implementations ([Raffin et al., 2021](http://jmlr.org/papers/v22/20-1364.html)).
