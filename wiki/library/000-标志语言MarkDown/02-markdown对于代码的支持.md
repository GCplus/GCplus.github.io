# markdown对于代码的支持
>当前版本：v1.1  
>维护人：Jhin  
>维护时间：2017年10月27日

## markdown语法高亮
 本网页使用amwiki来进行创建的，使用 [highlight.js](https://github.com/isagalaev/highlight.js) 进行预语法高亮渲染，它能对多达一百多种语言、样式提供语法高亮解析
使用两组每组三个反引号分单独两行将代码包围起来，并在第一组反引号后写上语言类型即可使用语法高亮。
用法说明
```
```（代码类型，比如js,javascript,java,c,cpp...）
//code
``````
如下为各个代码普通效果与添加支持代码的区别

## javascript / js 代码
普通效果
```
//发送验证码
function cd(num) {
    $('#code').val(num + '秒后可重发');
    setTimeout(function() {
        if (num - 1 >= 0) {
            cd(num - 1);
        } else {
            $('#code').removeClass('bg-gray').prop('disabled', false).val('重新发送验证码');
        }
    },
    1000);
}
```
添加js(javascript)后的代码展示
```js
//发送验证码
function cd(num) {
    $('#code').val(num + '秒后可重发');
    setTimeout(function() {
        if (num - 1 >= 0) {
            cd(num - 1);
        } else {
            $('#code').removeClass('bg-gray').prop('disabled', false).val('重新发送验证码');
        }
    },
    1000);
}
```
说明：  
amWiki 对 javascript 代码片段做了再次增强，可以点击 代码块右上角按钮 隐藏/显示注释
当注释处于隐藏状态时不会被复制，比较适合模拟返回 json 数据的接口时直接拷贝  
**由于 json 格式不允许注释，可以使用 js 替代着色**
## html代码
普通代码效果
```
<body>
    <div class="loading"><img src="/assets/images/loading.gif"></div>
    <header>some text</header>
    <script type="text/javascript" src="/assets/js/jquery-2.1.4.min.js"></script>
</body>
```
添加html后
```html
<body>
    <div class="loading"><img src="/assets/images/loading.gif"></div>
    <header>some text</header>
    <script type="text/javascript" src="/assets/js/jquery-2.1.4.min.js"></script>
</body>
```
## css代码
普通代码效果
```
/* 紧凑 */
html,body{display:block;width:100%;height:100%;min-width:320px;}
a,img{-webkit-touch-callout:none;}
/* 展开 */
input[type="button"],
input[type="submit"],
input[type="reset"],
textarea {
    -webkit-appearance: none;
}
```
添加css后
```css
/* 紧凑 */
html,body{display:block;width:100%;height:100%;min-width:320px;}
a,img{-webkit-touch-callout:none;}
/* 展开 */
input[type="button"],
input[type="submit"],
input[type="reset"],
textarea {
    -webkit-appearance: none;
}
```
## php代码
普通代码效果
```
private function addQuestData($data, $filing_id)
  {
    $quest_num = $data['status'] == 10 ? 1 : 2;
      $where = [
        ['user_filing_id', '=', $filing_id],
        ['project_id', '=', $data['project_id']],
        ['mobile','=', $data['mobile']],
        ['quest_num', '=', $quest_num]
      ];
  }
```
添加php后
```php
private function addQuestData($data, $filing_id)
  {
    $quest_num = $data['status'] == 10 ? 1 : 2;
      $where = [
        ['user_filing_id', '=', $filing_id],
        ['project_id', '=', $data['project_id']],
        ['mobile','=', $data['mobile']],
        ['quest_num', '=', $quest_num]
      ];
  }
```
## sql代码
普通代码块
```
SELECT Company, OrderNumber FROM Orders ORDER BY Company, OrderNumber
```
添加sql后
```sql
SELECT Company, OrderNumber FROM Orders ORDER BY Company, OrderNumber
```
## java 代码
普通代码块
```
public class Test {
   public static void main(String args[]) {
      int x = 10;
      while( x < 20 ) {
         System.out.print("value of x : " + x );
         x++;
         System.out.print("\n");
      }
   }
}
```
添加java后
```java
public class Test {
   public static void main(String args[]) {
      int x = 10;
      while( x < 20 ) {
         System.out.print("value of x : " + x );
         x++;
         System.out.print("\n");
      }
   }
}
```
## CPP语言
普通代码块
```
public class Test{
  public int main(){
    print ("hello");
  }
}
```
添加cpp后
```cpp
public class Test{
  public int main(){
    print ("hello");
  }
}
```
## C语言，cpp是相同注释
普通代码块
```
include<studio.h>
int main(){
  return 0;
}
```
添加c后
```cpp
include<studio.h>
int main(){
  return 0;
}
```
## python
普通代码块
```
print('hello, world')
```
添加python后
```python
print('hello, world')
```
## 章节引用
+ [markdown语法高亮-amWiki]( https://amwiki.org/doc/?file=020-%E6%95%99%E7%A8%8B%E5%AD%A6%E4%B9%A0%E7%AF%87/005-%E5%AD%A6%E4%B9%A0markdown/02-Markdown%E8%AF%AD%E6%B3%95%E9%AB%98%E4%BA%AE)
+ [highlight.js-GitHub](https://github.com/isagalaev/highlight.js)

## 历史版本

| 版本号 | 维护人 |维护时间 |维护内容|
| :- | :- | :-| :- |
| v1.0 | [Jhin](http://blog.link-lin.cn) |2017-10-27|创建了本词条|
|v1.1|[Jhin](http://blog.link-lin.cn)|2047-11-12|修改本词条的历史版本显示bug|
