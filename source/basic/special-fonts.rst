特殊字体
========

在介绍字体时说过，12号字体（Symbol）和34号字体（ZapfDingbats）比较特殊，这一节专门介绍一下。

能从键盘直接输入的字符是有限的，只有大小写的26个字母、0-9的阿拉伯数字以及几个常见的符号。有时候可能想要输入一些特殊的字符，比如希腊字母。

以字符 ``a`` 为例，使用除12号和34号外的其他字体时，显示的永远是字符 ``a`` ，只是样子可能有些不一样。如果将字符 ``a`` 设置为12号字体，显示的是 :math:`\alpha` ；如果将字符 ``a`` 设置为34号字体，则显示的是一个类似花的图案。本质上，12号和34字体与其他字体并没有什么本质的区别，可以理解为这两个字体显示的时候变化比较大。

由于输入的字符 ``a`` 与实际显示的字符 :math:`\alpha` 的差别太大，所以要一一对应就变得很困难。因而在使用12号和34号字体时通常使用一个三位的八进制码表示一个字符，每个二进制码对应一个字符。

下图给出了12号字体（Symbol字符集）和34字体（Pifont ZapfDingbats）的字符与八进制码对应关系：

.. figure:: /images/GMT_symbol_dingbats.*
   :width: 100%
   :align: center

   Symbol和Pifont字体八进制码

比如需要字符 :math:`\beta` ，则首先设置文本的字体为12号字体，查上表可知，字符 :math:`\beta` 位于 ``\14x`` 行 ``2`` 列，因而其对应的八进制码为 ``\142`` 。同理， :math:`\theta` 的八进制码为 ``\161`` 。同样是八进制码 ``\161`` ，如果设置字体为34号，则是右边图中对应的类似矩形的符号了。

下图给出了一些示例：

.. figure:: /images/GMT_symbol_examples.*
   :width: 100%
   :align: center

   12号和34号字体示例

对于26个希腊字母的大小写而言，由于其与26个英语字母的大小写一一对应，所以如果熟悉的话，完全可以用英文字母写文本，然后设置字体为12号字体，如第一行所示，这样的做法比第二行用八进制码1要简单些。但是对于其他特殊字符，由于不存在这种有规律的对应关系，所以最好使用八进制码表示。

用户可通过转义字符 @~ 或 @%% 来使用上述特殊字体，例如::

    gmt psbasemap -R0/10/0/10 -JX10c/10c -BWSne -Bx2+l"@~\161@~ or @%12%\161@%%" -By2+l"@%34%\164@%%" > test.ps

