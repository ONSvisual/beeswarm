# Beeswarm plots
Templated version of beeswarm plots

|[Plain beeswarm](#plain)|[Group beeswarm](#group)|
:-----:|:-----:
![Plain beeswarm](https://user-images.githubusercontent.com/2945099/48057973-3df72900-e1ad-11e8-92be-79d24393be8b.png)|![Group beeswarm](https://user-images.githubusercontent.com/2945099/48057972-3d5e9280-e1ad-11e8-8f5b-74b1a962b725.png)

|[Multiple beeswarm](#multiple)|[Accurate plain beeswarm](#accurateplain)|
:-----:|:-----:
![Multiple beeswarm](https://user-images.githubusercontent.com/2945099/48057971-3d5e9280-e1ad-11e8-8435-94bd07be5f20.png)|![Accurate beeswarm](https://user-images.githubusercontent.com/2945099/48057970-3d5e9280-e1ad-11e8-9a5c-46c37a3f1bb2.png)

The files for each chart should be in the following format:

![folder structure](https://user-images.githubusercontent.com/2945099/48058602-bf02f000-e1ae-11e8-900f-6cb4d03edffa.png)

The config file contains all the variables which you can adjust. Data.csv contains the data for your graph. The lib folder contains javascript libraries used.

## <a name="plain"></a>Plain beeswarm

This template uses force layout to calculate position, which isn't accurate to the data values. If you are looking for that try the [accurate plain beeswarm](#accurateplain) template.

### Data file
Save your data as a `.csv` file in the following format

| unique  | value |
| ------- | ----- |
| Germany | 12    |
| France  | 23    |
| Italy   | 15    |

### Config

Edit the `config.json` with your favourite text editor.

#### essentials

These contain the main variables which the chart will need and will possibly need changing for each new chart.

```"graphic_data_url": "data.csv"```

Tells the chart the filename for the data.

```"colour_palette": "#008080"```

Sets the colour for all the dots

```"sourceText":["Statistics"]```

Sets the text at the bottom of the chart

```"xAxisLabel":"% hrte"```

Sets the label for the x-axis

```"xAxisScale":[0,100] ```

Sets the scale for the x-axis. This can be set to `auto` to automatically find the highest or lowest numbers in the data or set manually with an array, e.g. `[0,100]`.

```"svgheight":200```

Sets the height of the svg. This is important as the beeswarm uses force layout to calculate the position of the dots. If the dots are outside of the svg, it can't handle the calculations so will break and display nothing. This is the first thing you should adjust if you see nothing. Also beware that in mobile view that the dots will cluster closer together so will be higher and may be outside the svg.

#### optional

```"mobileBreakpoint" : 610 ```

Set the width for the mobile breakpoint. This only affect the number of ticks displayed.

```"x_num_ticks_sm_md" : [6,10]```

Set the preference for number of ticks on x-axis. This can be overridden by D3.

## <a name="group"></a>Group beeswarm

### Data file
Save your data as a `.csv` file in the following format. The id field refers to the group for that value. All values for that group will be coloured in a separate colour. 

| id      | unique  | value |
| ------- | ------- | ----- |
| Europe1 | Germany | 12    |
| Europe2 | France  | 23    |
| Europe2 | Italy   | 15    |

### Config

Edit the `config.json` with your favourite text editor.

#### essentials

These contain the main variables which the chart will need and will possibly need changing for each new chart.

```"graphic_data_url": "data.csv"```

Tells the chart the filename for the data.

```"colour_palette": ["#66c2a5","#fc8d62","#8da0cb","#e78ac3","#a6d854","#ffd92f"]```

Sets the colour for each group of dots. You need as many colours as the groups in your data. 

```"sourceText":["Statistics"]```

Sets the text at the bottom of the chart

```"xAxisLabel":"% hrte"```

Sets the label for the x-axis

```"xAxisScale":[0,100] ```

Sets the scale for the x-axis. This can be set to `auto` to automatically find the highest or lowest numbers in the data or set manually with an array, e.g. `[0,100]`.

```"svgheight":200```

Sets the height of the svg. This is important as the beeswarm uses force layout to calculate the position of the dots. If the dots are outside of the svg, it can't handle the calculations so will break and display nothing. This is the first thing you should adjust if you see nothing. Also beware that in mobile view that the dots will cluster closer together so will be higher and may be outside the svg.

#### optional

```"mobileBreakpoint" : 610 ```

Set the width for the mobile breakpoint. This only affect the number of ticks displayed.

```"x_num_ticks_sm_md" : [6,10]```

Set the preference for number of ticks on x-axis. This can be overridden by D3.

## <a name="multiple"></a>Multiple beeswarm

### Data file
Save your data as a `.csv` file in the following format. The id field refers to the group for that value. All values of a certain group will appear together.

| id      | unique  | value |
| ------- | ------- | ----- |
| Europe1 | Germany | 12    |
| Europe2 | France  | 23    |
| Europe2 | Italy   | 15    |

### Config

Edit the `config.json` with your favourite text editor.

#### essentials

These contain the main variables which the chart will need and will possibly need changing for each new chart.

```"graphic_data_url": "data.csv"```

Tells the chart the filename for the data.

```"colour_palette": ["#66c2a5","#fc8d62","#8da0cb","#e78ac3","#a6d854","#ffd92f"]```

Sets the colour for each group of dots. You need as many colours as the groups in your data. 

```"sourceText":["Statistics"]```

Sets the text at the bottom of the chart

```"xAxisLabel":"% hrte"```

Sets the label for the x-axis

```"xAxisScale":[0,100] ```

Sets the scale for the x-axis. This can be set to `auto` to automatically find the highest or lowest numbers in the data or set manually with an array, e.g. `[0,100]`.

```"heightperstrip":55,```
Sets the height of each strip of dots. This is important as the beeswarm uses force layout to calculate the position of the dots. If the dots are outside of the svg, it can't handle the calculations so will break and display nothing. This is the first thing you should adjust if you see nothing. Also beware that in mobile view that the dots will cluster closer together so will be higher and may be outside the svg.

```"dotradius":3```
Sets the size of the dots.

#### optional

```"mobileBreakpoint" : 610 ```

Set the width for the mobile breakpoint. This only affect the number of ticks displayed.

```"x_num_ticks_sm_md" : [6,10]```

Set the preference for number of ticks on x-axis. This can be overridden by D3.

## <a name="accurateplain"></a>Accurate plain beeswarm

Use this template if you need your dots to be accurate to the data values, for example dots above a certain value are coloured a different colour.

### Data file
Save your data as a `.csv` file in the following format

| unique  | value |
| ------- | ----- |
| Germany | 12    |
| France  | 23    |
| Italy   | 15    |

### Config

Edit the `config.json` with your favourite text editor.

#### essentials

These contain the main variables which the chart will need and will possibly need changing for each new chart.

```"graphic_data_url": "data.csv"```

Tells the chart the filename for the data.

```"colour_palette": "#008080"```

Sets the colour for all the dots

```"sourceText":["Statistics"]```

Sets the text at the bottom of the chart

```"xAxisLabel":"% hrte"```

Sets the label for the x-axis

```"xAxisScale":[0,100] ```

Sets the scale for the x-axis. This can be set to `auto` to automatically find the highest or lowest numbers in the data or set manually with an array, e.g. `[0,100]`.

```"svgheight":200```

Sets the height of the svg. This is important as the beeswarm uses an algorithmto calculate the position of the dots. If the dots are outside of the svg, it can't handle the calculations so will break and display nothing. This is the first thing you should adjust if you see nothing. Also beware that in mobile view that the dots will cluster closer together so will be higher and may be outside the svg.

#### optional

```"mobileBreakpoint" : 610 ```

Set the width for the mobile breakpoint. This only affect the number of ticks displayed.

```"x_num_ticks_sm_md" : [6,10]```

Set the preference for number of ticks on x-axis. This can be overridden by D3.