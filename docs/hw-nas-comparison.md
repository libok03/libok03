# HW-NAS-YOLO — Comparison with Related Work

This comparison uses existing project material and published papers only. No new training, profiling, or benchmark reproduction was performed. It compares research methods and their reported evidence; it does not establish a cross-paper performance ranking.

## 1. What the existing project plots show

Source: [archived experiment plots](../assets/hw_nas_results.png).

All values below are approximate visual readings, not recovered raw measurements. The figure labels the detection metric as **validation mAP_50**.

| Plot / budget | HW-NAS | Random Search | Interpretation |
| :--- | ---: | ---: | :--- |
| Best-so-far validation mAP_50 at 4 evaluated architectures | **≈44.3%** | **≈44.1%** | Same displayed architecture count; a small observed gap, with no uncertainty estimate |
| Best-so-far validation mAP_50 at 20 evaluated architectures | **≈46.1%** | Not displayed | NAS endpoint; the Random Search curve in this panel ends at 4 architectures |
| Hypervolume at 40 evaluated architectures | **≈2.408** | **≈2.271** | NAS has higher displayed hypervolume under this figure's reference convention |

The mAP panel and hypervolume panel show different evaluation-count ranges. They should not be assumed to represent the same experiment or candidate set without the original logs. Architecture count also does not guarantee equal training or compilation cost.

The hypervolume axis states a latency reference of **6.2 ms**. Its numerical value depends on the objective definition, reference point, and scaling. It is not transferable to another paper's hypervolume. Seed count, variability, exact detector hardware, and raw candidate-level values are not established by this image.

## 2. Method comparison

| Dimension | HW-NAS-YOLO project | MobileDets | BRP-NAS | HELP | MO-HDNAS |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Main problem | YOLO-based detection and deployment-aware search | Detection-specific architectures for mobile accelerators | Predictor-based NAS and end-to-end latency estimation | Few-shot latency prediction for unseen devices | Multi-objective search with hardware-cost diversity |
| Architecture / search space | YOLO11n-derived block, depth, and attention choices | Inverted, fused, and Tucker bottlenecks with SSDLite | NAS-Bench-101/201 and DARTS experiments | NAS-Bench-201, MobileNetV3/OFA, and other NAS integrations | NAS-Bench-201 / HW-NAS-Bench |
| Latency model | Random Forest over stage-aware genome features | Linear regression fitted to whole-model on-device measurements | Graph convolutional network | Hardware-conditioned meta-learned predictor | Benchmark hardware-cost data |
| Measurement strategy | Warm-up plus uncertainty-selected TensorRT measurements; predictor updated during search | Offline cost-model collection; final on-device benchmarking | Device-specific measured training samples | Transfer from a device pool, followed by few-shot adaptation | Hardware costs supplied by the benchmark |
| Search / evaluation strategy | NSGA-II; 3→15→50 epoch evaluation; curriculum objectives | TuNAS one-shot search with platform-aware reward | Binary-relation accuracy prediction and iterative selection | Coupled to NAS frameworks such as MetaD2A and OFA | Representation similarity, hardware cost, and cost diversity |
| Relevant distinction | Selective online profiling during detector search | Accelerator-aware detector building blocks | Graph-based latency and architecture-ranking prediction | Transfer to new hardware with few target measurements | Diverse Pareto solutions in one search |

Descriptions of the project follow its paper/README and public implementation. A difference in method is not evidence that one approach performs better.

## 3. Numbers reported by the external papers

These are separate experimental results, not directly comparable scores.

