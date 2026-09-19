# 테스트에 쓴 프롬프트 모음

`pose_tool.ipynb`의 각 셀에서 그대로 쓰는 프롬프트입니다. Negative prompt는 모든 생성에 공통으로 적용됩니다.

- **Negative prompt (공통)**: `blurry, low quality, distorted anatomy, extra limbs`

## 기준 생성 (pose_01)

| 파일명 | 포즈 | 프롬프트 |
|---|---|---|
| `output_01.png` | pose_01 | `a girl in a flowing red dress standing on a beach at sunset` |

## 실험 A — 같은 포즈(pose_01), 다른 프롬프트

| 파일명 | 프롬프트 |
|---|---|
| `expA_samepose_prompt1.png` | `a knight in shining armor standing in a medieval castle courtyard, dramatic lighting` |
| `expA_samepose_prompt2.png` | `a ballet dancer in a white tutu on a theater stage, spotlight, soft focus background` |
| `expA_samepose_prompt3.png` | `a robot made of chrome metal standing in a futuristic city street at night, neon lights` |

## 실험 B — 같은 프롬프트, 다른 포즈(pose_01 vs pose_02)

| 파일명 | 포즈 | 프롬프트 |
|---|---|---|
| `expB_samepromt_pose01.png` | pose_01 (서있는 자세) | `a professional skateboarder in mid-trick, urban street background, dynamic action photo` |
| `output_02.png` | pose_02 (팔다리를 벌리고 점프하는 자세) | `a professional skateboarder in mid-trick, urban street background, dynamic action photo` |

## 파라미터

- `controlnet_conditioning_scale`: 1.0
- `num_inference_steps`: 25
- `guidance_scale`: 7.5
