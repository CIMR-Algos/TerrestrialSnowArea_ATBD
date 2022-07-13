# Baseline Algorithm Definition

Definition

## Retrieval Method

Subsection Text


## Forward Model

Subsection Text


## CIMR Level-1b re-sampling approach

Subsection Text


## Algorithm Assumptions and Simplifications

Subsection Text

## Level-2 End to End Algorithm Functional Flow Diagram

```{figure} ./figures/L2-algorithm.png
--- 
name: flow-diagram
width: 450px
---
Functional flow diagram of the Level-2 end to end algorithm of the TSA product.
```

## Functional description of each Algorithm step

Step 1: Mapping of L1B brightness temperatures to swath projection.

Step 2: Application of dry snow detection approach to gridded brightness temperatures.

Step 3: Output of L2 TSA maps.

Step 4: Optional masking e.g. land/water or latitude masking.

### Mathematical description

The dry snow detection algorithm of the TSA product is based on the approach of {cite:t}`hall_2002` but applies updated empirically derived thresholds as implemented for the EUMETSAT H SAF snow status product H11 {cite:p}`pulliainen_2010`. The brightness temperature difference between the Ku and Ka-band is used to estimate snow depth (SD) as

```{math}
:label: TB_diff
\text{SD} = R_c \cdot (T_B^{18H}-T_B^{37H}),
```

with regression coefficient $R_c$ of 1.59 cm/K and brightness temperatures $T_B$, where the superscripts indicate the frequency and polarisation.
For the algorithm in {eq}`TB_diff` to detect dry snow, the following thresholds must be met:

```{math}
\begin{aligned}
\text{SD} &≥ 3.0~\text{cm}\\
T_B^{37V} &< 255~\text{K}\\
T_B^{37H} &< 250~\text{K}.
\end{aligned}
```

The use of further CIMR channels for dry snow detection is under investigation.

### Input data

SubSubsection Text

### Output data

The snow maps are provided in swath projection and use the pixel values given in {numref}`tab:TSA-values`. Data are available for download as NetCDF files in addition the corresponding quick-look PNG files.

```{list-table} Snow map values
:header-rows: 1
:name: tab:TSA-values

* - Value
  - Label
* - -3
  - outside coverage area
* - -2
  - no data
* - -1
  - open water
* - 0
  - snow-free land
* - 1
  - snow-covered land
```

### Auxiliary data

SubSubsection Text

### Ancillary data

Ancillary data include a static water mask in order to have a consist definition of land and water grid cells. Furthermore, latitudes that fall outside the area of interest are masked out in order to avoid false positive snow cells. For the Northern Hemisphere all latitudes at and below 40° N are masked out, and for the Southern Hemisphere latitudes at and below x° S are affected. 

### Validation process

SubSubsection Text


