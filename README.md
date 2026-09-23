# ⚡️ Ansar Zeinulla

BSc Computer Science student at Nazarbayev University (Astana). I work on low-level performance on commodity hardware (Apple AMX and NEON kernels, WebAssembly) and on exact baselines for games and for learned models.

### 🔬 Research & Systems Projects

* **[libAMX / amxpy: ternary GEMM on Apple's undocumented AMX coprocessor](https://github.com/ansarzeinulla/amxpy)**
  * C++/pybind11 engine for 1.58-bit (ternary) weights on the AMX matrix unit, bypassing Accelerate.
  * 3.64 TOPS on an M2 Pro for an M=N=1024, K=4096 GEMM, 2.65× Accelerate's fp32 `cblas_sgemm`.
  * Faster than Accelerate only for batched inputs (e.g. 1.51× at batch 16 on a Llama-3-8B MLP block); slower for single-token decode, where weight decompression dominates.
  * Probes undocumented instruction behaviour at runtime and falls back safely. Verified on M2 Pro only.

* **[9Q: Togyzkumalak complexity and engine](https://github.com/ansarzeinulla/9Q)** | *Under review: ICGA Journal*
  * Upper bound of 1.51×10²⁵ on the state space.
  * Exhaustive search showing no game ends before half-move 11.
  * Statistics from 10⁹ random playouts.
  * Alpha-beta engine with a compact 16-byte transposition table, compiled to WebAssembly ([live demo](https://9qumalaq.vercel.app/)).
  * The early-game search table is independently reproduced by a separately written implementation.

* **[NogaiLLM: adapting an LLM to Nogai](https://github.com/ansarzeinulla/NogaiLLM-Apple-Silicon)** | *Manuscript in preparation*
  * Built a 163,531-row Nogai text corpus (2.35 M words) from newspapers, Bible translations and Wikipedia, plus Russian–Nogai instruction data with a leakage-free split.
  * Adapted Qwen2.5-1.5B in two LoRA stages (continued pre-training, then SFT) on a 16 GB Apple M2 Pro with `mlx-lm`; corpus, adapters and a demo are on [Hugging Face](https://huggingface.co/ansarzeinulla).

* **[llama.cpp PR #27589](https://github.com/ggml-org/llama.cpp/pull/27589)** | *Open, awaiting review*
  * 8×8 `i8mm` (SMMLA) GEMM for ternary `TQ2_0` weights on ARM: +85.6% prompt processing on an M2 Pro, bit-identical perplexity.

* **[Bestemshe](https://github.com/ansarzeinulla/Bestemshe)** | *Paper in preparation*
  * Strong solution of Bestemshe, a 5-pit Kazakh mancala: forced win for the second player, via retrograde analysis.
  * 8.3 GiB ZSTD-compressed tablebase with O(1) lookup, queryable remotely over HTTP Range.
  * Benchmark of a neural value/policy network against the exact oracle.

### 🛠️ Tech Stack
* **Languages:** C/C++, Python, SQL, WebAssembly (Emscripten), Bash
* **Systems & HPC:** Apple AMX, NEON / i8mm kernels, cache-aware data layouts, ZSTD block compression
* **ML:** PyTorch, MLX / mlx-lm, LoRA fine-tuning, ternary / low-bit quantization
