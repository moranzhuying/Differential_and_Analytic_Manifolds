# 微分流形与解析流形

## 主要内容

Bourbaki《数学原本》(Éléments de mathématique) 中《微分流形与解析流形》一卷的自学笔记。

## 说明

本笔记按 Bourbaki 原书的章节层级组织，对应关系如下：

| Bourbaki 原书 | 本笔记 | 本仓库中的示例 |
|---|---|---|
| 章（Chapitre） | `Content/` 下的**章目录** | `1_Differential_Manifolds/` |
| 节（§） | 章目录下的**节目录** | `1_Differentiable_functions/` |
| 小节（1、2、…） | 节目录下的 **`.tex` 文件** | `1_Order_of_contact_of_two_functions_at_a_point.tex` |

- 目录与文件名取该层级标题的**英译**，并加编号前缀（`1_`、`2_`…，不加前导零）。
- 中文标题写在 `\chapter{...}` 与 `\section{...}` 中：`\chapter{}` 用该**节目录**名的中译，`\section{}` 用该**文件**名的中译。
- 每层目录各有一个 `index.tex`，按顺序汇总对下一层的 `\input`。

定理环境用法、交叉引用（`\cref`）、符号库维护等 **tex 层面的规定**，另见模板《笔记写作》的 README。

## 内容结构

```
Content/
├─ 1_Differential_Manifolds/
│  ├─ 1_Differentiable_functions/
│  ├─ 2_Real_differentiable_functions/
│  ├─ 3_Real_or_complex_analytic_functions/
│  ├─ 4_Analytic_functions_non-Archimedean_case/
│  ├─ 5_Manifolds/
│  ├─ 6_Fiber_bundles/
│  ├─ 7_Vector_bundles/
│  └─ Appendix_Continuous_polynomials_and_formal_series/
└─ 2_Analytic_Manifolds/
   ├─ 1_Differential_calculus_of_order_1/
   ├─ 2_Differential_equations_and_foliations/
   ├─ 3_Measures_defined_by_differential_forms/
   ├─ 4_Stokes_formula/
   ├─ 5_Jets/
   ├─ 6_Point_distributions/
   ├─ 7_Differential_operators/
   └─ 8_Manifolds_of_maps/
```

## 文件结构

```
main.tex          编译入口
structure.sty     样式包：页面设置、定理环境、引用、数学符号库
quiver.sty        交换图支持
Content/          分章正文，每章一个目录，由 index.tex 汇总 \input
commit.py         一键提交并推送（说明见 commit.md）
setup_mode.py     习题编排模式切换（说明见 setup_mode.md）
README.md         本文件：项目说明
CHANGELOG.md      更新日志：tex 配置调整与正文内容调整
```

各脚本的选项与功能分别见 [commit.md](commit.md) 与 [setup_mode.md](setup_mode.md)；符号库由上层目录的 `symbols.py` 统一管理。

## 编译

本笔记使用自建的【笔记写作】模板（样式包 `structure.sty`），须用 **XeLaTeX** 编译：

```bash
xelatex main.tex
```

- **编译环境**：XeLaTeX。模板依赖 ctexbook 与 XeLaTeX 特性，**不支持 pdfLaTeX**。
- **TeXStudio**：建议 4.0 或更高版本。
- `main.pdf` 未纳入版本控制，需本地编译生成。
