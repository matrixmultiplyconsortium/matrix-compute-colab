# Matrix Compute Interactive Colab Notebooks (`matrix-compute-colab`)

Zero-install interactive Jupyter and Google Colab notebooks for testing and benchmarking the **Distributed Matrix Multiplication** network in under 60 seconds.

## Notebooks
1. **`01_quickstart_distributed_matmul.ipynb`:** 5-line quickstart using the Zero-Drain Trial Sandbox (`mode="trial"`) to dispatch a $4096 \times 4096$ matrix multiplication to idle seed GPU workers and verify the result in $O(n^2)$ using Freivalds' algorithm, plus 1-line NWC (`nostr+walletconnect://`) Mainnet configuration.
2. **`02_partitioning_strategies_benchmark.ipynb`:** Interactive comparison of 3D Inner-Product, 1D Outer-Product (`OUTER_PRODUCT_1D`), and Zero-Reduction 2D Output Grid (`OUTPUT_GRID_2D`) bandwidth and latency profiles.
3. **`03_confidential_computing_tee_demo.ipynb`:** End-to-end encrypted matrix dispatch with hardware attestation verification (NVIDIA CC, AMD SEV-SNP, Intel TDX).
