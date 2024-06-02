# 材料材质定义（assets）

## 键

- `color` (十六进制颜色): 定义材料语言文件的材料名称的显示颜色
- `fallbacks` (数组): (可选)定义材料材质的质感，一种材料可以拥有多种质感，不同的质感在**大板**部件上区分更明显
  > - `metal` 金属
  > - `wood` 木
  > - `crystal` 水晶
  > - `bone` 骨头
  > - `slime_metal` 黏液覆层金属
  > - `rock` 岩石
  > - `stick` 棍
  > - `cloth` 布料
  > - `primitive` 简陋
  > - `vine` 藤蔓
- `generator` (对象): 生成器
  > - `ignoreMaterialStats` (布尔值): 绝大多数情况下为`false` _(匠魂没有此项为`true`的部件材质，因此我也不知道此键的含义)_
  > - `supportedStats` (数组): 生成的部件材质列表
  >   > - `tconstruct:head` 头部
  >   > - `tconstruct:handle` 手柄
  >   > - `tconstruct:binding` 绑定 \_(1.18.2 及其以下版本为`tconstruct:extra`)
  >   > - `tconstruct:reparir_kit` 修补件
  >   > - `tconstruct:limb` 弓臂
  >   > - `tconstruct:grip` 弓把
  >   > - `tconstruct:bowstring` 弓弦
  >   > - `tconstruct:armor` 盔甲模型
  >   > - `tconstruct:plating_boots` 镶板靴子
  >   > - `tconstruct:plating_chestplate` 镶板盔甲
  >   > - `tconstruct:plating_helmet` 镶板头盔
  >   > - `tconstruct:plating_leggings` 镶板护腿
  >   > - `tconstruct:plating_shield` 镶板盾牌
  >   > - `tconstruct:maille` 夹板
  >   > - `tconstruct:armor_maille` 夹板模型
  > - `transformer` (对象): 生成着色器
  >   > - `type` (字符串): 着色类型
  >   >   > - `tconstruct:recolor_sprite` 重新着色 - 绝大多数部件的着色方式
  >   >   > - `tconstruct:grey_to_sprite` 覆盖着色 - 类似皇后史莱姆(tconstruct:queen*slime)的着色方式 *具体我也没研究懂，不推荐新手使用\_
  >   > - `color_mapping` (对象) 颜色映射，仅在同级的`type`为`tconstruct:recolor_sprite`可用
  >   >   > - `type` (字符串): `tconstruct:gery_to_sprite`
  >   >   > - `palette` (数组): 调色板，包含一个或多个颜色覆盖的对象
  >   >   >   > - `color` (十六进制颜色): 覆盖的颜色
  >   >   >   > - `grey` (整数): 被覆盖的灰度值（匠魂材质所有可被覆盖的灰度值:0、63、102、140、178、216、255）
  >   > - `palette` (数组): 调色板，仅在同级的`type`为`tconstruct:grey_to_sprite`可用，包含一个或多个颜色覆盖的对象
  >   >   > - `color` (十六进制颜色): 覆盖的颜色
  >   >   > - `grey` (整数): 被覆盖的灰度值（匠魂材质所有可被覆盖的灰度值:0、63、102、140、178、216、255）
  >   >   > - `path` (字符串): 覆盖着色材质的路径
- `luminosity` (整数) 光度

  ***

