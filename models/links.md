# 🔗 관련 모델 GitHub 링크 모음

이 파일에는 MCP를 통해 검색할 수 있는 주요 AI 모델들의 GitHub 링크가 정리되어 있습니다.

## 🖼️ Vision Transformer 모델들

### Official Implementations

#### 1. Google Research - Vision Transformer
- **Repository**: https://github.com/google-research/vision_transformer
- **Paper**: "An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale"
- **Conference**: ICLR 2021
- **Language**: Python (JAX/Flax)
- **Stars**: 9.8k+
- **License**: Apache 2.0

```bash
# Clone command
git clone https://github.com/google-research/vision_transformer.git
```

#### 2. Microsoft - Swin Transformer
- **Repository**: https://github.com/microsoft/Swin-Transformer
- **Paper**: "Swin Transformer: Hierarchical Vision Transformer using Shifted Windows"
- **Conference**: ICCV 2021
- **Language**: Python (PyTorch)
- **Stars**: 13.1k+
- **License**: MIT

```bash
# Clone command
git clone https://github.com/microsoft/Swin-Transformer.git
```

#### 3. Facebook Research - DeiT
- **Repository**: https://github.com/facebookresearch/deit
- **Paper**: "Training data-efficient image transformers & distillation through attention"
- **Conference**: ICML 2021
- **Language**: Python (PyTorch)
- **Stars**: 3.9k+
- **License**: Apache 2.0

```bash
# Clone command
git clone https://github.com/facebookresearch/deit.git
```

#### 4. Microsoft - CSWin Transformer
- **Repository**: https://github.com/microsoft/CSWin-Transformer
- **Paper**: "CSWin Transformer: A General Vision Transformer Backbone with Cross-Shaped Windows"
- **Conference**: CVPR 2022
- **Language**: Python (PyTorch)
- **Stars**: 450+
- **License**: MIT

```bash
# Clone command
git clone https://github.com/microsoft/CSWin-Transformer.git
```

### Community Implementations

#### 5. HuggingFace Transformers ViT
- **Repository**: https://github.com/huggingface/transformers
- **Documentation**: https://huggingface.co/docs/transformers/model_doc/vit
- **Pre-trained Models**: 100+ 개
- **Language**: Python (PyTorch/TensorFlow)
- **Stars**: 132k+

#### 6. PyTorch Image Models (timm)
- **Repository**: https://github.com/huggingface/pytorch-image-models
- **ViT Variants**: 50+ 개 구현
- **Language**: Python (PyTorch)
- **Stars**: 31k+

## 📈 Time Series Anomaly Detection 모델들

### Official Implementations

#### 1. Tsinghua University - Anomaly Transformer
- **Repository**: https://github.com/thuml/Anomaly-Transformer
- **Paper**: "Anomaly Transformer: Time Series Anomaly Detection with Association Discrepancy"
- **Conference**: ICLR 2022 Spotlight
- **Language**: Python (PyTorch)
- **Stars**: 1.8k+
- **License**: MIT

```bash
# Clone command
git clone https://github.com/thuml/Anomaly-Transformer.git
```

#### 2. Tsinghua University - TimesNet
- **Repository**: https://github.com/thuml/TimesNet
- **Paper**: "TimesNet: Temporal 2D-Variation Modeling for General Time Series Analysis"
- **Conference**: ICLR 2023
- **Language**: Python (PyTorch)
- **Stars**: 1.5k+

```bash
# Clone command
git clone https://github.com/thuml/TimesNet.git
```

#### 3. Monash University - CARLA
- **Repository**: https://github.com/zahra-zamanzadeh/CARLA
- **Paper**: "CARLA: Self-supervised contrastive representation learning for time series anomaly detection"
- **Journal**: Pattern Recognition 2024
- **Language**: Python (PyTorch)
- **Stars**: 200+

```bash
# Clone command
git clone https://github.com/zahra-zamanzadeh/CARLA.git
```

### Additional Time Series Models

