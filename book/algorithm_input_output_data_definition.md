# Algorithm Input and Output Data Definition (IODD)

The processing of the TSA product requires TB data in swath projection. Even though the application of auxiliary data is not mandatory, it is highly recommended to mask out known water bodies and latitudes which do not experience snow cover. 

## Input data

Daily Level-2 brightness temperature data are the main input, requiring data of the Ku-band of horizontal polarisation and of the Ka-band of both polarisations.
Brightness temperature data of all other bands and polarisations may be necessary for future TSA product versions.

```{important}
If available, early morning satellite data is preferred as input over late afternoon data in order to minimise effects of liquid water within the snowpack.
```

| Field | Description | Shape/Amount |
| ---   | ----------- | ------------ |
| L1B TB Ku-band | L1B Brightness Temperatures at 18.7 GHZ (H polarisation) | full swath or swath section (Nscans, Npos) |
| L1B TB Ka-band | L1B Brightness Temperatures at 36.5 GHZ (H and V polarisation) | full swath or swath section (Nscans, Npos) |

## Output data

| Field | Description | Shape/Amount |
| ----- | ----------- | ------------ |
| L2 TSA | Terrestrial Snow Area: 0 for 'snow-free', 1 for 'snow-covered land', NaN otherwise  | full swath or swath section (Nscans, Npos) |
| NaN Flag | Reason for NaN value: 'no data', 'open water' | full swath or swath section (Nscans, Npos) |

## Auxiliary data

* Land/water information (collocated to swath)
* Latitude information of the Northern Hemisphere (collocated to swath)

## Ancillary data

NA
