# Developmental Analysis of Frequency-Based Auditory Information Flow Segregation in ICc Neurons  
# ICc神经元基于频率信息的听觉信息流分离发育分析

---

## Overview 概述

This project investigates how frequency-based auditory information flow segregation evolves across development in rat inferior colliculus (ICc) neurons.

本项目研究大鼠下丘（ICc）神经元基于频率信息的听觉信息流分离能力在发育过程中的变化规律。

We focus on how frequency selectivity and frequency response functions (FRFs) change across developmental stages, and how these changes relate to population coding and information segregation.

核心关注频率选择性与频率响应函数（frequency response function, FRF）在发育过程中的变化，以及其与群体编码及信息流分离能力之间的关系。

---

## Mechanistic Rationale 机制基础

At the single-neuron level, frequency response function (FRF) sharpness determines frequency selectivity.

在单神经元层面，频率响应函数（FRF）的尖锐程度直接决定神经元对频率信息的选择性。

Neuronal responses are centered around the best frequency (BF) and decay with frequency deviation.

神经元响应以最佳频率（BF）为中心，并随着频率偏离逐渐下降。

At the population level, neurons with different BFs jointly form a distributed representation of frequency space.

在群体层面，不同BF神经元共同构成对频率空间的分布式表征。

Reduced overlap between FRFs enhances separability of auditory representations.

FRF重叠程度降低会增强不同声源在群体编码空间中的可分离性。

This mechanism is consistent with the evidence accumulation framework in auditory scene analysis (Bregman).

该机制与Bregman提出的听觉场景分析中的“证据积累”理论一致。

---

## Analysis Goal 分析目标

To quantify developmental changes in frequency-based information flow segregation in ICc neurons.

本研究旨在量化ICc神经元基于频率信息的听觉信息流分离能力在发育过程中的变化。

This is operationalized as changes in frequency response function (FRF) bandwidth across age groups.

通过不同年龄组FRF带宽变化进行定量刻画。

---

## Pipeline Overview 分析流程

### 1. Multi-peak FRF preprocessing 多峰FRF预处理

- Gaussian smoothing applied to FRF  
  对FRF进行高斯平滑  

- Peak prominence estimation  
  计算次峰显著性  

- IQR-based thresholding (Q3 + 1.5×IQR)  
  四分位间距异常检测  

- Removal of multi-unit contaminated neurons  
  剔除多单元污染神经元  

Thresholds are computed independently within each age group.

阈值在每个年龄组内独立计算，以避免分布偏差。

---

### 2. Frequency normalization 频率归一化

To account for nonlinear scaling of auditory frequency tuning:

为解决频率尺度非线性问题：

All frequencies are transformed into a BF-centered logarithmic space:

所有频率转换为以BF为中心的对数空间：

x = log2(f / BF)

This ensures comparability across neurons with different BF.

用于消除不同BF神经元之间的尺度不可比性。

---

### 3. Probabilistic representation 概率化表示

Each neuron’s FRF is normalized into a probability-like distribution.

将每个神经元的FRF标准化为概率分布形式。

---

### 4. Population FRF modeling 群体FRF建模

Within each age group, FRFs are centered and fitted using maximum likelihood estimation.

在每个年龄组内，对FRF进行中心化并采用最大似然估计进行拟合。

Models used:

- Gaussian  
- Cauchy  
- Laplace  

Model selection is performed using Akaike Information Criterion (AIC).

使用AIC准则选择最佳模型。

---

### 5. Developmental results 发育结果

The Laplace model provides the best fit across all age groups.

所有年龄组均以Laplace模型拟合最佳。

Estimated width parameter (b):

- P14–20: 0.25  
- P21–30: 0.24  
- Adult: 0.21  

These results indicate progressive narrowing of population FRFs with development.

结果表明FRF随发育逐渐变窄。

---

### 6. Single-neuron validation 单神经元验证

To validate population-level findings:

为验证群体结果：

- FRF fitted using Gaussian / Cauchy / Laplace models  
- Bandwidth computed using full width at half maximum (FWHM)  
- Converted to Q factor to remove BF dependence  

Statistical comparisons (Q values):

- Adult neurons show significantly higher Q values  
- No significant difference between P14–20 and P21–30  

---

## Key Findings 主要结论

- Frequency response functions become progressively sharper with development  
  FRF随发育逐渐变尖锐  

- Population representations show reduced uncertainty  
  群体表征不确定性降低  

- Frequency-based information flow segregation increases with maturation  
  频率信息流分离能力随发育增强  

- Critical developmental transition likely occurs after ~P30  
  关键发育阶段可能在P30之后  

---

## Data Source 数据来源

Extracellular recordings from ICc neurons across developmental stages:

ICc神经元胞外电生理记录数据：

- P14–20  
- P21–30  
- Adult  
