---
title: CYBERSEC2020(II) - Side-Channel
date: 2020-08-19 09:42:47
tags: #CYBERSEC2020
---
informed by Jiun-Peng Chen, NTU

# Introduction

> Side-channel attack is any attack based on information gained from the physical implementation of a cryptosystem, rather than brute force or theoretical weakness in the algorithms. (compare cryptanalysis)

> For example, timing, power consumption, electromagnetic leaks, or even sound can provide an extra source of information, which can be exploited to break the system.


## Attack on Implementations
### Invasive
-   Microprobing
-   Reverse Engineering

### Semi-Invasive
-   UV light
-   X-rays
-   Lasers

### Non-Invasive
-   Side-Channel Analysis

## Side-Channel Analysis
### Static power consumption
> There is no direct connection from VDD to GND but a small leakage current

### Dynamic power consumption
> For example, from 0 to 1, current charges the capacitor at Vout through PMOS, and then the short-circuit current occurs in a short period when PMOS and NMOS both conduct.