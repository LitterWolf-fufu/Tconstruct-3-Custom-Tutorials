# 语法

> 一些语法和有关语法的链接，方便理解

 ***

# 原料

## Ingredient

原版配方输入

### 键名

* `item` ([item](https://zh.minecraft.wiki/w/Java%E7%89%88%E6%95%B0%E6%8D%AE%E5%80%BC#%E7%89%A9%E5%93%81)): 表示一种物品，不能与`tag`并存
* `tag` ([tag](https://zh.minecraft.wiki/w/%E6%A0%87%E7%AD%BE#%E7%89%A9%E5%93%81%E6%A0%87%E7%AD%BE)): 表示一种标签物品，不能与`item`并存

## FluidIngredient

一个液体配方输入

### 键名

* `name` (string): 液体命名空间，不能与`tag`并存
* `tag` (string): 液体标签命名空间，不能与`name`并存
* `amount` (integer): 液体量(mB)

### 例

114mB的熔融金(tconstruct:molten_gold):

```json
"fluid": {
  "name": "tconstruct:molten_gold",
  "amount": 114
}
```

1000mB的水(minecraft:water)或500mB的蒸汽类型流体(forge:steam)

```json
"fluid": [
  {
    "name": "minecraft:water",
    "amount": 1000
  },
  {
    "tag": "forge:steam",
    "amount": 500
  }
]
```

## ItemOutput

配方输出物品或物品标签

### 键名

* `item` (string): 物品命名空间，不能与`tag`并存
* `tag` (string): 物品命标签名空间，不能与`item`并存
* `count` (integer): 物品数量，默认为 1
* `nbt` ([nbt](https://zh.minecraft.wiki/w/NBT)) 物品NBT

### 例

输出一个皮革(minecraft:leather)

```json
"result": "minecraft:leather"
```

输出一个燧石(minecraft:flint)
```json
"result": {
  "item": "minecraft:flint",
}
```

## FluidStack

流体格式

### 键名

* `fluid` (string): 流体命名空间
* `amount` (integer): 流体量(mB)

### 例

1000mB的融化玻璃流体(tconstruct:molten_glass)

```json
"result": {
    "amount": 1000,
    "fluid": "tconstruct:molten_glass"
  },
```

 ***

# 命名空间ID

## MaterialID

在`data/ModID/tinkering/materials/`目录下的`definition/`&`stats/`&`traits/`目录中都存在正确被定义的`ID.json`文件，则该材料的命名空间为`"ModID":"ID"`

# 功能交互

## 部件制造

工具材料在[部件制造台](https://www.mcmod.cn/item/636855.html)上制造部件

## 工具组装

部件在[工匠站](https://www.mcmod.cn/item/636877.html)/[工匠砧](https://www.mcmod.cn/item/636920.html)上进行组装

## 工具修复

工具在[工匠站](https://www.mcmod.cn/item/636877.html)/[工匠砧](https://www.mcmod.cn/item/636920.html)上进行修理

## 部件浇筑