#### 4. Salesforce - Informer
- **Repository**: https://github.com/zhouhaoyi/Informer2020
- **Paper**: "Informer: Beyond Efficient Transformer for Long Sequence Time-Series Forecasting"
- **Conference**: AAAI 2021
- **Stars**: 6.1k+

#### 5. Time Series Library (TSLib)
- **Repository**: https://github.com/thuml/Time-Series-Library
- **Description**: 종합적인 시계열 분석 라이브러리
- **Models**: 20+ 개 SOTA 모델 포함
- **Stars**: 6.2k+

## 🛠️ 유틸리티 및 도구들

### MCP Servers

#### 1. Official MCP Servers
- **Repository**: https://github.com/modelcontextprotocol/servers
- **Description**: 공식 MCP 서버 구현체들
- **Servers**: filesystem, github, sqlite, etc.

#### 2. Community MCP Servers
- **Smithery**: https://github.com/smithery-ai/smithery
- **Various MCP Implementations**: https://github.com/topics/mcp-server

### Benchmark Datasets

#### 1. Time Series Anomaly Detection Datasets
- **Repository**: https://github.com/TheDatumOrg/TSB-UAD
- **Description**: 시계열 이상 탐지 벤치마크
- **Datasets**: 15+ 개 데이터셋

#### 2. Computer Vision Datasets
- **ImageNet**: https://github.com/pytorch/examples/tree/main/imagenet
- **CIFAR**: https://github.com/keras-team/keras/tree/master/keras/datasets

## 📚 관련 논문 검색 링크

### Papers with Code 링크
- **Image Classification**: https://paperswithcode.com/task/image-classification
- **Time Series Anomaly Detection**: https://paperswithcode.com/task/time-series-anomaly-detection
- **Vision Transformer**: https://paperswithcode.com/method/vision-transformer

### ArXiv 검색 링크
- **Vision Transformer**: https://arxiv.org/search/?query=vision+transformer&searchtype=all
- **Time Series Anomaly Detection**: https://arxiv.org/search/?query=time+series+anomaly+detection&searchtype=all
- **Transformer Computer Vision**: https://arxiv.org/search/?query=transformer+computer+vision&searchtype=all

## 🚀 Quick Start Commands

### 모든 모델 한번에 클론하기
```bash
#!/bin/bash
# create_model_collection.sh

mkdir -p models/vision-transformers
mkdir -p models/time-series
mkdir -p models/utilities

# Vision Transformer models
cd models/vision-transformers
git clone https://github.com/google-research/vision_transformer.git
git clone https://github.com/microsoft/Swin-Transformer.git
git clone https://github.com/facebookresearch/deit.git
git clone https://github.com/microsoft/CSWin-Transformer.git

# Time series models
cd ../time-series
git clone https://github.com/thuml/Anomaly-Transformer.git
git clone https://github.com/thuml/TimesNet.git
git clone https://github.com/zahra-zamanzadeh/CARLA.git
git clone https://github.com/thuml/Time-Series-Library.git

# Utilities
cd ../utilities
git clone https://github.com/huggingface/transformers.git
git clone https://github.com/huggingface/pytorch-image-models.git

echo "✅ All models cloned successfully!"
```

### 서브모듈로 추가하기
```bash
# Vision Transformers as submodules
git submodule add https://github.com/google-research/vision_transformer.git models/vision_transformer
git submodule add https://github.com/microsoft/Swin-Transformer.git models/swin_transformer
git submodule add https://github.com/facebookresearch/deit.git models/deit

# Time Series models as submodules  
git submodule add https://github.com/thuml/Anomaly-Transformer.git models/anomaly_transformer
git submodule add https://github.com/thuml/TimesNet.git models/timesnet
git submodule add https://github.com/zahra-zamanzadeh/CARLA.git models/carla

# Initialize and update submodules
git submodule init
git submodule update
```

---

💡 **Tip**: 이 링크들을 통해 최신 모델들을 직접 다운로드하거나, MCP 논문 검색 서버를 사용하여 더 많은 관련 연구를 찾아보세요!