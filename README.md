# 원하는 포즈로 이미지 만드는 도구

## 도구 설명
- 사람 사진 한 장을 입력하면 OpenPose로 관절(스켈레톤)을 추출하고, 그 자세를 ControlNet 조건으로 넣어 원하는 프롬프트에 맞는 새 이미지를 생성하는 도구입니다.
- 모델은 FLUX.1-dev + `InstantX/FLUX.1-dev-Controlnet-Union`(pose 모드)을 사용합니다. FLUX.2-klein 4B는 이 시점 기준 diffusers용 공식 ControlNet 포즈 체크포인트가 없어 같은 FLUX 계열의 대체 모델을 선택했습니다. 자세한 이유는 `pose_tool.ipynb` 상단 설명 셀 참고.

## 사용법
1. [Google Colab](https://colab.research.google.com/)에서 `pose_tool.ipynb`를 엽니다 (GitHub에 올린 뒤 "Open in Colab" 배지나, Colab의 File > Open notebook > GitHub 탭에서 이 저장소 경로를 붙여넣어 열 수 있습니다). 런타임은 GPU(T4 이상)로 설정합니다.
2. 셀을 위에서부터 순서대로 실행합니다: 라이브러리 설치 → 로그인(Hugging Face 토큰 필요, FLUX.1-dev 라이선스 동의 필요) → 포즈 추출용 헬퍼 정의 → OpenPose 추출 → ControlNet+FLUX 파이프라인 로드 → `generate_pose_image()` 도구 정의 → 기준 이미지 생성 → 2단계 실험(같은 포즈·다른 프롬프트, 같은 프롬프트·다른 포즈).
3. 결과 이미지는 노트북 실행 중 `samples/` 폴더에 저장됩니다 (`pose_01.png`, `output_01.png`, `pose_02.png`, `output_02.png`, `expA_*`, `expB_*`). Colab에서 만든 `samples/` 폴더 내용을 이 저장소의 `samples/` 폴더에 그대로 다운로드해서 채워 넣으면 됩니다.

## 테스트 결과
- 포즈 1: (Colab 실행 후 작성 — 어떤 자세였는지) → 프롬프트: [prompts.md](prompts.md) 참고 → 결과: (잘 됨/어긋남, 실행 후 작성)
- 포즈 2: (Colab 실행 후 작성) → 프롬프트: [prompts.md](prompts.md) 참고 → 결과: (실행 후 작성)
- 자세한 비교(같은 포즈·다른 프롬프트 vs 같은 프롬프트·다른 포즈)는 `pose_tool.ipynb` 맨 마지막 마크다운 셀에 정리되어 있습니다.

## 한계
- (Colab에서 실제로 실행한 뒤, 잘 안 된 경우와 그 이유를 짧게 적어 넣으세요. 예: 손가락 디테일이 흐트러짐, 얼굴 방향이 포즈와 다르게 나옴, controlnet_conditioning_scale이 너무 높으면 원본 인물 실루엣을 과하게 따라감 등)
