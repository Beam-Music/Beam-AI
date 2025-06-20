<div align="center">

<h1>AI 보이스 변환 WebUI (RVC)</h1>
<strong>For Beam Music</strong><br><br>
VITS 기반의 사용하기 쉬운 음성 변환 프레임워크<br><br>

[![madewithlove](https://img.shields.io/badge/made_with-%E2%9D%A4-red?style=for-the-badge&labelColor=orange)](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI)

<img src="https://counter.seku.su/cmoe?name=rvc&theme=r34" /><br>

[![Open In Colab](https://img.shields.io/badge/Colab-F9AB00?style=for-the-badge&logo=googlecolab&color=525252)](https://colab.research.google.com/github/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/blob/main/Retrieval_based_Voice_Conversion_WebUI.ipynb)
[![Licence](https://img.shields.io/badge/LICENSE-MIT-green.svg?style=for-the-badge)](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/blob/main/LICENSE)
[![Huggingface](https://img.shields.io/badge/🤗%20-Spaces-yellow.svg?style=for-the-badge)](https://huggingface.co/lj1995/VoiceConversionWebUI/tree/main/)

[![Discord](https://img.shields.io/badge/RVC%20Developers-Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/HcsmBBGyVk)

[**업데이트 로그**](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/blob/main/docs/Changelog_CN.md) | [**자주 묻는 질문(FAQ)**](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/wiki/%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94) | [**AutoDL을 이용한 저비용 AI 가수 훈련**](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/wiki/Autodl%E8%AE%AD%E7%BB%83RVC%C2%B7AI%E6%AD%8C%E6%89%8B%E6%95%99%E7%A8%8B) | [**비교 실험 기록**](<https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/wiki/Autodl%E8%AE%AD%E7%BB%83RVC%C2%B7AI%E6%AD%8C%E6%89%8B%E6%95%99%E7%A8%8B](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/wiki/%E5%AF%B9%E7%85%A7%E5%AE%9E%E9%AA%8C%C2%B7%E5%AE%9E%E9%AA%8C%E8%AE%B0%E5%BD%95)>) | [**온라인 데모**](https://modelscope.cn/studios/FlowerCry/RVCv2demo)

[**English**](./docs/en/README.en.md) | [**中文简体**](./README.md) | [**日本語**](./docs/jp/README.ja.md) | [**한국어**](./docs/kr/README.ko.md) ([**韓國語**](./docs/kr/README.ko.han.md)) | [**Français**](./docs/fr/README.fr.md) | [**Türkçe**](./docs/tr/README.tr.md) | [**Português**](./docs/pt/README.pt.md)

</div>

> 베이스 모델은 약 50시간 분량의 고품질 오픈소스 VCTK 데이터셋으로 학습되었으며, 저작권 문제가 없으니 안심하고 사용하세요.

> 더 커진 파라미터와 데이터, 향상된 성능, 비슷한 추론 속도, 더 적은 훈련 데이터 요구량을 갖춘 RVCv3 베이스 모델을 기대해주세요.

<table>
   <tr>
		<td align="center">학습 및 추론 인터페이스</td>
		<td align="center">실시간 음성 변환 인터페이스</td>
	</tr>
  <tr>
		<td align="center"><img src="https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/assets/129054828/092e5c12-0d49-4168-a590-0b0ef6a4f630"></td>
    <td align="center"><img src="https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/assets/129054828/730b4114-8805-44a1-ab1a-04668f3c30a6"></td>
	</tr>
	<tr>
		<td align="center">go-web.bat</td>
		<td align="center">go-realtime-gui.bat</td>
	</tr>
  <tr>
    <td align="center">원하는 작업을 자유롭게 선택할 수 있습니다.</td>
		<td align="center">End-to-end 170ms 지연 시간을 구현했습니다. ASIO 입출력 장치를 사용하면 90ms까지 단축 가능하지만, 하드웨어 드라이버 지원에 크게 의존합니다.</td>
	</tr>
</table>

<table>
   <tr>
		<td align="center">학습 및 추론 인터페이스</td>
		<td align="center">실시간 음성 변환 인터페이스</td>
	</tr>
  <tr>
		<td align="center"><img src="https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/assets/129054828/092e5c12-0d49-4168-a590-0b0ef6a4f630"></td>
    <td align="center"><img src="https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/assets/129054828/730b4114-8805-44a1-ab1a-04668f3c30a6"></td>
	</tr>
	<tr>
		<td align="center">go-web.bat</td>
		<td align="center">go-realtime-gui.bat</td>
	</tr>
  <tr>
    <td align="center">원하는 작업을 자유롭게 선택할 수 있습니다.</td>
		<td align="center">End-to-end 170ms 지연 시간을 구현했습니다. ASIO 입출력 장치를 사용하면 90ms까지 단축 가능하지만, 하드웨어 드라이버 지원에 크게 의존합니다.</td>
	</tr>
</table>

## 소개

이 저장소는 다음과 같은 특징을 가집니다

- Top-1 검색을 사용하여 입력 소스의 특징을 훈련 세트의 특징으로 대체하여 음색 유출을 방지합니다.
- 비교적 성능이 낮은 그래픽카드에서도 빠르게 훈련할 수 있습니다.
- 적은 양의 데이터로도 좋은 결과를 얻을 수 있습니다 (최소 10분 분량의 노이즈가 적은 음성 데이터 수집 권장).
- 모델 융합(체크포인트 처리 탭의 ckpt-merge 기능)을 통해 음색을 변경할 수 있습니다.
- 사용하기 쉬운 웹 인터페이스
- UVR5 모델을 호출하여 보컬과 반주를 빠르게 분리할 수 있습니다.
- 최신 음성 피치 추출 알고리즘인 [InterSpeech2023-RMVPE](#참고 프로젝트)를 사용하여 음소거 문제를 해결합니다. 성능은 가장 좋으면서도(눈에 띄게) crepe_full보다 빠르고 리소스 사용량이 적습니다.
- AMD/Intel 그래픽카드 가속 지원

[여기](https://www.bilibili.com/video/BV1pm4y1z7Gm/)에서 데모 영상을 확인하세요!

## 환경 설정

### Windows/Linux/MacOS 등 플랫폼 공용 방법

다음 방법 중 하나를 선택하세요.

#### 1. pip를 통한 의존성 설치

1. Pytorch와 핵심 의존성을 설치합니다. 이미 설치된 경우 이 단계를 건너뜁니다. 참고: https://pytorch.org/get-started/locally/

```bash
pip install torch torchvision torchaudio
```

2. Windows 시스템 + Nvidia Ampere 아키텍처(RTX 30xx)의 경우, #21 경험에 따라 pytorch에 맞는 CUDA 버전을 지정해야 합니다.

```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu117
```

3. 자신의 그래픽카드에 맞는 의존성을 설치하세요.

- Nvidia 카드

```bash
pip install -r requirements.txt
```

- AMD/Intel 카드

```bash
pip install -r requirements-dml.txt
```

- AMD 카드 ROCM(Linux)

```bash
pip install -r requirements-amd.txt
```

- Intel 카드 IPEX(Linux)

```bash
pip install -r requirements-ipex.txt
```

#### 2. poetry를 통한 의존성 설치

Poetry 의존성 관리 도구를 설치합니다. 이미 설치된 경우 이 단계를 건너뜁니다. 참고: https://python-poetry.org/docs/#installation

```bash
curl -sSL https://install.python-poetry.org | python3 -
```

Poetry로 의존성을 설치할 때, Python은 3.7-3.10 버전을 권장합니다. 다른 버전은 llvmlite==0.39.0 설치 시 충돌이 발생할 수 있습니다.

```bash
poetry init -n
poetry env use "path to your python.exe"
poetry run pip install -r requirments.txt
```

### MacOS

`run.sh`를 통해 의존성을 설치할 수 있습니다.

```bash
sh ./run.sh
```

## 기타 사전 모델 준비

RVC는 추론 및 훈련을 위해 다른 사전 모델들이 필요합니다.

[Hugging Face space](https://huggingface.co/lj1995/VoiceConversionWebUI/tree/main/)에서 이 모델들을 다운로드할 수 있습니다.

### 1. assets 다운로드

다음은 모든 RVC 필수 사전 모델과 기타 파일 목록입니다. 'tools' 폴더에서 다운로드 스크립트를 찾을 수 있습니다.

- ./assets/hubert/hubert_base.pt

- ./assets/pretrained

- ./assets/uvr5_weights

v2 버전 모델을 사용하려면 추가로 다운로드해야 합니다.

- ./assets/pretrained_v2

### 2. ffmpeg 설치

ffmpeg와 ffprobe가 이미 설치되어 있다면 이 단계를 건너뜁니다.

#### Ubuntu/Debian 사용자

```bash
sudo apt install ffmpeg
```

#### MacOS 사용자

```bash
brew install ffmpeg
```

#### Windows 사용자

다운로드 후 루트 디렉토리에 배치하세요.

- [ffmpeg.exe](https://huggingface.co/lj1995/VoiceConversionWebUI/blob/main/ffmpeg.exe) 다운로드

- [ffprobe.exe](https://huggingface.co/lj1995/VoiceConversionWebUI/blob/main/ffprobe.exe) 다운로드

### 3. rmvpe 음성 피치 추출 알고리즘 필요 파일 다운로드

최신 RMVPE 음성 피치 추출 알고리즘을 사용하려면, 피치 추출 모델 파라미터를 다운로드하여 RVC 루트 디렉토리에 배치해야 합니다.

- [rmvpe.pt](https://huggingface.co/lj1995/VoiceConversionWebUI/blob/main/rmvpe.pt) 다운로드

#### rmvpe dml 환경 다운로드 (선택사항, AMD/Intel 카드 사용자)

- [rmvpe.onnx](https://huggingface.co/lj1995/VoiceConversionWebUI/blob/main/rmvpe.onnx) 다운로드

### 4. AMD 그래픽카드 Rocm (선택사항, Linux 전용)

AMD의 Rocm 기술을 기반으로 Linux에서 RVC를 실행하려면, 먼저 [여기](https://rocm.docs.amd.com/en/latest/deploy/linux/os-native/install.html)에서 필요한 드라이버를 설치하세요.

Arch Linux를 사용한다면, pacman을 사용하여 필요한 드라이버를 설치할 수 있습니다:

```
pacman -S rocm-hip-sdk rocm-opencl-sdk
```

일부 그래픽카드 모델(예: RX6700XT)의 경우, 다음과 같은 환경 변수를 추가로 설정해야 할 수 있습니다:

```
export ROCM_PATH=/opt/rocm
export HSA_OVERRIDE_GFX_VERSION=10.3.0
```

또한 현재 사용자가 'render' 및 'video' 사용자 그룹에 속해 있는지 확인하세요:

```
sudo usermod -aG render $USERNAME
sudo usermod -aG video $USERNAME
```

## 시작하기

### 직접 시작

다음 명령어를 사용하여 WebUI를 시작합니다.

```bash
python infer-web.py
```

이전에 Poetry를 사용하여 의존성을 설치했다면, 다음 방식으로 WebUI를 시작할 수 있습니다.

```bash
poetry run python infer-web.py
```

### 통합 패키지 사용

`RVC-beta.7z` 다운로드 및 압축 해제

#### Windows 사용자

`go-web.bat` 더블클릭

#### MacOS 사용자

```bash
sh ./run.sh
```

### IPEX 기술이 필요한 Intel 카드 사용자 (Linux 전용)

```bash
source /opt/intel/oneapi/setvars.sh
```

## 참고 프로젝트

- [ContentVec](https://github.com/auspicious3000/contentvec/)
- [VITS](https://github.com/jaywalnut310/vits)
- [HIFIGAN](https://github.com/jik876/hifi-gan)
- [Gradio](https://github.com/gradio-app/gradio)
- [FFmpeg](https://github.com/FFmpeg/FFmpeg)
- [Ultimate Vocal Remover](https://github.com/Anjok07/ultimatevocalremovergui)
- [audio-slicer](https://github.com/openvpi/audio-slicer)
- [Vocal pitch extraction:RMVPE](https://github.com/Dream-High/RMVPE)
  - The pretrained model is trained and tested by [yxlllc](https://github.com/yxlllc/RMVPE) and [RVC-Boss](https://github.com/RVC-Boss).
