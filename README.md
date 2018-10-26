# utils.js
<p align="left">
  <a href="#">
    <img src="https://img.shields.io/badge/dev-v1.0.0-green.svg" alt="version">
  </a>
  <a href="https://opensource.org/licenses/MIT">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License MIT">
  </a>
</p>

常用工具函数。

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
## isBoolean(val)
判断是不是布尔型。
```javascript 1.5
    Utils.isBoolean(true);//true
    Utils.isBoolean(false);//true
    Utils.isBoolean(new Boolean(true));//true
    Utils.isBoolean('true');//false
```
# isDate(obj)
时间对象判断
```javascript 1.5
    Utils.isDate("20181025");//false
    Utils.isDate(new Date());//true
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

## kaNaToCDB(str)
全角カナ转换成半角カナ。
```javascript 1.5
    Utils.kaNaToCDB("アイウエオ");//ｱｲｳｴｵ
    Utils.kaNaToCDB("ｱｲｳｴｵ");//ｱｲｳｴｵ
```

## toCDB(str,isNE, isSpaces, isKaNa)
全角字符串转换成半角字符串，默认英数字，空格，カナ都准换。
* 如果isNE为false的话，不转英数字；
* 如果isSpaces为false的话，不转空格；
* 如果isKaNa为false的话，不转カナ。
```javascript 1.5
    Utils.toCDB("ａｂｃ　ＡＢＣ　１２３ アイウエオ");//abc ABC 123 ｱｲｳｴｵ
    Utils.toCDB("ａｂｃ ＡＢＣ　１２３　アイウエオ",false,false);//ａｂｃ ＡＢＣ　１２３　ｱｲｳｴｵ
```
## numberAndEnglishToDBC(str)
半角英数字转全角英数字。
```javascript 1.5
    Utils.numberAndEnglishToDBC("abcdefghijklmnopqrstuvwsyz");//ａｂｃｄｅｆｇｈｉｊｋｌｍｎｏｐｑｒｓｔｕｖｗｓｙｚ
    Utils.numberAndEnglishToDBC("ABCDEFGHIJKLMNOPQRSTUVWSYZ");//ＡＢＣＤＥＦＧＨＩＪＫＬＭＮＯＰＱＲＳＴＵＶＷＳＹＺ
    Utils.numberAndEnglishToDBC("1234567890");//１２３４５６７８９０
    Utils.numberAndEnglishToDBC("~!@#$%^&*():'<>?,./");//～！＠＃＄％＾＆＊（）：＇＜＞？，．／
```
## spacesToDBC(str)
半角空格转换成全角空格。
```javascript 1.5
    Utils.spacesToDBC("abc ABC 123");//abc　ABC　123
```
## kaNaToDBC(str)
半角カナ转换成全角カナ。
```javascript 1.5
    Utils.kaNaToDBC("ｱｲｳｴｵ");//アイウエオ
```
## toDBC(str,isNE, isSpaces, isKaNa)
半角字符串转换成全角字符串，默认英数字，空格，カナ都准换。
* 如果isNE为false的话，不转英数字；
* 如果isSpaces为false的话，不转空格；
* 如果isKaNa为false的话，不转カナ。
```javascript 1.5
    Utils.toDBC("abc ABC 123　ｱｲｳｴｵ");//ａｂｃ　ＡＢＣ　１２３　アイウエオ
    Utils.toDBC("abc ABC 123　ｱｲｳｴｵ",false,false);//abc ABC 123 アイウエオ
```
## hiRaToKaNa(str)
日语中，平假名转片假名。
```javascript 1.5
    Utils.hiRaToKaNa("あいうえお");//アイウエオ
    Utils.hiRaToKaNa("あいうえお ｱｲｳｴｵ");//アイウエオ ｱｲｳｴｵ
```
## kaNaToHiRa(str)
日语中，片假名(不包含半角片假名)转换成平假名。
```javascript 1.5
    Utils.kaNaToHiRa("アイウエオ");//あいうえお
    Utils.kaNaToHiRa("アイウエオ　ｱｲｳｴｵ　あいうえお");//あいうえお　ｱｲｳｴｵ　あいうえお
```
## kaNaToHiRaContainCDB(str)
片假名(包含半角片假名)转平假名。
```javascript 1.5
    Utils.kaNaToHiRaContainCDB("アイウエオ　ｱｲｳｴｵ　あいうえお");//あいうえお　あいうえお　あいうえお
```
## dateFormat(date, strFormat)
日期格式化。第一个参数必须是Date类型。
* MM:月(带0)
* DD:日(带0)
* hh:时(带0)
* mm:分(带0)
* ss:秒(带0)
* M:月(不带0)
* D:日(不带0)
* h:时(不带0)
* m:分(不带0)
* s:秒(不带0)
* SSS:毫秒
```javascript 1.5
    Utils.dateFormat(new Date(),'YYYY-MM-DD hh:mm:ss.SSS');//2018-10-25 18:30:25.837
    Utils.dateFormat(new Date(),'YYYY-M-D h:m:s.SSS');//2018-10-25 18:30:25.837
```
## strToDate(str,strFormat)
字符串转Date对象。时间使用格式参照【dateFormat】。
```javascript 1.5
    Utils.strToDate('20180102181225555','YYYYMMDDhhmmssSSS');//Tue Jan 02 2018 18:12:25 GMT+0900 (東京 (標準時))
    Utils.strToDate('2018-01-02','YYYY-MM-DD');//Tue Jan 02 2018 00:00:00 GMT+0900 (東京 (標準時))
```
## strToTimestamp(str,strFormat)
字符串格式的时间，转换成时间戳。
```javascript 1.5
    Utils.strToTimestamp('20180102181225555','YYYYMMDDhhmmssSSS');//1514884346
```
## nowTimestamp()
当前时间戳。
```javascript 1.5
    Utils.nowTimestamp();//1540542098
```
## dateCount(date, diff, type)
日期计算,返回时间格式日期
```javascript 1.5
    Utils.dateCount(new Date(), -1,'y');//Thu Oct 26 2017 21:06:29 GMT+0800 (中国标准时间)
    Utils.dateCount(new Date(), 2,'m');//Sun Aug 26 2018 21:06:29 GMT+0800 (中国标准时间)
    Utils.dateCount(new Date(), 1,'d');//Sat Oct 27 2018 21:06:29 GMT+0800 (中国标准时间)
```

