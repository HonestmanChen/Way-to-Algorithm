<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS-MML_HTMLorMML"/></script>
<script> gitbook.events.bind("page.change", function() { MathJax.Hub.Queue(["Typeset",MathJax.Hub]); } </script>

# Boyer Moore - Boyer-Moore算法

--------

#### 问题

在文本$$ text $$中查找字符串$$ pattern $$出现的所有位置（$$ text $$长度为$$ n $$，$$ pattern $$长度为$$ m $$，$$ n, m $$都是正整数且$$ n \gt m $$）。

#### 解法

Boyer-Moore算法与KMP算法类似，当匹配失败时跳转到某个位置继续匹配。

--------

#### 源码

[import, lang:"c_cpp"](../../../src/TextMatch/BoyerMoore.h)

#### 测试

[import, lang:"c_cpp"](../../../src/TextMatch/BoyerMoore.cpp)