# utils
工作中使用的工具类

## isInteger(number)
判断number是否是整数。
```$javascript 1.5
    Utils.isInteger(1); //true
    Utils.isInteger(1.1);//false
    Utils.isInteger('1');//false
```
## isString(str)
判断str是否是字符串
```javascript 1.5
    Utils.isString('1');                //true
    Utils.isString(new String('1'));    //true
    Utils.isString(1);                  //false
```
