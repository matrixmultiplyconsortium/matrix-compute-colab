# matrix-compute-colab

[![Open In Colab — 01 Quickstart](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/matrix-compute/matrix-compute-colab/blob/main/01_quickstart_distributed_matmul.ipynb)

Interactive **Google Colab** notebooks for the decentralized **Matrix Compute** network. Try distributed matrix multiplication, topological partitioning benchmarks, and confidential computing (TEE) enclaves directly in your browser using the **Zero-Drain Trial Sandbox (`mode="trial"`)** — **no wallet, credit card, or API key required**.

## Interactive Notebooks

| Notebook | Description | Launch in Browser |
| :--- | :--- | :--- |
| **[`01_quickstart_distributed_matmul.ipynb`](01_quickstart_distributed_matmul.ipynb)** | Installs `matrix-compute`, runs a $4096 \times 4096$ FP32 distributed GEMM ($137.4\text{ GFLOPs}$) in `mode="trial"` with client-side SHA-256 Hashcash PoW and zero-value trial macaroons (`mc_trial_...`), benchmarks $O(n^2)$ Freivalds verification vs. $O(n^3)$ recomputation, and shows the 1-line `nwc_uri="nostr+walletconnect://..."` Mainnet upgrade path. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/matrix-compute/matrix-compute-colab/blob/main/01_quickstart_distributed_matmul.ipynb) |
| **[`02_partitioning_strategies_benchmark.ipynb`](02_partitioning_strategies_benchmark.ipynb)** | Profiles and executes `BLOCK_3D`, `OUTER_PRODUCT_1D` ($R_{up} \equiv 0.0$), and `OUTPUT_GRID_2D` ($R_{down} \equiv 0.0$), verifying zero client-side reduction overhead (`reduction_ops == 0`) and aspect-ratio optimality. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/matrix-compute/matrix-compute-colab/blob/main/02_partitioning_strategies_benchmark.ipynb) |
| **[`03_confidential_computing_tee_demo.ipynb`](03_confidential_computing_tee_demo.ipynb)** | Demonstrates multi-vendor hardware attestation verification (**NVIDIA Hopper CC**, **AMD SEV-SNP**, **Intel TDX**), fail-closed tamper/replay/MITM rejection, and end-to-end AES-256-GCM encrypted tile streaming with wire ciphertext Shannon entropy verification ($H \ge 7.95\text{ bits/byte}$). | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/matrix-compute/matrix-compute-colab/blob/main/03_confidential_computing_tee_demo.ipynb) |

## Zero-Drain Trial Sandbox (`mode="trial"`)

Every notebook runs out-of-the-box in `mode="trial"`, which enforces three cryptographic guardrails so developers can evaluate the protocol with zero onboarding friction:
1. **Zero-Value Trial Macaroon (`mc_trial_...`)**: Locked satoshis are strictly `0 sats` — the settlement node never pays an outbound Lightning invoice for trial jobs.
2. **Seed-Worker Scope & $4096 \times 4096$ Dimension Cap**: Trial macaroons are cryptographically bound to our dedicated seed workers and reject matrices exceeding $4096 \times 4096$ (`PERMISSION_DENIED: Trial macaroon dimension exceeds 4096 cap`).
3. **Client-Side SHA-256 Hashcash PoW**: The SDK automatically solves a 16-bit SHA-256 Hashcash puzzle (`mc_pow:...`) in ~50–150 ms to protect the public trial workers from automated spam.
