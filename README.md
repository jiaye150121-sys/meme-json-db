# meme-json-db

13 个表情包的公开 JSON 检索库。

## 文件

- `catalog.json`：完整条目（分类、情绪、标签、角色、使用场景、`search_text`、文件哈希）
- `search_index.json`：精简检索索引
- `images/`：原图

## 怎么检索

```bash
# 按关键词扫 search_text / tags
jq '.items[] | select(.search_text | contains("困惑")) | {id,title,file}' catalog.json

# 按分类
jq '.indexes.by_category["困惑"]' catalog.json
```

## 分类一览

| 分类 | 数量相关条目见 indexes.by_category |
| --- | --- |
- `假装听懂` → meme_02
- `像素糊` → meme_05
- `冷淡` → meme_07
- `动漫` → meme_09, meme_13
- `动物` → meme_11, meme_12
- `发呆` → meme_11
- `可爱` → meme_12
- `吐槽` → meme_13
- `呆住` → meme_04
- `困惑` → meme_01, meme_02
- `委屈` → meme_03
- `小孩` → meme_10
- `崩溃` → meme_10
- `应付不来` → meme_10
- `思考` → meme_09
- `怪笑` → meme_05
- `抽象` → meme_05
- `无奈` → meme_13
- `无语` → meme_04, meme_07
- `没听清` → meme_01
- `熊猫头` → meme_08
- `玩梗` → meme_06, meme_12
- `破防` → meme_08
- `社交` → meme_01, meme_02, meme_03
- `空白` → meme_04, meme_11
- `算计` → meme_09
- `缓冲中` → meme_01
- `自信` → meme_06
- `苦笑` → meme_08
- `被骂` → meme_03
- `装逼` → meme_06
- `面瘫` → meme_07

## 条目速览

- **meme_01** `01_buffering_friend_said.jpg` — 朋友说了几遍，还没听清的我 — 分类: 困惑, 没听清, 缓冲中, 社交
- **meme_02** `02_pretend_understood.jpg` — 然后假装听懂了belike — 分类: 假装听懂, 困惑, 社交
- **meme_03** `03_scolded_by_friend.jpg` — 被朋友骂了的我 — 分类: 被骂, 委屈, 社交
- **meme_04** `04_blank_stare.jpg` — 空白凝视 — 分类: 空白, 呆住, 无语
- **meme_05** `05_pixel_smile.jpg` — 糊脸怪笑 — 分类: 怪笑, 抽象, 像素糊
- **meme_06** `06_uncle_can_fly.jpg` — 别闹，叔叔会飞 — 分类: 装逼, 玩梗, 自信
- **meme_07** `07_deadpan_girl.jpg` — 面瘫少女 — 分类: 面瘫, 无语, 冷淡
- **meme_08** `08_laugh_cry.jpg` — 笑着流泪 — 分类: 苦笑, 破防, 熊猫头
- **meme_09** `09_light_thinking.jpg` — 夜神月思考 — 分类: 思考, 算计, 动漫
- **meme_10** `10_cant_cope_kid.jpg` — 我无法应对 — 分类: 崩溃, 应付不来, 小孩
- **meme_11** `11_yellow_dog_blank.jpg` — 黄狗发呆 — 分类: 发呆, 空白, 动物
- **meme_12** `12_watermelon_dog.jpg` — 西瓜头盔狗 — 分类: 可爱, 玩梗, 动物
- **meme_13** `13_light_old_feng.jpg` — 哎呦我滴个老冯子呀 — 分类: 无奈, 吐槽, 动漫
