# DMF-Net: Dual-Modal Fusion Network for MRI/PET Multimodal Brain Region Segmentation




## 📋 Overview

**DMF-Net** is a 3D deep neural network designed for MRI/PET multimodal brain region segmentation. The model features a **heterogeneous dual-encoder architecture** that separately captures fine-grained anatomical features from MRI and global functional information from PET, integrated through a bidirectional **Dynamic Feature Fusion (DFF)** module for adaptive cross-modal interaction.

### Key Highlights

- 🧠 **Heterogeneous Dual-Encoder**: MRI encoder with SE attention + PET encoder with Mamba modules for modality-specific modeling
- 🔄 **Bidirectional DFF Module**: Adaptive cross-modal feature fusion in both channel and spatial dimensions
- 📐 **Multi-Scale Feature Interaction**: Progressive fusion across multiple encoder levels
- 🏥 **Clinical-Grade Dataset**: 328 subjects with PET/MR brain imaging data + 23 independent external test samples

---

---

## 🔧 Preprocessing Pipeline

1. **Rigid Registration**: FSL FLIRT — align PET to individual MRI space
2. **Non-linear Registration**: FSL FNIRT — register MRI to MNI152 standard space
3. **Spatial Standardization**: Unified image matrix of **128 × 128 × 128**
4. **Label Generation**: FreeSurfer `recon-all` → 44 brain regions in individual space → transform to standard space
5. **One-hot Encoding**: Masks converted from `128×128×128` to `44×128×128×128` multi-channel format

---

## 🚀 Getting Started

### Requirements

- Python ≥ 3.8
- PyTorch ≥ 1.10
- CUDA ≥ 11.3
- FSL (for preprocessing)
- FreeSurfer (for label generation)


---

## 📖 Citation

If you find this work useful, please cite:

```bibtex
@article{dmf-net2025,
  title={DMF-Net: Dual-Modal Fusion Network for MRI/PET Multimodal Brain Region Segmentation},
  author={},
  journal={},
  year={2025},
  note={Under review}
}
```

---

## ⚖️ License

This project is released under the [MIT License](LICENSE).

---

## 🙏 Acknowledgements

- Data provided by Chinese PLA General Hospital
- Preprocessing tools: [FSL](https://fsl.fmrib.ox.ac.uk/), [FreeSurfer](https://surfer.nmr.mgh.harvard.edu/)
- Built with [PyTorch](https://pytorch.org/)

---
