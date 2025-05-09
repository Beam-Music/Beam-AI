# Beam-Music TTS (Based on Spark-TTS)

이 프로젝트는 Spark-TTS 기반의 고성능 Text-to-Speech(TTS) 엔진을 음악 플레이어(Beam-Music)에 통합하여, 음악 재생 중 실시간 안내, 가사 읽기, 음성 알림 등 다양한 TTS 기능을 제공합니다.

## 주요 특징

- **고품질 음성 합성**: LLM(Qwen2.5) 기반의 자연스러운 음성 합성
- **제로샷 보이스 클로닝**: 별도 학습 없이 다양한 화자의 목소리 복제 가능
- **중/영어 지원**: 중국어, 영어 모두 지원
- **음성 생성 제어**: 성별, 피치, 속도 등 조절 가능

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

## Beam-Music 통합 예시

- 음악 재생 중 가사 읽기
- 곡 변경/재생/정지 등 음성 안내
- 사용자 맞춤 음성 알림

---

> 본 프로젝트는 Spark-TTS의 inference 코드를 기반으로 하며, Beam-Music의 음악 플레이어 환경에 맞게 튜닝 및 통합 중입니다.
