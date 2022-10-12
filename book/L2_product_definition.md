# Level-2 Product Definition

The Level-2 TSA product is obtained by processing Level-1B brightness temperatures to Level-2 terrestrial snow area.
The product is provided in the native grid of the CIMR instrument at L-band frequency, which means it contains 135
samples per scan. Multiplied by the number of scans for each orbit gives the
number of retrieved ice thickness values per orbit. The product is provided in netCDF format and contains the
following variables:

(product_variables)=
| Variable name | Unit | Dimension |
| --- | ---- | ---| 
| `terrestrial_snow_area` | 1 | n_scans * n_samples_earth |
| `terrestrial_snow_area nan_flag` | 1 | n_scans * n_samples_earth| 


The dimension follow the definition of the original CIMR L1b product.

The NaN flag is an 8-bit mask describing the cause for NaN values. It contains the following bits:
(product_flags)=
| Bit | Description |
| --- | ---- |
| 0 | No data |
| 1 | Open water |
| 2-8 | Reserved |

