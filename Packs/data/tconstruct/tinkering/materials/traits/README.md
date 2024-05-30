# tratis-材料特性

> 一个特性的复合标签类似于下面这样

```json5
{
    "level": 1,                     // 特性的等级
    "name": "tconstruct:hydraulic"  // 特性的命名空间
}
```

## 默认特性

> 该材料所有部件拥有的特性

`"defualt"` 键名，对应的值为一个存储特性的复合标签的列表`[...]`

```json5
{
    "defualt": [
        { "level": 1, "name": "ModID:xxx" }
        // ...
    ]
}
```

## 部件特性

> 该材料指定部件拥有的特性

`"perStat"` 键名，对应的值为一个复合标签`{...}`

```json5
{
    "perStat": {
        "tconstruct:head": [    // 头部部件
            // traits
        ],
        "tconstruct:head": [    // 手柄部件
            // traits
        ],
        "tconstruct:binding": [    // 绑定部件
            // traits
        ],
        "tconstruct:limb": [    // 弓臂部件
            // traits
        ],
        "tconstruct:grip": [    // 弓把部件
            // traits
        ],
        "tconstruct:bowstring": [    // 弓弦部件
            // traits
        ],
        "tconstruct:armor": [    // 镶板类型、夹板、护盾基底部件
            // traits
        ],
    }
}
```

# 示例

## ancient_hide - 远古兽皮

```json
{
  "default": [
    {
      "level": 1,
      "name": "tconstruct:fortune"
    }
  ],
  "perStat": {
    "tconstruct:armor": [
      {
        "level": 1,
        "name": "tconstruct:fortified"
      }
    ]
  }
}
```
