# Parse Chinese Number

A simple but powerful module converting Chinese numeral into number and vice versa.

```javascript
import { parseChineseNumber } from "parse-chinese-number";

parseChineseNumber("七點二一"); // 7.21
parseChineseNumber("點三"); // 0.3
parseChineseNumber("負六"); // -6
parseChineseNumber("萬五"); // 15000
parseChineseNumber("三億五千萬"); // 350000000
```

```javascript
import { toChineseNumber } from "parse-chinese-number";

toChineseNumber(1234); // "一千二百三十四"
toChineseNumber(-654321.1234); // "負六十五萬四千三百二十一點一二三四"
toChineseNumber(2300450607800); // "二兆三千零四億五千零六十萬七千八百"
```

## Demo

Please visit [https://tommyinb.github.io/parse-chinese-number/](https://tommyinb.github.io/parse-chinese-number/)

## Variants

Chinese variants are supported. For example, "一" and "壹" are inter-changeable.

```javascript
parseChineseNumber("兩万參仟肆佰伍十陸"); // 23456
parseChineseNumber("拾四亿"); // 14_0000_0000
```

```javascript
toChineseNumber(150000000, Style.Big, Script.Traditional); // "壹億伍仟萬"
toChineseNumber(150000000, Style.Big, Script.Simplified); // "壹亿伍仟万"
toChineseNumber(150000000, Style.Small, Script.Traditional); // "一億五千萬"
toChineseNumber(150000000, Style.Small, Script.Simplified); // "一亿五千万"
```

| Character | Variants                  |
| --------- | ------------------------- |
| 一        | 壹, 乙, 1, １             |
| 二        | 貳, 貮, 贰, 兩, 两, 2, ２ |
| 三        | 參, 叁, 参, 叄, 3, ３     |
| 四        | 肆, 4, ４                 |
| 五        | 伍, 5, ５                 |
| 六        | 陸, 陆, 6, ６             |
| 七        | 柒, 7, ７                 |
| 八        | 捌, 8, ８                 |
| 九        | 玖, 9, ９                 |
| 零        | 〇, 0, ０                 |
| 十        | 拾                        |
| 百        | 佰                        |
| 千        | 仟                        |
| 萬        | 万                        |
| 億        | 亿                        |

## Big Number

The biggest unit is **垓** which represents 1_0000_0000_0000_0000_0000.

Please be noted that this unit is a lot larger than _MAX_SAFE_INTEGER_, 9007_1992_5474_0991.

| Unit | Value                       |
| ---- | --------------------------- |
| 萬   | 10,000                      |
| 億   | 100,000,000                 |
| 兆   | 1,000,000,000,000           |
| 京   | 10,000,000,000,000,000      |
| 垓   | 100,000,000,000,000,000,000 |

In fact, value starting from **京** should be considered imprecise.
