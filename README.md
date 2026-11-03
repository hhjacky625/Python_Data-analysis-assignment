# 数据分析作业 · Data Analysis Assignment

> 一份用 Python 完成的数据分析课程个人作业：从数据预处理概念、数据可视化，到 seaborn `penguins` 数据集的探索性分析与 PCA 降维，全部整理成可一键运行的 Jupyter Notebook。
>
> A course assignment completed in Python: from data-preprocessing fundamentals and visualization to exploratory analysis and PCA on the seaborn `penguins` dataset — all packaged as runnable Jupyter notebooks.

![Python](https://img.shields.io/badge/Python-3.13-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![License](https://img.shields.io/badge/use-coursework-lightgrey)

**作者 / Author：** 黄河俊天 (Huang JunTian)　**学号 / ID：** 22301170100

---

## 📌 作业要求 / Assignment Requirements

作业共 6 题，每题在 notebook 中对应一个独立 section（理论题用 Markdown 作答，操作题附可运行代码与输出结果）。

| # | 题目要求 | 类型 | 对应内容 |
|---|---|---|---|
| 1 | 数据预处理包括哪些步骤？ | 理论 | 数据清洗 / 集成 / 变换 / 规约 / 划分 五步 |
| 2 | 什么是异常值？ | 理论 | 定义、成因、3σ 与 IQR 检测法、处理方式 |
| 3 | 复现简洁美观的 sin 和 cos 图 | 绘图 | π 刻度、坐标轴居中、去边框、图例 |
| 4 | 使用 `plt.subplot` 绘制多列散点图 | 绘图 | 2×2 子图，penguins 特征组合按种类着色 |
| 5 | 画出箱线图，并解释箱体上的各个部分 | 绘图 + 解释 | 箱体 / 四分位数 / 中位线 / 须线 / 离群点标注 |
| 6* | 用 penguins 数据集：探索特征，绘散点图、箱体图、小提琴图、成对图，并做 PCA | 综合 | 数据探索 → 4 类图形 → 标准化 + PCA 降维 |

> 第 6 题为加分题（带 \*），是整份作业的主体部分。

---

## 📂 仓库结构 / Repository Structure

```
.
├── 数据分析作业.ipynb                  # 中文版 notebook（6 题，已执行并保存输出）
├── Data_Analysis_Assignment_EN.ipynb   # 英文版 notebook（内容一一对应）
├── images/                             # README 预览图（从 notebook 输出中提取）
│   ├── 01_sin_cos.png
│   ├── 02_subplot_scatter.png
│   ├── 03_boxplot.png
│   ├── 04_scatter.png
│   ├── 05_violin.png
│   ├── 06_pairplot.png
│   └── 07_pca.png
├── requirements.txt                    # 依赖清单
└── README.md
```

两个 notebook 的单元格输出（图表、统计量）都已执行并内嵌保存，**克隆后无需运行即可直接查看结果**。

---

## 🚀 快速开始 / Quick Start

```bash
git clone <this-repo-url>
cd <repo-folder>

# 建议使用虚拟环境
pip install -r requirements.txt

jupyter notebook
```

打开 `数据分析作业.ipynb`（或英文版），点击 **Run All** 即可复现全部结果。

> 首次运行 `sns.load_dataset("penguins")` 需要联网下载数据集，之后 seaborn 会自动缓存。

---

## 🔍 内容导览 / What's Inside

**第 1–2 题**：数据预处理与异常值的概念梳理，以表格形式对比各步骤 / 检测方法的适用场景。

**第 3 题**：Matplotlib 绘制 sin / cos 曲线——`np.linspace` 生成平滑采样点，刻度用 π 表示，隐藏上/右边框并把左/下轴移到原点。

**第 4 题**：`plt.subplot(2, 2, i)` 布局 4 个子图，展示嘴长、嘴深、鳍长、体重两两组合的散点关系，按企鹅种类着色。

**第 5 题**：以企鹅体重为例绘制箱线图，并在图上用箭头标注 Q1、Q3、中位数、上下须与离群点，配文解释各部分的统计含义。

**第 6 题**（核心）：
- **数据探索**：344 行 × 7 列，3 个种类（Adelie 152 / Gentoo 124 / Chinstrap 68），统计各列缺失值，清洗后 333 行；
- **可视化**：散点图、分组箱体图、小提琴图（含四分位内嵌）、成对图（对角 KDE）；
- **PCA**：4 个数值特征标准化后降至 2 维，**PC1 解释 68.6%，PC2 解释 19.4%，累计 88.1%**，并输出主成分载荷矩阵与降维散点图——Gentoo 在主成分平面上明显分离。

---

## 📊 结果预览 / Result Previews

| sin & cos 曲线 | 箱线图标注 |
|---|---|
| <img src="images/01_sin_cos.png" width="420"> | <img src="images/03_boxplot.png" width="420"> |

| `plt.subplot` 多列散点图 |
|---|
| <img src="images/02_subplot_scatter.png" width="860"> |

| penguins 散点图 | 分组小提琴图 |
|---|---|
| <img src="images/04_scatter.png" width="420"> | <img src="images/05_violin.png" width="420"> |

| 成对图 (pairplot) | PCA 降维结果 |
|---|---|
| <img src="images/06_pairplot.png" width="420"> | <img src="images/07_pca.png" width="420"> |

---

## 🛠 运行环境 / Environment

- Python 3.13
- pandas · numpy · matplotlib · seaborn · scikit-learn · jupyter

版本要求见 [requirements.txt](requirements.txt)。

---

## 📄 License / 使用说明

本仓库为课程作业存档，仅供学习参考。如需引用其中的代码或图表，请注明出处。
This repository is archived coursework for learning purposes. Please credit the source if you reuse the code or figures.