我知道你可能看不懂上面写的什么，为此我提供了一个[文件](#文件)可以让新手快速上手~

---

## 示例

木材料(tconstruct:wood)的材料材质文件

```json
{
  "color": "FF876627",
  "fallbacks": ["wood", "stick", "primitive"],
  "generator": {
    "ignoreMaterialStats": false,
    "supportedStats": [
      "tconstruct:head",
      "tconstruct:handle",
      "tconstruct:binding",
      "tconstruct:repair_kit",
      "tconstruct:limb",
      "tconstruct:grip",
      "tconstruct:shield_core"
    ],
    "transformer": {
      "type": "tconstruct:recolor_sprite",
      "color_mapping": {
        "type": "tconstrut:grey_to_color",
        "palette": [
          {
            "color": "FF000000",
            "grey": 0
          },
          {
            "color": "FF281E0B",
            "grey": 63
          },
          {
            "color": "FF493615",
            "grey": 102
          },
          {
            "color": "FF584014",
            "grey": 140
          },
          {
            "color": "FF684E1E",
            "grey": 178
          },
          {
            "color": "FF785A22",
            "grey": 216
          },
          {
            "color": "FF896727",
            "grey": 255
          }
        ]
      }
    }
  },
  "luminosity": 0
}
```

史莱姆皇后材料(tconstruct:queen_slime)的材料材质文件

```json
{
  "color": "FF809912",
  "fallbacks": ["slime_metal", "metal"],
  "generator": {
    "ignoreMaterialStats": false,
    "supportedStats": [
      "tconstruct:head",
      "tconstruct:handle",
      "tconstruct:binding",
      "tconstruct:repair_kit",
      "tconstruct:limb",
      "tconstruct:grip",
      "tconstruct:armor_plating",
      "tconstruct:plating_boots",
      "tconstruct:plating_leggings",
      "tconstruct:plating_chestplate",
      "tconstruct:plating_helmet",
      "tconstruct:plating_shield",
      "tconstruct:maille",
      "tconstruct:armor_maille"
    ],
    "transformer": {
      "type": "tconstruct:grey_to_sprite",
      "palette": [
        {
          "color": "FF000000",
          "grey": 0
        },
        {
          "color": "FFC8C8C8",
          "grey": 63,
          "path": "tconstruct:item/materials/generator/queens_slime_border"
        },
        {
          "grey": 102,
          "path": "tconstruct:item/materials/generator/queens_slime_border"
        },
        {
          "color": "FFE1E1E1",
          "grey": 140,
          "path": "tconstruct:item/materials/generator/queens_slime"
        },
        {
          "grey": 178,
          "path": "tconstruct:item/materials/generator/queens_slime"
        },
        {
          "color": "FFE1E1E1",
          "grey": 216,
          "path": "tconstruct:item/materials/generator/queens_slime_highlight"
        },
        {
          "grey": 255,
          "path": "tconstruct:item/materials/generator/queens_slime_highlight"
        }
      ]
    }
  },
  "luminosity": 9
}
```

---

## 文件

```json
{
  "color": "<材料文本颜色(16进制颜色代码)>",
  "fallbacks": ["<部件的质感(可以不写, 但是记得把我删了)>"],
  "generator": {
    "ignoreMaterialStats": false,
    "supportedStats": [
      "<需要输出的部件, 我这里帮你把所有部件的都写了, 把不需要的删掉就行(记得把我也删了)>",
      "tconstruct:head",
      "tconstruct:handle",
      "tconstruct:binding",
      "tconstruct:repair_kit",
      "tconstruct:limb",
      "tconstruct:grip",
      "tconstruct:armor_plating",
      "tconstruct:plating_boots",
      "tconstruct:plating_leggings",
      "tconstruct:plating_chestplate",
      "tconstruct:plating_helmet",
      "tconstruct:plating_shield",
      "tconstruct:maille",
      "tconstruct:armor_maille"
    ],
    "transformer": {
      "type": "tconstruct:recolor_sprite",
      "color_mapping": {
        "type": "tconstrut:grey_to_color",
        "palette": [
          { "color": "<16进制颜色代码> 这是最深色的", "grey": 0 },
          { "color": "<16进制颜色代码>", "grey": 63 },
          { "color": "<16进制颜色代码>", "grey": 102 },
          { "color": "<16进制颜色代码>", "grey": 140 },
          { "color": "<16进制颜色代码>", "grey": 178 },
          { "color": "<16进制颜色代码>", "grey": 216 },
          { "color": "<16进制颜色代码> 这是最浅色的", "grey": 255 }
        ]
      }
    }
  },
  "luminosity": 0
}
```
