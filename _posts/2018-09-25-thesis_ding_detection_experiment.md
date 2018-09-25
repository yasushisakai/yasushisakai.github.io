---
title: ding experiments
layout: post
---

# ring bells

## 1. Bronze circular bell
  - from Crane
  - produced in Japan

## 2. Generic silver circular
  - no brand

## 3. Generic golden circular
  - produced in Japan

## 4. Oi bicycle bell
  - designed in Australia

## 5. Hubway bike bell

# detecting devices

- Motorola pure (2015)

- Nexus 5 (2013)


# target frequencies

| devices | 1. Bronze circular bell | 2. Generic Silver | 3. Generic Golden | 4. Oi | 5. Hubway |
| --- | --- | --- | --- | --- | --- |
| motorola  | 3609.375 | 2390.625 | 2484.375 | 2765.625 | 2953.125 |
| nexus5 | 3609.375 | 2390.625 | 2484.375 | 2765.625 | 2953.125 |

# what I want to know

## consistency between different phones

- peak frequency detection

Two devices used for catching the peak frequency, recorded in the same time/ring from the bell.


- ding detection

Two devices evaluated for ding detection, using same bell and same time.

## bike bell property

 A. The threshold of the slop of adjacent frequencies

 B. The threshold of the duration of the significant slope

 C. good limit between two dings to detect a double ding

 D. shortest overall ms for complete detection

# experiment

sound clips

- each bell have 5 samples of single dings in a quiet environment
- each bell having 10 samples of single dings in a noisy environment
- each bell have 5 samples of double dings in a quiet environment
- each bell having 10 samples of double dings in a noisy environment
- 20 samples of sound without any ding

recorded separately for both devices


