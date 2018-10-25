# utils
工作中使用的工具类

## isInteger(number)
判断number是否是整数。
```javascript 1.5
    Utils.isInteger(1); //true
    Utils.isInteger(1.1);//false
    Utils.isInteger('1');//false
```
## isString(str)
判断str是否是字符串。
```javascript 1.5
    Utils.isString('1');                //true
    Utils.isString(new String('1'));    //true
    Utils.isString(1);                  //false
```
## numberAndEnglishToCDB(str)
全角英数字转换为半角英数字（不包含全角空格）。
```javascript 1.5
    Utils.numberAndEnglishToCDB("ａｂｃｄｅｆｇｈｉｊｋｌｍｎｏｐｑｒｓｔｕｖｗｓｙｚ");//abcdefghijklmnopqrstuvwsyz
    Utils.numberAndEnglishToCDB("ＡＢＣＤＥＦＧＨＩＪＫＬＭＮＯＰＱＲＳＴＵＶＷＳＹＺ");//ABCDEFGHIJKLMNOPQRSTUVWSYZ
    Utils.numberAndEnglishToCDB("１２３４５６７８９０");//1234567890
```
## spacesToCDB(str)
字符串中的全角空格转换为半角空格。
```javascript 1.5
    Utils.spacesToCDB("ａｂｃ　ＡＢＣ　１２３");//ａｂｃ ＡＢＣ １２３
    Utils.spacesToCDB("ａｂｃ ＡＢＣ　１２３");//ａｂｃ ＡＢＣ １２３
```