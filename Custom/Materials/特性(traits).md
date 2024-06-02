# 材料特性（traits）

> 材料特性定义**文件路径`data/ModID/tinkering/materials/tratis/ID.json`**

## 键

- `defualt` (数组): 默认特性，该材料所有可制作的[**工具部件**](#一些补充)拥有的特性

> 包含一个或多个特性对象(object):
>
> > - `name` ([traitID](../../Gammers.md/#traitid)): 特性名称，必须与`level`同时存在
> > - `level` (integer): 特性等级，必须与`name`同时存在

- `perStat` (对象): 指定特性，该材料指定可制作的部件拥有的特性

> - `tconstruct:head` (数组): 代表**头部**部件，包含一个或多个特性对象(object)
> - `tconstruct:handle` (数组): 代表**手柄**部件，包含一个或多个特性对象(object)
> - `tconstruct:binding` (数组): 代表**绑定结**部件，包含一个或多个特性对象(object) _在 1.19.2 版本以下应为`tconstruct:extra`_
> - `tconstruct:limb` (数组): 代表**弓臂**部件，包含一个或多个特性对象(object)
> - `tconstruct:grip` (数组): 代表**弓把**部件，包含一个或多个特性对象(object)
> - `tconstruct:bowstring` (数组): 代表**弓弦**部件，包含一个或多个特性对象(object)
> - `tconstruct:armor` (数组) 代表[**盔甲部件**](#一些补充)，包含一个或多个特性对象(object)

### 一些补充

工具部件： 头部、手柄、绑定结、弓臂、弓把、弓弦

盔甲部件： 头盔镶板、胸甲镶板、护腿镶板、靴子镶板、盾牌镶板、夹板、盾牌基底

## 例

_摘自钴(tconstruct:cobalt)的材料特性文件_。该材料的所有**工具部件**具有等级为 1 的轻便(tconstruct:lightweight)特性；该工具材料的**盔甲部件**具有等级为 1 的近战保护(tconstruct:melee_protection)特性

```json
{
  "default": [
    {
      "level": 1,
      "name": "tconstruct:lightweight"
    }
  ],
  "perStat": {
    "tconstruct:armor": [
      {
        "level": 1,
        "name": "tconstruct:melee_protection"
      }
    ]
  }
}
```

_摘自黏木(tconstruct:slimewood)的材料特性文件_。该材料的所有**工具部件**具有等级为 1 的**蔓生**和等级为 1 的**黏液覆层**

```json
{
  "default": [
    {
      "level": 1,
      "name": "tconstruct:overgrowth"
    },
    {
      "level": 1,
      "name": "tconstruct:overslime"
    }
  ]
}
```
