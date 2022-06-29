# Baseline Algorithm Definition

Definition

### Retrieval Method

Subsection Text


### Forward Model

Subsection Text


### CIMR Level-1b re-sampling approach

Subsection Text


### Algorithm Assumptions and Simplifications

Subsection Text

### Level-2 end to end algorithm functional flow diagram

Subsection Text

### Functional description of each Algorithm step

Subsection Text

##### Mathematical description

The dry snow detection algorithm of the TSA product is based on the approach of {cite:t}`hall_2002` but applies updated empirically derived thresholds as implemented for the EUMETSAT H SAF snow status product H11 {cite:p}`pulliainen_2010`. The brightness temperature difference between the Ku and Ka-band is used to estimate snow depth (SD) as

$$
\text{SD} = R_c \cdot (T_B^{18H}-T_B^{37H}),
$$

with regression coefficient $R_c$ of 1.59 cm/K and brightness temperatures $T_B$.
For the algorithm in to detect dry snow, the following thresholds must be met:

$$
\begin{aligned}
\text{SD} &≥ 3.0~\text{cm}\\
T_B^{37V} &< 255~\text{K}\\
T_B^{37H} &< 250~\text{K}.
\end{aligned}
$$

The use of further CIMR channels for dry snow detection is under investigation.

##### Input data

SubSubsection Text

##### Output data

The snow maps are provided as EASE-Grid 2.0 North and South azimuthal projections, respectively, of 12.5 km resolution and use the pixel values given in {numref}`tab:TSA-values`. Data are available for download as NetCDF files in addition the corresponding quick-look PNG files.

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

##### Auxiliary data

SubSubsection Text

##### Ancillary data

SubSubsection Text

##### Validation process

SubSubsection Text


