# samples/

`pose_tool.ipynb`를 Colab에서 실제로 실행해서 얻은 결과입니다.

- `pose_01.png` — 첫 번째 참조 사진(서있는 자세)에서 추출한 포즈 스켈레톤
- `output_01.png` — pose_01 + "a girl in a flowing red dress standing on a beach at sunset" 프롬프트로 생성한 결과
- `pose_02.png` — 두 번째 참조 사진(팔다리를 벌리고 점프하는 자세)에서 추출한 포즈 스켈레톤
- `output_02.png` — pose_02 + "a professional skateboarder in mid-trick, urban street background, dynamic action photo" 프롬프트로 생성한 결과
- `expA_comparison.png` — 실험 A: pose_01 고정, 프롬프트만 knight/ballet dancer/robot으로 바꿔가며 생성한 3장 비교
- `expB_comparison.png` — 실험 B: 같은 스케이트보더 프롬프트를 pose_01과 pose_02에 각각 적용한 비교 (포즈 조건이 결과에 미치는 영향을 가장 잘 보여줌)
