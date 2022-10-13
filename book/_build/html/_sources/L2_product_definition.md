# Level-2 Product Definition

The Level-2 TSA product is obtained by processing Level-1B brightness temperatures to Level-2 terrestrial snow area.
The product is provided in netCDF format and contains the following variables:

(product_variables)=
| Variable name | Unit |
| --- | ---- |
| `terrestrial_snow_area` | 1 |
| `terrestrial_snow_area nan_flag` | 1 | 

The NaN flag is an 8-bit mask describing the cause for NaN values. It contains the following bits:
(product_flags)=
| Bit | Description |
| --- | ---- |
| 0 | No data |
| 1 | Open water |
| 2-8 | Reserved |

