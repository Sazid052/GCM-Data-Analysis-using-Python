# Climate Data Analysis using Python

This repository contains Python code for analyzing and visualizing climate data from CMIP6 model outputs. The code processes netCDF files to extract temperature data, clips it using a shapefile for specific geographic regions, and generates various plots such as temperature distribution, location-wise mean temperature, spatial temperature trends, and time series data.

## Requirements
To run this code, you need to install the following Python libraries:
- `netCDF4`
- `cartopy`
- `xarray`
- `rioxarray`
- `geopandas`
- `shapely`
- `matplotlib`
- `numpy`

You can install these packages using pip:
```bash
## Data Description
- **Input Data**: CMIP6 netCDF files containing temperature variables (`tasmax`), with spatial dimensions (longitude, latitude) and a time dimension.
- **Shapefiles**: Used to clip the data for a specific geographic region, such as the Dhaka or Chattogram division in Bangladesh.

## Code Overview
1. **Loading Data**: 
   - The code starts by loading netCDF files from the specified folder and reading the temperature data (`tasmax`).
   - It renames the longitude and latitude variables for compatibility with `rioxarray`.

2. **Clipping Data**: 
   - The climate data is clipped to a specific region using a shapefile, which defines the geographic boundary.

3. **Data Conversion**:
   - The temperature data is converted from Kelvin to Celsius.
   - The data is merged along the time dimension for further analysis.

4. **Visualizations**:
   - **Temperature Distribution**: Plots the temperature distribution over the specified region for a given day.
   - **Location-wise Mean Temperature**: Calculates and visualizes the mean temperature across all time steps for each location.
   - **Spatial Trend Analysis**: Computes the trend of temperature change over time for each spatial location using linear regression.
   - **Time Series Data**: Converts the merged data into a pivot table and exports it as a CSV for further analysis.

## Usage
1. Update the `data_folder` and `shapefile` paths to your local directories where the netCDF files and shapefiles are stored.
2. Customize the longitude and latitude bounds (`ax.set_extent`) to focus on the desired region.
3. Run the script to generate the plots and export time series data.

## Examples
### Temperature Distribution
- The code generates a map of average temperature for a specific date, clipped to the Chattogram division:

### Location-wise Mean Temperature
- The code calculates the mean temperature over time for each location and visualizes it on a map:

### Spatial Trend Analysis
- The code performs a linear regression to estimate the trend in temperature over the entire time series for each location:

## Output
- The generated plots are displayed and can be saved manually.
- The time series data is exported to a CSV file named `precipitation_time_series.csv`.

## Notes
- Ensure the netCDF files are named consistently for proper loading and merging.
- Adjust the CRS (Coordinate Reference System) as needed to match your shapefile.
