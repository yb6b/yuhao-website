# 单字编码

## 编码规则

学习了「宇浩」的拆字规则后，我们可以将任何一个汉字拆成唯一的字根组合。最后一步，便是把字根转为「宇浩」编码。

宇浩的单字编码一般是由**4 个字母**构成。部分字根字为 3 个字母。

在「宇浩」中，无论一个字能拆成几个字根，我们只关心其中的四个根，分别是：

- 第一根：首根
- 第二根：二根
- 第三根：三根
- 倒数第一根：末根

这同五笔字型相同，和郑码、徐码不同。

单字编码规则如下：

1. 依次取一、二、三、末根大码。
2. 不足四码时，补上末根小码。
3. 仍然不足四码时，补上首根小码。

最后一条，只有双根字中会出现。第二条，只有三根字中会出现。

::: tip 例

- 「嫩」字拆成〔女木口夂〕，分别对应了首根、二根、三根、末根，我们直接取〔女 Cn 木 Fv 口 Lv 夂 Eh〕四个字根的大码 CFLE 即可出字。
- 「整」字拆成〔木口夂一止〕，我们只取首根、二根、三根、末根，也就是〔木 Fv 口 Lv 攵 Eh 止 Ni〕的大码，输入 FLEN 即可出字。
- 「算」字拆成〔竹目卄〕，只有三根，所以我们取全部根，也就是〔𥫗Qk 目 Mf 廾 Sj〕的大码，即 QMS。此时，注意到不足四码，故而补上最末根的小码 o。输入 QMSj 即可出字。
- 「织」字拆成〔纟口八〕，只有三根，所以我们取全部根大码，也就是 VLT。此时，注意到不足四码，故而补上最末根的小码 b。输入 VLTi 即可出字。
- 「认」字拆成〔讠人〕，只有两根，所以我们取全部根，也就是〔讠 Oa 人 Te〕的大码，即 OT 。此时，注意到不足四码，故而补上最末根的小码 e。注意到仍然不足四码，于是再添上首根的小码 a。输入 OTea 即可出字。
- 「好」字拆成〔女子〕，只有两根，所以我们取全部根，也就是〔女 Cn 子 Vk〕的大码，即 CV。此时，注意到不足四码，故而补上最末根的小码 k。注意到仍然不足四码，于是再添上首根的小码 n。输入 CVkn 即可出字。
:::

末尾添加首根的小码，只是为了补齐四码的作用，只有在双根字中才会出现。

## 成字字根

有些字根本身就是常用字，称为「成字字根」，又称为「单根字」。

单根字的全码为三码：大码+小码+小码

::: tip 例

- 「木」作为单字时，编码为 `Fvv`。
- 「骨」作为单字时，编码为 `Mgg`。
:::

注意到，字根字编码规则同单字编码规则是一致的。

- 假设字根大码为 A，小码为 a。  
- 首先，依次取一、二、三、末根大碼，故取 A。  
- 接着，不足四碼，故補上末根小碼，故取 a。  
- 最後，仍然不足四碼，故補上首根小碼 a。最終編碼爲 Aaa。

::: info 常见问题

Q：字根字重复小码的原因是什么？  
A：首先是为了让字根编码规则和单字编码规则一致。其次，如果字根字是两码，但字根本身比较罕用，那么会浪费一个宝贵的二级简码码位。很多输入法会将另一个常用字设置成二简，而让字根字选重，或者通过其他方式为字根字增加一码。这个方式实际上却在事实上形成了新的重码。宇浩输入法直接在根源上解决了这个问题。
:::

## 空格键的使用

在很多输入法软件中，空格键（以下用`_`表示）用来上屏首选字。

根据以上的学习内容，我们发现：「宇浩」的编码最长不超过 4 个字母。由于这个特性，我们在输入完编码后，不一定需要按空格键将字打上屏幕。

空格键只在以下情况需要使用：

1. 一个字的编码低于 4 位，需要按空格键上屏首选。比如「人」字，需要按`Re_`上屏。
2. 一个字的编码等于 4 位，且后面没有其他的字需要输入，则需要按空格键上屏首选。

以下情况，不需要使用空格键：

一个字的编码等于 4 位，且有后续字符等待输入。我们不需要按空格键。只要直接输入下一个字的首码，这个字就会自动上屏。我们称之为「五码顶屏」。例如：我们打「霁雨」二字，「霁」字的编码是`〔雨文{介下同八}・ CTKa〕`。输入`a`后，我们直接输入「雨」字的编码`〔雨・ Cvv〕`，则「霁」字会自动上屏。