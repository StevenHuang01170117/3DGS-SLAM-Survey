# 3DGS-SLAM-Survey

> Systematic reproduction and benchmark of 10+ 3DGS / 3DGS-SLAM algorithms on TUM-RGBD dataset.
> Unified evaluation pipeline for fair comparison across offline reconstruction and real-time SLAM methods.

## 📊 Benchmarked Algorithms

| Algorithm | Type | Code Source | Status |
|-----------|------|-------------|--------|
| Hierarchical3DGS | Offline | [Official](https://github.com/graphdeco-inria/hierarchical-3d-gaussians) | ✅ Reproduced |
| MemGS | Real-time SLAM | [Official](https://github.com/NAIL-HNU/MemGS_SLAM) | ✅ Reproduced |
| LEGO-SLAM | Real-time SLAM | [Official](https://github.com/Lab-of-AI-and-Robotics/LEGO-SLAM) | ✅ Reproduced |
| SplaTAM | Real-time SLAM | [Official](https://github.com/spla-tam/SplaTAM) | ✅ Reproduced |
| VINGS-Mono | Real-time SLAM | [Official](https://github.com/Fudan-MAGIC-Lab/VINGS-Mono) | ✅ Reproduced |
| MonoGS | Real-time SLAM | [Official](https://github.com/muskie82/MonoGS) | ✅ Reproduced |
| PhotoSLAM | Real-time SLAM | [Official](https://github.com/HuajianUP/Photo-SLAM) | ✅ Reproduced |
| Traditional 3DGS | Offline | [Official](https://github.com/graphdeco-inria/gaussian-splatting) | ✅ Reproduced |

*Note: Source code of each algorithm is NOT included. Please refer to their official repositories.*

## 🎯 Evaluation Results (TUM-RGBD)

*Metrics: PSNR(dB) ↑ / SSIM ↑ / LPIPS ↓ / Tracking FPS ↑ / VRAM(GB) ↓ / Points ↓*
*Traditional 3DGS & Hierarchical3DGS are offline methods (no Tracking FPS).*

### Scene 1: fr1_desk
| Algorithm | Type | PSNR ↑ | SSIM ↑ | LPIPS ↓ | FPS ↑ | Mem(GB) | Points ↓ |
|-----------|------|--------|--------|---------|-------|---------|----------|
| SplaTAM | Real-time SLAM | 21.680 | - | - | 0.196 | 1.476 | 971,162 |
| Photo-SLAM | Real-time SLAM | 19.60 | - | - | 10.25 | 0.559 | 36,821 |
| MemGS | Real-time SLAM | 18.218 | - | - | 9.217 | 1.190 | 36,678 |
| **Ours (A+B)** | **Real-time SLAM** | **23.364** | **-** | **-** | **9.377** | **3.064** | **21,911** |

### Scene 2: fr2_xyz
| Algorithm | Type | PSNR ↑ | SSIM ↑ | LPIPS ↓ | FPS ↑ | Mem(GB) | Points ↓ |
|-----------|------|--------|--------|---------|-------|---------|----------|
| SplaTAM | Real-time SLAM | 25.14 | - | - | 0.074 | 9.067 | 6,283,744 |
| Photo-SLAM | Real-time SLAM | 22.11 | - | - | 11.14 | 0.482 | 80,502 |
| MemGS | Real-time SLAM | 26.489 | - | - | 10.289 | 0.587 | 40,477 |
| **Ours (A+B)** | **Real-time SLAM** | **26.736** | **-** | **-** | **8.926** | **1.956** | **32,156** |

### Scene 3: fr3_office
| Algorithm | Type | PSNR ↑ | SSIM ↑ | LPIPS ↓ | FPS ↑ | Mem(GB) | Points ↓ |
|-----------|------|--------|--------|---------|-------|---------|----------|
| SplaTAM | Real-time SLAM | 21.680 | - | - | 0.217 | 3.276 | 802,888 |
| Photo-SLAM | Real-time SLAM | 19.85 | - | - | 10.05 | 1.196 | 62,512 |
| MemGS | Real-time SLAM | 24.375 | - | - | 9.124 | 1.709 | 52,076 |
| **Ours (A+B)** | **Real-time SLAM** | **25.482** | **-** | **-** | **9.371** | **11.971** | **69,945** |

> **Note**: `SSIM` / `LPIPS` metrics are in progress and will be updated.  
> `Mem` = Peak GPU memory usage during tracking/mapping (GB).  
> `Points` = Final Gaussian point count after convergence.