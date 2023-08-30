## [2777.日期范围生成器]
<p>现给定起始日期 <code>start</code> 、结束日期 <code>end</code> 和正整数 <code>step</code> ，返回一个生成器对象，该生成器对象按照从 <code>start</code> 到 <code>end</code>（包括 start 和 end ）的范围生成日期。所有日期都以字符串格式 <code>YYYY-MM-DD</code> 表示。<code>step</code> 的值表示连续生成的日期之间的天数间隔。</p>

<p>&nbsp;</p>

<p><strong class="example">示例 1：</strong></p>

<pre>
<b>输入：</b>start = "2023-04-01", end = "2023-04-04", step = 1
<b>输出：</b>["2023-04-01","2023-04-02","2023-04-03","2023-04-04"]
<b>解释：</b>
const g = dateRangeGenerator(start, end, step);
g.next().value // '2023-04-01'
g.next().value // '2023-04-02'
g.next().value // '2023-04-03'
g.next().value // '2023-04-04'</pre>

<p><strong class="example">示例 2：</strong></p>

<pre>
<b>输入：</b>start = "2023-04-10", end = "2023-04-20", step = 3
<b>输出：</b>["2023-04-10","2023-04-13","2023-04-16","2023-04-19"]
<b>解释：</b>
const g = dateRangeGenerator(start, end, step);
g.next().value // '2023-04-10'
g.next().value // '2023-04-13'
g.next().value // '2023-04-16'
g.next().value // '2023-04-19'</pre>

<p><strong class="example">示例 3：</strong></p>

<pre>
<b>输入：</b>start = "2023-04-10", end = "2023-04-10", step = 1
<b>输出：</b>["2023-04-10"]
<b>解释：</b>
const g = dateRangeGenerator(start, end, step);
g.next().value // '2023-04-10'
</pre>

<p>&nbsp;</p>

<p><strong>提示：</strong></p>

<ul>
	<li><code>new Date(start) &lt;= new Date(end)</code></li>
	<li><code>0 &lt;= 结束日期与开始日期之间的天数差 &lt;= 1000</code></li>
	<li><code>1 &lt;= step &lt;= 100</code></li>
</ul>
