# 🤖 관련 AI 모델들

이 폴더에는 MCP를 통해 검색할 수 있는 주요 AI 모델들의 정보와 링크가 포함되어 있습니다.

## 🔍 Vision Transformer 모델들

### 1. Original Vision Transformer (ViT)
- **Repository**: [google-research/vision_transformer](https://github.com/google-research/vision_transformer)
- **Paper**: "An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale" (ICLR 2021)
- **Performance**: ImageNet Top-1 84.0%
- **Innovation**: 순수 Transformer 아키텍처를 이미지 분류에 적용

### 2. Swin Transformer
- **Repository**: [microsoft/Swin-Transformer](https://github.com/microsoft/Swin-Transformer)
- **Paper**: "Swin Transformer: Hierarchical Vision Transformer using Shifted Windows" (ICCV 2021)
- **Performance**: ImageNet Top-1 83.5%
- **Innovation**: Shifted window 메커니즘으로 효율성 개선

### 3. DeiT (Data-efficient image Transformers)
- **Repository**: [facebookresearch/deit](https://github.com/facebookresearch/deit)
- **Paper**: "Training data-efficient image transformers & distillation through attention" (ICML 2021)
- **Performance**: ImageNet Top-1 83.1%
- **Innovation**: Knowledge distillation을 통한 효율적 학습

### 4. CSWin Transformer
- **Repository**: [microsoft/CSWin-Transformer](https://github.com/microsoft/CSWin-Transformer)
- **Paper**: "CSWin Transformer: A General Vision Transformer Backbone with Cross-Shaped Windows" (CVPR 2022)
- **Performance**: ImageNet Top-1 85.4%
- **Innovation**: Cross-shaped window attention 메커니즘

## 📈 Time Series 모델들

### 1. Anomaly Transformer
- **Repository**: [thuml/Anomaly-Transformer](https://github.com/thuml/Anomaly-Transformer)
- **Paper**: "Anomaly Transformer: Time Series Anomaly Detection with Association Discrepancy" (ICLR 2022)
- **Performance**: MSL F1-Score ~90%
- **Innovation**: Association Discrepancy for anomaly detection

### 2. TimesNet
- **Repository**: [thuml/TimesNet](https://github.com/thuml/TimesNet)
- **Paper**: "TimesNet: Temporal 2D-Variation Modeling for General Time Series Analysis" (ICLR 2023)
- **Performance**: Multiple benchmarks SOTA
- **Innovation**: 1D → 2D transformation for temporal analysis

### 3. CARLA
- **Repository**: [zahra-zamanzadeh/CARLA](https://github.com/zahra-zamanzadeh/CARLA)
- **Paper**: "CARLA: Self-supervised contrastive representation learning for time series anomaly detection" (Pattern Recognition 2024)
- **Performance**: MSL F1-Score ~95%
- **Innovation**: Self-supervised contrastive learning

## 🛠️ 설치 방법

### Quick Start
```bash
# Vision Transformer 클론
git clone https://github.com/google-research/vision_transformer.git

# Swin Transformer 클론  
git clone https://github.com/microsoft/Swin-Transformer.git

# DeiT 클론
git clone https://github.com/facebookresearch/deit.git

# Anomaly Transformer 클론
git clone https://github.com/thuml/Anomaly-Transformer.git
```

### 서브모듈로 추가하기
```bash
# 이 리포지토리에 서브모듈로 추가
git submodule add https://github.com/google-research/vision_transformer.git models/vision-transformer
git submodule add https://github.com/microsoft/Swin-Transformer.git models/swin-transformer
git submodule add https://github.com/facebookresearch/deit.git models/deit
git submodule add https://github.com/thuml/Anomaly-Transformer.git models/anomaly-transformer
```

## 📊 성능 비교

### Image Classification (ImageNet)
| Model | Top-1 Accuracy | Parameters | FLOPs | Year |
|-------|---------------|------------|-------|------|
| CSWin-T | 85.4% | 88M | 4.9G | 2022 |
| ViT-L/16 | 84.0% | 632M | 81.5G | 2021 |
| Swin-B | 83.5% | 197M | 15.4G | 2021 |
| DeiT-B | 83.1% | 86M | 17.5G | 2021 |

### Time Series Anomaly Detection (MSL)
| Model | F1-Score | Precision | Recall | Year |
|-------|----------|-----------|--------|------|
| CARLA | 95.2% | 94.8% | 95.6% | 2024 |
| TimesNet | 93.1% | 92.5% | 93.7% | 2023 |
| Anomaly-TF | 90.3% | 89.8% | 90.8% | 2022 |

## 🔗 유용한 링크

- **Papers with Code**: [Image Classification](https://paperswithcode.com/task/image-classification)
- **Papers with Code**: [Time Series Anomaly Detection](https://paperswithcode.com/task/time-series-anomaly-detection)
- **Hugging Face Models**: [Vision Transformers](https://huggingface.co/models?pipeline_tag=image-classification&sort=downloads)
- **Model Zoo**: [MMDetection](https://github.com/open-mmlab/mmdetection)

---

💡 **Tip**: MCP 논문 검색 서버를 사용하여 이 모델들에 대한 최신 정보를 실시간으로 검색할 수 있습니다!