# plotvuer 

[![npm version](https://badge.fury.io/js/%40tehsurfer%2Fplotvuer.svg)](https://badge.fury.io/js/%40tehsurfer%2Fplotvuer)
[![Maintainability](https://api.codeclimate.com/v1/badges/8dd727f153711aaae6e1/maintainability)](https://codeclimate.com/github/Tehsurfer/plotvuer/maintainability)

This project aims to process and display csv files as graphs in the vue framework

Demo the site functionality of this app [here](https://plotvuer-demo.herokuapp.com/)

![demo](https://user-images.githubusercontent.com/37255664/73617045-a3231e00-467f-11ea-90bd-b1074acd26b3.gif)

## Project installation
```
npm i @tehsurfer/plotvuer
```


## Project setup
```
npm install
npm run serve
```

### Compiles and minifies for production
```
npm run build-bundle
```

## How to use
Include the package in your script.
```javascript
import '@tehsurfer/plotvuer'
import '@tehsurfer/plotvuer/dist/plotvuer.css'
```

The snippet above registers the Plotvuer component into the global scope.
You can now use the Plotvuer in your vue template as followed:
```html
<PlotVuer :url="csvfile.csv"></PlotVuer>
```
_Optional Parameters_: 
 1. Type of plot - Use 'scatter, 'heatmap', or 'barplot'.
 2. Plot filters - Filters will preload the plot with the supplied data
```html
<PlotVuer :url="csvfile.csv" :plotType="'scatter'" :xAxisFilter="['step1', 'step2']"></PlotVuer>
```

`url` should be the variable/string containing the url of a csv file.

`plotType` is the type of plot we wish to see the data as one of: `'heatmap', 'scatter', 'barplot'` 

`xAxisFilter` and `yAxisFilter` provide filters to load the plot with selected filters displayed.


## CSV file formatting

`plotvuer` will load and csv file that follow the form of headers on first row and coloumn and if data is time based, rows will be assumed to be time dependant. 

### Example 1. Heatmap data

|               | Gene 1  | Gene 2 | 
| :------------ |:--------|  ------| 
| Sample 1      | -1.54 | -3.40 |
| Sample 2      | 0.68       |   1.22 |
| Sample 3      | 0.05      |    0.66 |


### Example 2. Timeseries data


| time (seconds)| Sweep 0_Membrane Potential (mV) | 
| :------------ |:--------|  
| 0     | -70.12939453 | 
| 0.0002    | -70.12939453     |
| 0.0004      | -70.34301758      | 
