# 前言

# <span id=材料配方>材料基础配方(material)</span>

> 材料基础配方。在部件加工台上进行，用于合成或修复部件
> 
> 若`"craftable"`为`false`则为修复和合成配方，为`true`则仅为修复配方

```json5
{
    "type": "tconstruct:material",
    "ingredient": {
        "item": "minecraft:clay_ball" // item 或 tag
    },
    "material": "tconstruct:clay",  // 输出材料的命名空间
    "needed": 1,    // 合成部件需要的基础值
    "value": 1      // 每个合成材料提供的值
}
```

# <span id=流体材料配方>材料浇筑配方(material_fluid)</span>

> 材料浇筑配方。将液体浇筑在铸模或部件上，用于合成新部件

```json5
{
    "type": "tconstruct:material_fluid",
    "fluid": {
        "amount": 250,  // 消耗液体的量(mL)
        "tag": "tconstruct:molten_clay" // 消耗液体的标签命名空间
    },
    "output": "tconstruct:brick",   // 输出材料的命名空间
    "temperature": 450  // 要求达到的温度
}
```

# <span id=材料熔炼配方>材料熔炼配方(material_melting)</span>

> 材料熔炼配方。将材料部件熔炼为液体

```json5
{
    "type": "tconstruct:material_melting",
    "input": "tconstruct:clay",         // 输入材料的命名空间
    "result": {
        "amount": 250,                  // 输出液体的量(mL)
        "fluid": "tconstruct:molten_clay" // 输出液体的命名空间
    },
    "temperature": 450  // 要求达到的温度
}
```