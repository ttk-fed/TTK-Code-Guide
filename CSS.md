# CSS 编码规范

以下为前端开发团队遵循和约定的 CSS 编码规范。

## 代码风格

* 代码应该符合 CSS 语法有效性，可以使用 [W3C CSS validator](http://jigsaw.w3.org/css-validator/validator.html.zh-cn) 工具来验证。

* ID 和 Class 应该按照元素功能命名，不应该按照元素表现命名，命名应该含义清晰。

    ```css
    /* bad: 含义不清 */
    #yee-1901 {}

    /* bad: 表现化 */
    .button-green {}
    .clear {}

    /* good: 功能化 */
    #gallery {}
    #login {}
    .video {}
    ```

* ID 和 Class 命名应该在保持含义清晰的前提下尽可能简短。

    ```css
    /* bad */
    #navigation {}
    .atr {}

    /* good */
    #nav {}
    .author {}
    ```

* ID 和 Class 命名中单词应该全部小写，单词之间使用 `-` 作为分隔符。

    ```css
    /* bad */
    #videoId {}
    .demoimage {}
    .error_status {}

    /* good */
    #video-id {}
    .ads-sample {}
    ```

* 不能「MUST NOT」把 ID 和 Class 选择符作为类型选择符的限定符，这样做没必要，反而还影响性能。

    ```css
    /* bad */
    ul#example {}
    div.error {}

    /* good */
    #example {}
    .error {}
    ```

* CSS 属性应该尽可能使用简化方式书写，需注意简写时默认值的副作用，详细参考 [Shorthand properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties)。

    ```css
    /* bad */
    border-top-style: none;
    font-family: palatino, georgia, serif;
    font-size: 100%;
    line-height: 1.6;
    padding-bottom: 2em;
    padding-left: 1em;
    padding-right: 1em;
    padding-top: 0;

    /* good */
    border-top: 0;
    font: 100%/1.6 palatino, georgia, serif;
    padding: 0 1em 2em;
    ```

* CSS 属性中的 `0` 值不应该带单位。

    ```css
    /* bad */
    margin: 0px;
    padding: 0px;

    /* good */
    margin: 0;
    padding: 0;
    ```

* CSS 属性中数值介于-1到1之间的小数应该忽略开头的 `0`。

    ```css
    /* bad */
    font-size: 0.8em;

    /* good */
    font-size: .8em;
    ```

* CSS 的色值应该尽可能使用简化写法。

    ```css
    /* bad */
    color: #eebbcc;

    /* good */
    color: #ebc;
    ```


## 组织格式

* 必须采用 4 个空格为一次缩进。

* CSS 属性声明应该按字母升序排列。

    ```css
    /* good */
    background: fuchsia;
    border: 1px solid;
    -moz-border-radius: 4px;
    -webkit-border-radius: 4px;
    border-radius: 4px;
    color: black;
    text-align: center;
    text-indent: 2em;
    ```

* CSS 每个代码块相对于父代码库必须有缩进。

    ```css
    /*good*/
    @media screen, projection {

      html {
        background: #fff;
        color: #444;
      }

    }
    ```

* CSS 属性声明必须以分号结尾。
* CSS 属性名冒号后必须有一个空格。

    ```css
    /* bad */
    color:#eebbcc;

    /* good */
    color: #ebc;
    ```

* CSS 中的属性名建议按照字母顺序排列，可以使用 Sublime Text 的 F5 命令来自动格式化。
* 最后的选择符与 `{` 之间必须有一个空格。

    ```css
    /* bad */
    #video{
      margin-top: 1em;
    }
    .author
    {
      margin-top: 1em;
    }

    /* good */
    #video {
      margin-top: 1em;
    }
    ```

* 多个并列的选择符必须换行。

    ```css
    /* bad */
    a:focus, a:active {
      position: relative; top: 1px;
    }

    /* good */
    h1,
    h2,
    h3 {
      font-weight: normal;
      line-height: 1.2;
    }
    ```

* CSS 规则之间必须以空白行分隔。

    ```css
    /* good */
    html {
      background: #fff;
    }

    body {
      margin: auto;
      width: 50%;
    }
    ```

* CSS 属性值中所有使用到引号的位置必须使用单引号。

    ```css
    /* bad */
    @import url("//www.google.com/css/maia.css");

    html {
      font-family: "open sans", arial, sans-serif;
    }

    /* good */
    @import url('//www.google.com/css/maia.css');

    html {
      font-family: 'open sans', arial, sans-serif;
    }
    ```


## 代码注释

* CSS规则段落之前应该添加注释说明。

    ```css
    /* good */
    /* Header */

    #adw-header {}

    /* Footer */

    #adw-footer {}

    /* Gallery */

    .adw-gallery {}
    ```
