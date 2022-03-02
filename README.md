# research_data
This repository shares the data in my researches published.

## Land surface temperature
- Land surface temperature on July 10, 2017, Beijing, China, retrieved from the Landsat 8 image with a spatial resolution of 30 m.<br />
  - Available at: https://drive.google.com/file/d/1emj4Wk7IhogBqoLmo9VbO7tLKIb6GrV0/view?usp=sharing<br />
  - Data citation: Zhao, J., Zhao, X., Liang, S., Zhou, T., Du, X., Xu, P. and Wu, D., 2020. Assessing the thermal contributions of urban land cover types. ***Landscape and Urban Planning***, 204, p.103927.<br />

## Surface parameters of urban green spaces (UGSs) in Beijing main city from 1984 to 2020
- Time series data including the normalized difference vegetation index (NDVI), land surface temperature (LST), evapotranspiration (ET) and albedo.<br />
  - Available at: https://drive.google.com/file/d/1X9-EcTeK3nPrNHvJWtMUhk-jRToSIg3F/view?usp=sharing<br />
  - Data citation: Zhao, J., Zhao, X., Liang, S., Wang, H., Liu, N., Liu, P. and Wu, D., 2021. Dynamic Cooling Effects of Permanent Urban Green Spaces in Beijing, China. ***Remote Sensing***, 13(16), p.3282.<br />

## Multi-Source Weather (MSWX) historical monthly meteorological product from 2000 to 2020
- High-resolution (0.1°), bias-corrected meteorological product based on ERA5 and CHELSA with global coverage from 1979 to now. Currently I only processed the data from 2000 to 2020.<br />
  - **Dataset access in Google Earth Engine (GEE)**<br />
  Image Collection id: projects/ee-jzhao-external-dataset/assets/raster/mswx/past/monthly<br />
  
  - **Usage**
  ```JavaScript
  var mswxMonthly = ee.ImageCollection('projects/ee-jzhao-external-dataset/assets/raster/mswx/past/monthly').filterDate('2020-07-01', '2020-08-01');
  var visualization = {
      bands: ['b1'],
      min: 0,
      max: 35,
      palette: [
          "#000080", "#0000D9", "#4000FF", "#8000FF", "#0080FF", "#00FFFF",
          "#00FF80", "#80FF00", "#DAFF00", "#FFFF00", "#FFF500", "#FFDA00",
          "#FFB000", "#FFA400", "#FF4F00", "#FF2500", "#FF0A00", "#FF00FF",
      ]
   };
   Map.setCenter(22.2, 21.2, 2);
   Map.addLayer(mswxMonthly, visualization, '2-m Air Temperature');
   ```
  - **Band specifics**
  
| Band Name | Description                                    | Unit |
| --------- | ---------------------------------------------- | ---- |
| b1        | 2-m air temperature                            | °C   |
| b2        | 2-m maximum daily air temperature at           | °C   |
| b3        | 2-m minimum daily air temperature at           | °C   |
| b4        | surface pressure                               | Pa   |
| b5        | precipitation                                  | mm   |
| b6        | 2-m relative humidity                          | %    |
| b7        | 2-m specific humidity                          | g/g  |
| b8        | downward longwave radiation                    | W/m<sup>2</sup> |
| b9        | downward shortwave radiation                   | W/m<sup>2</sup> |
| b10       | 10-m wind speed                                | m/s |

  - MSWX is released under the Creative Commons Attribution-NonCommercial 4.0 International ([CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)) license. Please [contact the authors](http://www.gloh2o.org/contact/) if you are affiliated with a commercial entity and want to use MSWX. If you do not have a commercial affiliation and you intend to use the product for non-commercial purposes, please [send the authors a request](http://www.gloh2o.org/mswx/) (request frame can be found in the Data license section at the website). You will receive a link to the Google Drive containing MSWX once your request has been approved. 
  - Data citation: Beck, H.E., van Dijk, A.I., Larraondo, P.R., McVicar, T.R., Pan, M., Dutra, E. and Miralles, D.G., 2021. MSWX: global 3-hourly 0.1° bias-corrected meteorological data including near real-time updates and forecast ensembles. ***Bulletin of the American Meteorological Society***, pp.1-55.<br />
