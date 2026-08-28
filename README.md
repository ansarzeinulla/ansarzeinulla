# ⚡️ Ansar Zeinulla

I am a Systems & AI Researcher at Nazarbayev University, bridging complex combinatorial game theory with highly optimized, low-level execution. I specialize in C++ high-performance computing, WebAssembly, and hardware-aware deep learning optimizations on constrained silicon.

### 🔬 Core Research & Systems Projects

* **[libAMX / amxpy: Bare-Metal AMX Engine for 1.58-bit LLMs](https://github.com/ansarzeinulla/amxpy)** | *Hardware Acceleration*
  * Reverse-engineered Apple's undocumented AMX matrix coprocessor to build a zero-copy C++/Python inference engine for 1.58-bit (ternary) neural networks, completely bypassing the native Accelerate framework.
  * Achieved **3.64 TOPS** on an M2 Pro (outperforming Apple's `cblas_sgemm` by **2.65x** during batched prompt ingestion) with an 8x reduction in memory bandwidth footprint.
  * Engineered a dynamic silicon capability probe to safely dispatch undocumented `matint` opcodes and vectorized K-block accumulations, bypassing silent hardware faults across M1/M2/M3 architectures.

* **[9Q Engine: Bounding a $10^{25}$ Game Tree](https://github.com/ansarzeinulla/9Q)** | *Under Review: IEEE Transactions on Games*
  * Calculated the exact state-space complexity upper bound of the asymmetric mancala game *Togyzkumalak*.
  * Built a concurrent 1-billion game C++ Minimax engine with 16-byte aligned Zobrist Transposition Tables. Cross-compiled the search core to WebAssembly with dynamic JavaScript memory hooks (1.43M NPS native, 0.85M NPS Wasm).

* **[NogaiLLM: Curing Catastrophic Forgetting](https://github.com/ansarzeinulla/NogaiLLM-Apple-Silicon)** | *Under Review: ACM TALLIP*
  * Formulated an end-to-end NLP framework for zero-resource Turkic language adaptation (Qwen-2.5 1.5B).
  * Resolved critical OS-level memory leaks inside the macOS Metal driver API by engineering a garbage-collection cache threshold, stabilizing multi-epoch QLoRA training on unified memory architectures.

* **[Upstream Contributions to `llama.cpp`](https://github.com/ggml-org/llama.cpp/pull/27589)** | *Open Source*
  * Designed blocked 8x8 `i8mm` / `SMMLA` vector kernels for ternary `TQ2_0` weights, bypassing scalar fallbacks and achieving an **+85.6% speedup** in prompt ingestion on Apple Silicon.

### 🔜 Upcoming Publication
* **Strongly Solving Bestemshe:** Generating an 8.3 GB ZSTD-compressed retrograde endgame Tablebase (Oracle) and benchmarking ResMLP neural approximations to quantify compounding decision errors over deep-tree MDPs (Targeting ICLR 2027).

### 🛠️ Tech Stack
* **Languages:** C/C++, Python, SQL, WebAssembly (Wasm/Emscripten), Bash
* **Systems & HPC:** Apple AMX/Metal, Hardware Probing, SIMD/NEON Kernels, Cache Alignment, ZSTD Compression
* **AI Infrastructure:** MLX Framework, PyTorch, Parameter-Efficient Fine-Tuning (PEFT), Ternary/INT4 Quantization
