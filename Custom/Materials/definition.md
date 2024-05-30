# definition-材料定义

> 材料定义定义**文件路径`data/ModID/tinkering/materials/definition/ID.json`**

## 键名

* `craftable` (boolean): 材料是否可以在[部件制作台](https://www.mcmod.cn/item/636855.html)上制作部件
* `tier` (integer): 该材料的等级，一般为1~4
* `sortOrder` (integer): 该材料在同等级匠魂宝典目录中的位置
* `hidden` (boolean): 材料是否在匠魂宝典中被隐藏

## 示例

摘自材料`tconstruct:wood.json`。可在[部件制作台](https://www.mcmod.cn/item/636855.html)上制造该材料的部件；不在匠魂宝典中隐藏；该材料在等级为1的匠魂宝典([匠魂宝典:材料与你](https://www.mcmod.cn/item/637290.html))中排列位置为0

```json
{
  "craftable": true,
  "hidden": false,
  "sortOrder": 0,
  "tier": 1
}
```