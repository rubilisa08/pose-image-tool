# 원하는 포즈로 이미지 만드는 도구

## 도구 설명
- 참조 사진 한 장에서 OpenPose로 사람의 자세(관절)를 추출하고, 그 자세를 ControlNet 조건으로 넣어 원하는 프롬프트에 맞는 새로운 인물/장면 이미지를 생성하는 도구입니다.

## 사용법
1. 아래 Colab 링크를 열어 실행합니다: https://colab.research.google.com/github/rubilisa08/pose-image-tool/blob/main/pose_tool.ipynb
2. 런타임 유형을 GPU(T4)로 설정한 뒤, 맨 위 셀부터 순서대로 실행합니다 (라이브러리 설치 → 모델 로드 → 사진 업로드 → 포즈 추출 → 이미지 생성).
3. 결과 이미지는 노트북 실행 중 `samples/` 폴더에 저장됩니다.

## 테스트 결과
- 포즈 1: 서있는 자세 → 프롬프트: "a girl in a flowing red dress standing on a beach at sunset" → 결과: 잘 됨
- 포즈 2: 팔다리를 벌리고 점프하는 역동적인 자세 → 프롬프트: "a professional skateboarder in mid-trick, urban street background, dynamic action photo" → 결과: 잘 됨

## 한계
-  OpenPose가 몸통·팔다리 뼈대만 추출하고 손가락 세부 동작은 반영하지 않아, 손 모양이 부자연스럽게 나오는 경우가 있습니다.
- Colab 무료 GPU 사용 시간 제약으로 controlnet_conditioning_scale, num_inference_steps 등다양한 파라미터 조합을 폭넓게 실험하지는 못했습니다.
