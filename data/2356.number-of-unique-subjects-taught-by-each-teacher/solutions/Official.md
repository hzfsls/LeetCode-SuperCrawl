[TOC]

## 解决方案

- MySQL

- Pandas

---

### 概述

计算每一位老师在大学里教授的不同科目的数量。

---

### 方法 1：GROUP BY 和计数 DISTINCT

#### MySQL

##### MySQL 思想

在 SQL 中，统计每个教师教授的不同科目数量的查询涉及到按 `teacher_id` 分组，然后计算不同的 `subject_id`。

##### MySQL 算法

这项任务需要计算每位教师在大学里教授的不同科目的数量。这意味着我们必须按 teacher_id 分组，然后计算不同的 subject_id。

以下是一个帮助巩固该算法背后的思想的例子：

一开始的 `teacher` 表：

| teacher_id | subject_id | dept_id |
|------------|------------|---------|
| 1          | 2          | 3       |
| 1          | 2          | 4       |
| 1          | 3          | 3       |
| 2          | 1          | 1       |
| 2          | 2          | 1       |
| 2          | 3          | 1       |
| 2          | 4          | 1       |

按照 `teacher_id` 分组并计数不同的 `subject_id` 之后的表：

| teacher_id | cnt |
|------------|-----|
| 1          | 2   |
| 2          | 4   |

##### MySQL 实现

```Sql
SELECT teacher_id, COUNT(DISTINCT subject_id) AS cnt
FROM Teacher
GROUP BY teacher_id;
```

#### Pandas

##### Pandas 思想

在 Pandas 中，我们可以对 `'teacher_id'` 列使用 groupby 函数，然后使用 `.nunique()` 函数计算每个教师的唯一 `'subject_id'` 。

##### Pandas 算法

要计算每名教师在大学中教授的独特科目的数量，我们首先需要按 `'teacher_id'` 分组，然后统计不同 `'subject_id‘` 的数量。列的重命名是为了使输出匹配所需的格式(类似于 SQL 中的 `AS` 关键字)。
注意，我们需要为它指定 `axis=1` ，因为我们重命名的是列，而不是行。

以下是一个帮助巩固该算法背后的思想的例子：

一开始的 `teacher` 表：

| teacher_id | subject_id | dept_id |
|------------|------------|---------|
| 1          | 2          | 3       |
| 1          | 2          | 4       |
| 1          | 3          | 3       |
| 2          | 1          | 1       |
| 2          | 2          | 1       |
| 2          | 3          | 1       |
| 2          | 4          | 1       |

在按照 `teacher_id` 分组并计数不同的 `subject_id` 后的表：

| teacher_id | cnt |
|------------|-----|
| 1          | 2   |
| 2          | 4   |

##### Pandas 实现

```Python3
import pandas as pd

def count_unique_subjects(teacher: pd.DataFrame) -> pd.DataFrame:
    df = teacher.groupby(["teacher_id"])["subject_id"].nunique().reset_index()
    df = df.rename({'subject_id': "cnt"}, axis=1)
    return df
```