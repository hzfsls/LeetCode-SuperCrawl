## [571.给定数字的频率查询中位数]
<p><code>Numbers</code> 表：</p>

<pre>
+-------------+------+
| Column Name | Type |
+-------------+------+
| num         | int  |
| frequency   | int  |
+-------------+------+
num 是这张表的主键(具有唯一值的列)。
这张表的每一行表示某个数字在该数据库中的出现频率。</pre>

<p>&nbsp;</p>
<a href="https://baike.baidu.com/item/%E4%B8%AD%E4%BD%8D%E6%95%B0/3087401" target="_blank"><strong>中位数</strong></a> 是将数据样本中半数较高值和半数较低值分隔开的值。

<p>编写解决方案，解压 <code>Numbers</code> 表，报告数据库中所有数字的 <strong>中位数</strong> 。结果四舍五入至 <strong>一位小数</strong> 。</p>

<p>返回结果如下例所示。</p>

<p>&nbsp;</p>

<div class="top-view__1vxA">
<div class="original__bRMd">
<div>
<p><strong>示例 1：</strong></p>

<pre>
<strong>输入：</strong> 
Numbers 表：
+-----+-----------+
| num | frequency |
+-----+-----------+
| 0   | 7         |
| 1   | 1         |
| 2   | 3         |
| 3   | 1         |
+-----+-----------+
<strong>输出：</strong>
+--------+
| median |
+--------+
| 0.0    |
+--------+
<strong>解释：</strong>
如果解压这个 Numbers 表，可以得到 [0, 0, 0, 0, 0, 0, 0, 1, 2, 2, 2, 3] ，所以中位数是 (0 + 0) / 2 = 0 。
</pre>
</div>
</div>
</div>
