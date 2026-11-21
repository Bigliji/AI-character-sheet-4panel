# 四宫格角色设定图 — 提示词模板

构建提示词时以此模板为骨架。占位符共 4 处：【BG】（背景）、【LIGHT】（光调）、【RATIO】（画幅）、【PRESERVATION】（保真清单，由参考图分析结果填充）。面板定义、影棚设定、负面清单原则上逐字保留，不自行改写。

## 占位符填写规则

| 占位符 | 用户未指定时的默认值 | 说明 |
|---|---|---|
| 【BG】 | light gray seamless studio cyclorama | 背景色，跟随用户指定（冷灰/暖灰/白/黑等） |
| 【LIGHT】 | neutral daylight | 光调，跟随用户指定 |
| 【RATIO】 | square 1:1 | 画幅，跟随用户指定；9:16 竖版优先请求 1080x1920（实测可用，模型实出 1072x1920），720x1280 作兜底；2160x3840 不支持，报错 14402 时降级到同比例较小尺寸 |
| 【PRESERVATION】 | —（必填） | 参考图分析出的保真清单逐项填入：脸型、眼鼻嘴、发际线与发型、帽子款式与绣字、年龄、肤色与肤质、身材比例、服装每处细节；参考图中的道具（手机/镜子等）声明剔除 |

## 完整模板

```
Convert the uploaded character reference photo into a 4-panel character sheet, single image, 【RATIO】, 2x2 grid of four equal panels separated by thin white gutters, with a small clean label in each panel corner reading exactly: "FACE FRONT", "FACE SIDE", "BODY FRONT", "BACK".

CRITICAL PRESERVATION OVERRIDE — The uploaded photo is the ONLY design source. The exact same person appears in all four panels. Preserve EXACTLY: 【PRESERVATION】. NO beautification, NO redesign, NO style drift, NO "improving" the face. One identity across all panels. Remove 【参考图中出现的道具】 and the mirror-selfie context entirely.

PANEL 1 — TOP LEFT, FACE FRONT: head-and-shoulders close-up, face directly toward camera, calm neutral expression, eyes engaged but relaxed, hair/headwear worn exactly as in the reference.
PANEL 2 — TOP RIGHT, FACE SIDE: same head-and-shoulders scale, clean 90-degree profile view, same expression, same hair behavior.
PANEL 3 — BOTTOM LEFT, BODY FRONT: full-body standing pose, front view. IMPORTANT: the face in this panel MUST be intentionally featureless and low-detail — render it as a smooth blank skin-tone surface with NO eyes, NO nose, NO mouth, like an untextured mannequin head, reserved for later editing. Natural relaxed weight, arms relaxed at sides. Complete the outfit below the waist using the lower-body plan the user confirmed in advance (never invent one yourself), in the most neutral way consistent with the reference: 【下半身与鞋补全项——填入用户已确认的方案，如 plain dark charcoal casual trousers and plain low-top off-white sneakers】. No added accessories, no height change.
PANEL 4 — BOTTOM RIGHT, BACK: full-body standing pose, rear view — hair/headwear seen from behind, garment back seams and back neckline, same trousers, same footwear and heel height, same standing spot as PANEL 3.

STUDIO SETUP (all four panels identical): seamless 【BG】 background, single hard key light at 45 degrees camera-left, 【LIGHT】 tone, NO fill light, no set dressing, no props. Only natural contact shadows on the floor.

QUALITY: photographic character sheet for film production casting, even exposure, accurate fabric weave, matte skin, real pores, no gloss. Clean, clinical, production-use.

AVOID: no beauty-filter skin, no glossy TV-drama complexion, no idol makeup, no plastic skin, no face slimming, no enlarged eyes, no skin smoothing; no pose change between panels, no outfit change, no added accessories, no height change; no ambient color spill, no rim-light drama.
```

## 填写示例（节选）

保真清单填写示例（对应一张"奶油色棒球帽 + 米白宽松卫衣"参考图）：

> facial structure, eyes, nose, mouth shape, hairline and hairstyle (dark brown soft straight hair with wispy curtain bangs under a cream/beige six-panel baseball cap with curved brim and small cursive embroidered script on the front panel), age (late teens to early 20s), fair warm skin tone and natural skin texture (real pores, matte), slender lean body proportion and weight, and every garment detail from the reference: oversized cream/off-white long-sleeve sweatshirt, relaxed drop-shoulder cut, wide ribbed crew neckline, sleeves bunching at the wrists, soft brushed cotton fabric with natural wrinkles and visible seams

要点：每一项都来自参考图分析结果，不凭常识脑补；帽子上的绣字描述为"small cursive embroidered script"即可，不要试图在提示词里还原具体文字。