| Work | Reported value | Experimental conditions | What it measures |
| :--- | :--- | :--- | :--- |
| **MobileDets** | **28.0% test AP; 3.2 ms** | COCO test-dev; 320×320; Jetson Xavier; TensorRT FP16; batch 1; Table 2 | Detection quality and device latency |
| **BRP-NAS** | **85.9 ± 1.9%** of predictions within **±5%** latency error | NAS-Bench-201; desktop GPU; 900 training architectures per predictor run; Table 1 | Latency prediction reliability, not detection AP |
| **HELP** | **10 target measurements; 0.987 GPU / 0.989 CPU Spearman correlation** | NAS-Bench-201; unseen target devices; Table 3; prior device-pool meta-training | Latency ranking and adaptation sample efficiency |
| **MO-HDNAS** | **0.65 vs 20.87 GPU-hours** | CIFAR-100 / FPGA comparison with HW-EvRSNAS; Table 1 | One Pareto search versus separate searches for nine cost constraints |

MobileDets uses COCO AP averaged over IoU thresholds, while the project figure labels its value mAP_50. The datasets, image sizes, and devices also differ. Thus **46.1% versus 28.0% is not a valid accuracy comparison**, and project-plot latency cannot establish a speed advantage over Jetson Xavier.

HELP's 10 measurements are adaptation samples, not its total historical data or training cost. Its timing analysis excludes prior meta-training and, where applicable, supernet training. MO-HDNAS's reported cost advantage reflects its specific single-search versus multiple-search setup, not a speedup over this project.

## 4. What the comparison supports

- The archived project figure shows higher HW-NAS hypervolume than its Random Search curve at the displayed 40-architecture endpoint.
- The project combines YOLO-derived architecture choices, multi-fidelity candidate evaluation, and selective online TensorRT profiling.
- MobileDets is the closest detection-oriented reference; BRP-NAS is a useful latency-predictor reference; HELP addresses device transfer; MO-HDNAS addresses multi-objective exploration.
- Whole-model latency prediction and hardware-aware Pareto search already appear in prior work. The project's proposed emphasis is their integration with online measurement selection in its detector-search workflow.

The available material does not establish better detection AP, lower latency, lower total search cost, or better predictor accuracy than these papers. Actual TensorRT measurement counts, wall-clock search costs, raw AP metrics, and prediction-error statistics are not available here.

## 5. Metric provenance in the public implementation

The current [evaluation code](https://github.com/libok03/HW-NAS-YOLO/blob/main/HW_NAS_YOLO/multi_fidelity_evaluator.py) stores a field named `mAP` as `results.box.map + 0.5 * results.box.maps[0]`. This is a composite search score, not standard mAP. According to the [Ultralytics metric documentation](https://docs.ultralytics.com/reference/utils/metrics/), `maps[0]` is the class-0 AP entry, not object-size-specific AP.

The same code derives a slope from `np.linspace`, rather than recorded per-epoch validation values. Consequently, the public code alone does not validate a learning-curve-based candidate-selection claim.

The relationship between this implementation and the archived plots is not established. The plots retain their original metric labels, and this document does not infer that prior experiments used the current implementation.

## References

1. Xiong et al. **MobileDets: Searching for Object Detection Architectures for Mobile Accelerators**, CVPR 2021. [Paper](https://arxiv.org/pdf/2004.14525). Method: Section 4; conditions: Section 5; result: Table 2.
2. Dudziak et al. **BRP-NAS: Prediction-based NAS using GCNs**, NeurIPS 2020. [Paper](https://proceedings.nips.cc/paper_files/paper/2020/file/768e78024aa8fdb9b8fe87be86f64745-Paper.pdf). Latency predictor: Section 3 / Table 1.
3. Lee et al. **HELP: Hardware-Adaptive Efficient Latency Prediction for NAS via Meta-Learning**, NeurIPS 2021. [Paper](https://proceedings.neurips.cc/paper/2021/file/e3251075554389fe91d17a794861d47b-Paper.pdf). Results: Table 3; timing scope: Section 4.2.
4. Sinha et al. **Multi-Objective Hardware Aware Neural Architecture Search using Hardware Cost Diversity**, CVPR Workshops 2024. [Paper](https://arxiv.org/html/2404.12403v1). Objectives: Section 3; results and cost: Section 4 / Table 1.

Compiled on 2026-10-02. Project image blob SHA: `147f4e1eb92e9d71327287e9008aeb3237382074`.
