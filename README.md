[**BeamMusic-TTS**](https://github.com/Beam-Music/Beam-AI) : (AI 보이스 클로닝 및 음성 합성 모듈)

Spark-TTS를 기반으로 개발된 고성능 음성 합성 엔진 모듈입니다. Beam-Music 슈퍼앱의 핵심 기능인 AI 보이스 클로닝을 통해, **사용자가 원하는 노래를 특정 가수의 학습된 또는 즉석에서 복제된(zero-shot cloned) 목소리로 생성하여 들을 수 있게 합니다.** LLM(Qwen2.5)을 활용한 자연스럽고 고품질의 음성 합성을 구현하며, 중국어와 영어를 모두 지원합니다. 이 기능을 중심으로 음악 재생 중 실시간 가사 읽기, 음성 안내, 사용자 맞춤 알림 등 다양한 부가적인 음성 기반 기능을 제공하여 사용자 경험을 혁신적으로 향상시키는 역할을 합니다. 현재 Beam-Music 플레이어 환경에 최적화 및 통합 작업이 진행 중입니다.

---

# BeamMusic-TTS (Based on Spark-TTS)

## 주요 특징

- **AI 보이스 클로닝**: 원하는 가수의 목소리를 학습 또는 zero-shot 방식으로 복제하여 노래 생성
- **고품질 음성 합성**: LLM(Qwen2.5) 기반의 자연스러운 음성 합성
- **중/영어 지원**: 중국어, 영어 모두 지원
- **음성 생성 제어**: 성별, 피치, 속도 등 조절 가능
- **음악 플레이어 통합**: 실시간 가사 읽기, 음성 안내, 맞춤 알림 등 다양한 TTS 기반 부가 기능 제공

## 설치 방법

```bash
# Conda 환경 권장
conda create -n beam-music-tts -y python=3.12
conda activate beam-music-tts
pip install -r requirements.txt
```

## 모델 다운로드

```python
from huggingface_hub import snapshot_download
snapshot_download("SparkAudio/Spark-TTS-0.5B", local_dir="pretrained_models/Spark-TTS-0.5B")
```

또는

```bash
mkdir -p pretrained_models
# git-lfs 필요
git lfs install
git clone https://huggingface.co/SparkAudio/Spark-TTS-0.5B pretrained_models/Spark-TTS-0.5B
```

## 기본 사용법

```bash
cd example
bash infer.sh
```

또는

```bash
python -m cli.inference \
    --text "음성으로 변환할 텍스트" \
    --device 0 \
    --save_dir "path/to/save/audio" \
    --model_dir pretrained_models/Spark-TTS-0.5B \
    --prompt_text "프롬프트 오디오의 텍스트" \
    --prompt_speech_path "path/to/prompt_audio"
```

## Web UI 사용법

```bash
python webui.py --device 0
```

- 웹 UI에서 음성 클로닝, 음성 생성, 오디오 업로드/녹음 기능 제공

## Beam-Music 활용 예시

- 노래 재생 시 실시간 가사 음성 안내 (TTS)
- 곡 변경, 재생, 일시정지 등 주요 동작에 대한 음성 피드백
- 사용자가 선택한 가수의 목소리로 노래를 합성하여 재생 (AI 보이스 클로닝)
- 플레이리스트, 추천곡, 알림 등 사용자 맞춤 음성 안내
- 시각장애인 등 접근성 향상을 위한 음성 내비게이션

---

> 본 프로젝트는 Spark-TTS의 inference 코드를 기반으로 하며, Beam-Music의 음악 플레이어 환경에 맞게 튜닝 및 통합 중입니다.
