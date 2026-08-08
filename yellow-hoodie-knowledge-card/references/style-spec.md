# Visual System

## Character lock

Use one recurring original mascot with stable identity across every panel:

- sunny, warm East Asian boy/young man with a youthful rounded face, bright small dark eyes, and a tiny nose; resting expression is friendly, while mouth, eyebrows, gaze, and head angle change naturally with the scene;
- short tousled charcoal-black hair with a few irregular spikes, no facial hair;
- mustard-yellow pullover hoodie with black drawstrings, white shirt visible only when composition needs it;
- optional dark gray over-ear headphones resting around the neck in the hero scene only;
- simplified body proportions and natural small hands; posture ranges from leaning in with curiosity to focused work, thoughtful comparison, determined action, relief, or open celebration;
- drawn consistently in the same hand-inked illustration language; do not age, restyle, or change clothes between panels.

Vary expression, pose, and props to express meaning: curiosity while discovering, concentration while reading or building, concern when detecting risk, thoughtfulness while comparing, determination while acting, relief after solving, and joy when celebrating. Keep identity stable, not expression.

## Style lock

- Warm editorial educational illustration; sunny, energetic, approachable, intelligent, and human.
- Warm ivory paper background (`#F7F3EA` to `#FBF8F1`), never pure white.
- Charcoal-black hand-drawn outlines (`#252525`), about 2–3 px at 1200 px width, with subtle organic irregularity.
- Primary accent mustard yellow (`#F2B92F` to `#F6C343`).
- Secondary accent muted sage (`#8FA875`) used sparingly for plants, books, or positive markers.
- Very light warm-gray panel lines (`#DDD8CD`) and pale yellow emphasis boxes (`#FFF8E5`).
- Mostly flat colors with tiny watercolor/pencil texture; almost no shadow; no dramatic lighting.
- Rounded rectangular panels, generous gutters, orderly alignment, calm whitespace.
- Chinese typography should feel handwritten but remain highly legible: bold rounded title, clean regular body, consistent punctuation and baseline.
- Icons are simple black-line symbols with one yellow or green fill.

## Compact prompt skeleton

Adapt this scaffold into a single Chinese drawing prompt of no more than 600 Unicode characters; replace brackets with task content and exact text:

> 生成[比例与画布]中文知识卡片《[主题]》。固定角色为阳光亲和的黄衣少年，身份一致但随场景呈现[自然表情、姿态与动作序列]。采用暖白纸张、炭黑手绘线、芥末黄与鼠尾草绿。[根据内容关系选择的布局及阅读路径]。文字逐字呈现：“[标题/论点/模块/综合区/页脚]”。中文清晰、层级醒目；排除[负面约束]。

Append these negative constraints:

> No photorealism, no 3D, no glossy vector gradients, no saturated background, no busy decoration, no anime glamour, no oversized eyes, no extra fingers or limbs, no inconsistent mascot, no altered equations, no misspelled or invented Chinese text, no clipped text, no watermark, no logo.

## Quality checklist

- Identity: same hair silhouette, facial structure, hoodie color, and proportions; expressions and poses change naturally with each scene.
- Emotion: no repeated frozen smile; gaze, eyebrows, mouth, head angle, and gesture support the panel's meaning.
- Typography: every character matches the approved copy; no pseudo-Chinese glyphs.
- Hierarchy: title first, thesis second, modules third, synthesis fourth, footer last.
- Readability: body copy remains readable on a phone; no paragraph-shaped blocks.
- Composition: consistent margins and gutters; no panel feels crowded or empty.
- Semantics: each pose, icon, arrow, and chart supports a specific teaching point.
- Restraint: yellow is the focal accent; green is secondary; the page remains mostly warm ivory.
- Reference use: the result inherits the mascot and visual language without copying the reference's text or composition.
- Layout fit: the chosen composition reflects sequence, comparison, causality, hierarchy, or branching in the source.
- Prompt length: the final prompt body is no more than 600 Unicode characters.
