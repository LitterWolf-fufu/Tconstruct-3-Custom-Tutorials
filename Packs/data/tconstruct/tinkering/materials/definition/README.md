# definition-材料定义

* `craftable`:`boolean` 若为true，该材料使用[**材料配方**][recipe:material]合成与修复；若为false，该材料使用[**流体材料配方**][recipe:fluid_material]合成，使用[**材料配方**][recipe:material]修复
* `tier`:`int` 该材料的等级，一般为1~4
* `sortOrder`:`int` 该材料在同等级匠魂宝典目录中的位置
* `hidden`:`boolean` 若为true，该材料的信息不会显示在匠魂宝典中，但不影响该材料的合成等一系列操作

[recipe:material]: ../../../../../../Custom/Recipes.md/#材料配方

[recipe:fluid_material]: ../../../../../../Custom/Recipes.md/#流体材料配方

# 示例

## [clay.json](clay.json)

```json
{
    "craftable": true,
    "tier": 1,
    "sortOrder": 9,
    "hidden": false
}
```
