# Developmental Analysis of Frequency-Based Auditory Information Flow Segregation in ICc Neurons

---

## Overview

This project investigates how frequency-based auditory information flow segregation evolves across development in rat inferior colliculus (ICc) neurons.

We focus on how frequency selectivity, as quantified by frequency response functions (FRFs), changes across developmental stages, and how these changes relate to population-level auditory representation and information segregation.

---

## Mechanistic Rationale

At the single-neuron level, frequency response function (FRF) sharpness determines frequency selectivity. Neuronal responses are centered at the best frequency (BF) and decrease with frequency deviation.

At the population level, neurons with different BFs jointly form a distributed representation of frequency space. Reduced overlap between FRFs enhances the separability of auditory representations across frequencies.

This mechanism is consistent with the evidence accumulation framework in auditory scene analysis (Bregman).

---

## Analysis Goal

To quantify developmental changes in frequency-based information flow segregation in ICc neurons using frequency response function (FRF) structure.

---

## Pipeline Overview

### 1. FRF Preprocessing and Multi-unit Removal

- Gaussian smoothing applied to FRF
- Peak prominence estimation for secondary peaks
- IQR-based thresholding (Q3 + 1.5 × IQR) within each age group
- Removal of neurons with significant secondary peaks

All thresholds are computed independently within each developmental group.

---

### 2. Frequency Normalization

To account for nonlinear scaling of auditory frequency tuning, all frequencies are transformed into a BF-centered logarithmic space:

\[
x = \log_2(f / BF)
\]

This ensures comparability across neurons with different best frequencies.

---

### 3. Probabilistic Representation

Each neuron’s frequency response function (FRF) is normalized into a probability-like distribution, enabling population-level statistical modeling.

---

### 4. Population FRF Modeling

Within each age group:

- FRFs are centered and aggregated
- Maximum likelihood estimation (MLE) is used for model fitting

Three models are evaluated:

- Gaussian
- Cauchy
- Laplace

Model selection is performed using Akaike Information Criterion (AIC).

---

## Developmental Results (Population Level)

The Laplace model provides the best fit across all age groups.

Estimated scale parameter (b):

- P14–20: 0.25  
- P21–30: 0.24  
- Adult: 0.21  

These results indicate a progressive narrowing of population frequency response functions across development, suggesting reduced representational uncertainty and improved frequency selectivity.

---

## Single-Neuron Validation

To validate population-level findings, single-neuron FRFs were further analyzed.

- FRFs were fitted using Gaussian, Cauchy, and Laplace models
- Bandwidth was computed using full width at half maximum (FWHM)
- FWHM was converted to Q factor to remove BF dependence

### Statistical results:

- Adult neurons show significantly higher Q values than juvenile groups
- No significant difference between P14–20 and P21–30 groups

---

## Key Findings

- Frequency response functions become progressively sharper with development
- Population-level representations become less uncertain across age
- Frequency-based information flow segregation increases with maturation
- Critical developmental transition likely occurs after ~P30

---

## Data

Extracellular recordings from ICc neurons across developmental stages:

- P14–20  
- P21–30  
- Adult  
