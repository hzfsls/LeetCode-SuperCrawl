## [1543.产品名称格式修复](https://leetcode.cn/problems/fix-product-name-format/)
<p>表：<code>Sales</code></p>

<pre>
+--------------+---------+
| Column Name  | Type    |
+--------------+---------+
| sale_id      | int     |
| product_name | varchar |
| sale_date    | date    |
+--------------+---------+
sale_id 是该表主键
该表的每一行包含了产品的名称及其销售日期
</pre>

<p>&nbsp;</p>

<p>因为在 2000 年该表是手工填写的，<code>product_name</code>&nbsp;可能包含前后空格，而且包含大小写。</p>

<p>写一个 SQL 语句报告每个月的销售情况：</p>

<ul>
	<li><code>product_name</code>&nbsp;是小写字母且不包含前后空格</li>
	<li><code>sale_date</code>&nbsp;格式为&nbsp;<code>('YYYY-MM')</code>&nbsp;</li>
	<li><code>total</code>&nbsp;是产品在本月销售的次数</li>
</ul>

<p>返回结果以&nbsp;<code>product_name</code>&nbsp;<strong>升序</strong> 排列，如果有排名相同，再以&nbsp;<code>sale_date</code> <strong>升序 </strong>排列。</p>

<p>查询结果格式如下所示。</p>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<pre>
<code><strong>输入：</strong>
Sales</code> 表：
+---------+--------------+------------+
| sale_id | product_name | sale_date  |
+---------+--------------+------------+
| 1       | LCPHONE      | 2000-01-16 |
| 2       | LCPhone      | 2000-01-17 |
| 3       | LcPhOnE      | 2000-02-18 |
| 4       | LCKeyCHAiN   | 2000-02-19 |
| 5       | LCKeyChain   | 2000-02-28 |
| 6       | Matryoshka   | 2000-03-31 |
+---------+--------------+------------+
<strong>输出：</strong>
+--------------+-----------+-------+
| product_name | sale_date | total |
+--------------+-----------+-------+
| lckeychain   | 2000-02   | 2     |
| lcphone      | 2000-01   | 2     |
| lcphone      | 2000-02   | 1     |
| matryoshka   | 2000-03   | 1     |
+--------------+-----------+-------+
<strong>解释：</strong>
一月份售出 2 部 LcPhones。请注意，产品名称不区分大小写，且可能包含空格。 
二月份售出 2 个 LCKeychains 和 1部 LCPhone。 
三月份售出 1 个 Matryoshka。</pre>
