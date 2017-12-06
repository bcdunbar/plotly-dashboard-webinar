# Using Excel to Generate Online Dashboards in Plotly

## Contents

- [Crowdcast Webinar](#crowdcast-webinar)
- [Plotcon Workshops](#plotcon-workshops)
- [Tour of Plotly](#tour-of-plotly)
- [Data](#1-data)
- [Create a Chart](#2-create-a-chart)
  - [Average Happiness Choropleth](#21-average-happiness-choropleth)
  - [Average GDP Scatter Plot](#22-average-gdp-scatter-plot)
  - [World Happiness Table](#23-world-happiness-table)
- [Create a Dashboard](#3-create-a-dashboard)
  - [Add Charts](#31-add-charts)
  - [Style It](#32-style-it)

## Crowdcast Webinar

Click here to watch the [Crowdcast Webinar](https://www.crowdcast.io/e/using-excel-to-generate)

## Plotcon Workshops

Take part in [hands-on workshops](https://plotcon.plot.ly/) for some the fastest growing data visualization libraries. Next workshops in Montréal, Canada:

[Python Dash | February 17-18, 2018](https://plotcon.plot.ly/workshops/dash-master-class)

This two-day workshop will go over the foundations and guiding principles of dash, starting with simple examples on the first day and more advanced use cases on the second day. Each section of the Dash workshop will be focused around complete examples that the attendees can run on their own computers. Attendees will learn the principles of Dash by customizing these examples through gentle, interactive “challenges”.
This workshop is taught by the author of the Dash library itself, with help from other Dash solutions experts at Plotly.

[SQL & Dashboards | February 24-25, 2018](https://plotcon.plot.ly/workshops/sql-dashboards)

Falcon is a free, open-source SQL editor that features inline data visualization, the ability to edit charts in Plotly's Chart Studio, setup persistent connections and connect to a plethora of databases including RedShift, MySQL, PostgreSQL, IBM DB2, Impala, MS SQL, and SQLite.
In this workshop, Branden will walk you through how to use Falcon SQL Client to connect to databases, execute queries, create interactive and styled charts and embed them in dashboards and reports. By way of lectures, hands-on tutorials, and breakout sessions, attendees will learn best practices and modern data warehousing options.

[R, Shiny & DashR | March 3-4, 2018](https://plotcon.plot.ly/workshops/r-shiny-dash-r)

By the end of this workshop, you should be able to leverage interactive visualization techniques to perform/present data analysis tasks/findings using the R package plotly. Though it would be beneficial to have some prior knowledge of R and ggplot2, we do not require it, and as such, we avoid assuming pre-existing knowledge as much as possible. Furthermore, this workshop is not designed to make you an R programming expert – it’s designed to get you doing powerful things quickly regardless of your experience with R or programming in general.

## Tour of Plotly

[Chart Studio](https://plot.ly/online-chart-maker/) is Plotly's point-and-click, no coding required, chart editor/maker.

[Dashboards & Reports](https://plot.ly/dashboards/) is the place to build your interactive reports and dashboards.

Plotly has numerous APIs, including:
  - [JS](https://plot.ly/plotly-js-scientific-d3-charting-library/)
  - [Python](https://plot.ly/d3-js-for-python-and-pandas-charts/)
  - [R](https://plot.ly/d3-js-for-r-and-shiny-charts/)

[Dash](https://plot.ly/products/dash/) is Plotly's python framework for creating reactive and analytical web applications in pure python.

[Falcon SQL Client](https://plot.ly/database-connectors/) is Plotly's free and open-source SQL client, which enables you to connecto numerous databases, preview schemas, write queries, perform inline data viz, or to unlock the full power of plotly perform queries in the Chart Studio. Furthermore, you can setup persistent connections, which means that you plots and dashboards will update automatically.

[Spectacle Editor](https://plot.ly/powerpoint-online/) is Plotly's online drag-and-drop editor that facilitates the creation of slick and concise presentations.

## 1. Data

To get started, head to Plotly’s [Chart Studio](https://plot.ly/create/) and add your data. You have the option of typing directly in the grid, uploading your file, or entering a URL of an online dataset. For this tutorial, we'll use the World Happiness Dataset from the Sustainable Development Solutions Network. To begin, simply view the [dataset](https://plot.ly/~bdun9/2521/) and click **'Fork & Edit'**. The Chart Studio ought to open and you're all set to go.

![Fork and Edit](/images/choropleth/fork-and-edit.png)

Alternatively, navigate to the [Chart Studio](https://plot.ly/create/) and click **'Import'**, **'By URL'**, and then paste in the **URL** (https://raw.githubusercontent.com/bcdunbar/datasets/master/worldhappiness.csv).

![Add Data](/images/choropleth/add-data.png)

## 2. Create a Chart

To visualize World Hapiness from 2015 to 2017, we'll create three individual charts: (1) a average happiness choropleth map, (2) GDP per capita scatter plot and (3) a table to visualise the data. In the section below, we'll look at how to make each of the charts.

### 2.1. Average Happiness Choropleth

##### 2.1.1. Create
Now that we have the data added to the grid, we can select our chart type. To do so, select *Graph* on the left-hand side, then *Create*. Click *Chart Type*, and **Choropleth** from the *Maps* column.

![Chart Type](/images/choropleth/chart-type.png)

Now to populate the graph with data, in the *Locations* and *Values* dropdown select **Country** and **HappinessScore**, respectively. Additionally, set **Country Names** in the *Locations Format* dropdown, **World** in the *Map Regions*, and set the *Projections* to **Distance Preserving (Equirectangular)**. You ought to note that countries aren't defined yet as we need to aggregate the data.

![Trace Values](/images/choropleth/trace-values.png)

##### 2.1.2. Aggregate
Now, for this choropleth we want to plot the average number of confirmed cases. Therefore, we need to aggregate the data. To do so, open *Aggregate*, select **Country** as the *Group By Column*, and **HappinessScore** as the *Trace*. Then, set *Z* value to **avg**.

![Aggregate](/images/choropleth/aggregate.png)

##### 2.1.3. Traces
To style, under *Style* click *Traces*. Here, we can change the colorscale by clicking the **yellow/blue** palette (around the 3rd from the left).

![Trace Styles](/images/choropleth/trace-style.png)

##### 2.1.4. Layout
Now that we've finished styling the trace, click *Layout* to style the background, fonts, and margins. To complete the former, select *Canvas* and set **#444444** as the *Margin Color*.

![Canvas](/images/choropleth/canvas.png)

Next, navigate to the *Layout* tab, open *Margins and Paddings* and set all the values to **0** to make it full width and height.

![Margins](/images/choropleth/margins.png)

In choropleth maps, we have *Geo Style* and *Geo Layout*. To alter the former, select *Geo Style* and set *Land* to **Show**. Set *Color* to **#444444**. Next, set *Oceans* to **Show** and *Color* **#444444**; *Country* to **Show** and *Color* **#444444**. Lastly, *Frame* to **Hide**.

![Geo Style](/images/choropleth/geo-style.png)

Next, in *Geo Layout* you can define attributes such as *Map Scope*, *Projection*, *Rotation*, *Scale*, and *Map Resolution*. In this tutorial, we'll leave it as-is.

![Geo Layout](/images/choropleth/geo-layout.png)


##### 2.1.5. Color Bars

Finally, click *Color Bars* under *Style* and open *Labels*. Here, set the *Typeface* to **Raleway** and the *Font Color* to **#FFFFFF**.

![Color Bar Size](/images/choropleth/color-bar-labels.png)


##### 2.1.6. Save
Congrats, your chart is complete! Click **Save** on the left-hand side of the screen. In the pop-up, enter your filename and select either **Public** (visible to all) or **Private Link** (visible only to those who you share the link with) and hit **Save**. Since these plots are destined for a dashboard, they can't be set to private.

![Save](/images/choropleth/save.png)

### 2.2. Average GDP Scatter Plot
Using the same grid as the previous plot, open the data in the Chart Studio.

##### 2.2.1. Create
Now that we have the data added to the grid, we can select our chart type. To do so, select *Graph* on the left-hand side, then *Create*. Click *Chart Type*, and **Scatter** from the *Business* column.

![Chart Type](/images/scatter/chart-type.png)

Now to populate the graph with data, in the *Locations* and *Values* dropdown select **Country** and **Economy_GDP_per_Capita**, respectively. Additionally, set **HappinessScore** in the *Size* and *Color* dropdowns.

![Trace Values](/images/scatter/trace-value.png)

##### 2.2.2. Aggregate
Like previously, we need to aggregate the data. To do so, open *Aggregate*, select **Country** as the *Group By Column*, and **Economy_GDP_per_Capita** as the *Trace*. Then, set *Y*, *Marker Size* and *Marker Color* to **avg**.

![Aggregate](/images/scatter/aggregate.png)

##### 2.2.3. Traces
To style, under *Style* click *Traces*. Here, we can change the colorscale by clicking the **blue/yellow** palette (around the 3rd from the left).

![Trace Styles](/images/scatter/trace-styles.png)

##### 2.2.4. Layout
Now that we've finished styling the trace, click *Layout* to style the background, fonts, and margins. To complete the former, select *Canvas* and set **#444444** as the *Margin Color*.

![Canvas](/images/scatter/canvas.png)

Below *Canvas*, open the *Title and Fonts* box and under *Global Font*, set *Typeface* to **Raleway**, *Font Size* to **12**, and *Font Color* to **#FFFFFF**.

![Global Font](/images/scatter/global-font.png)

Next, navigate to the *Layout* tab, open *Margins and Paddings* and set the values to **10**, **120**, **80** and **0**, respectively.

![Margins](/images/scatter/margins.png)

##### 2.2.5. Axes
Moving on to the *Axes* tab, select *Title*. Remove the *X* title, then  click *Y* and set the title to **GDP per Capita**.

![Axes Titles](/images/scatter/axes-titles.png)

Next, navigate to *Lines*, click *All* and select **Hide** for all options. This will remove all lines including grid, horizontal and zero line.

![Lines](/images/scatter/lines.png)

Lastly, because we want to use the crossfilter feature with our dashboard open *Zoom* and select **Disable**.

![Zoom](/images/scatter/zoom.png)

##### 2.2.6. Save
Congrats, your chart is complete! Click **Save** on the left-hand side of the screen. In the pop-up, enter your filename and select either **Public** (visible to all) or **Private Link** (visible only to those who you share the link with) and hit **Save**. Since these plots are destined for a dashboard, they can't be set to private.

![Save](/images/scatter/save.png)

### 2.3. World Happiness Table
Using the same grid as the previous plot, open the data in the Chart Studio.


##### 2.3.1. Create
Now that we have the data added to the grid, we can select our chart type. To do so, select *Graph* on the left-hand side, then *Create*. Click *Chart Type*, and **Table** from the *Statistics* column.

![Chart Type](/images/table/chart-type.png)

For tables, you want to create your header names. To do so, in the 1dt spare column type in the header names: **Year**, **Country**, **Happiness Rank**, **Happiness Score** and **GDP per Capita**. Lastly, rename the column to **Headers**.

![Add Headers](/images/table/headers.png)

Now to populate the table with data, set the *Headers* dropwdown to **Headers**. Then, **Year**, **Country**, **Happiness Rank**, **Happiness Score** and **Economy_GDP_per_Capita** to the columns dropdown.

![Trace Values](/images/table/trace-values.png)


##### 2.3.2. Traces
To begin styling the table, click *Traces* under *Style*. In *Header*, set the *Fill Color* to **#444444**, *Font Color* to **#FFFFFF**, and *Border Color* to **#FFFFFF**. In *Cells*, the *Fill Color* to **#444444**, *Font Color* to **#FFFFFF**, and *Border Color* to **#FFFFFF**.

![Trace Styles](/images/table/trace-style.png)

##### 2.3.3. Layout
Next, navigate to the *Layout* tab, open *Canvas* and set the *Plot* and *Margin Color* to **#000000** to keep with the dark theme of the previous plots.

![Canvas](/images/table/canvas.png)

Next, open *Margins and Paddings* and set all the values to **10** to make the table just shy of full width and height.

![Margins](/images/table/margins.png)

##### 2.3.4. Save
Congrats, your chart is complete! Click **Save** on the left-hand side of the screen. In the pop-up, enter your filename and select either **Public** (visible to all) or **Private Link** (visible only to those who you share the link with) and hit **Save**. Since these plots are destined for a dashboard, they can't be set to private.

![Save](/images/table/save.png)

## 3. Create a Dashboard

With the charts completed and saved in your [home folder](https://plot.ly/organize/home), we can now create a dashboard by simply adding these charts, adjusting the layout, and styling the dashboard before sharing and interacting. To get started with creating a dashboard, hover over the *+Create* button and select **Dashboard** from the menu. Alternatively, open this [link](https://plot.ly/dashboard/create).

### 3.1. Add Charts

First, to add the Maximum Cases per Month Map, click *+Plot* in the bottom left corner of the screen. A new box ought to appear with the option to 'Add a Plot'. Click, the *'Your Files'* option and then in the pop-up select the **Average Happiness by Country** map we made earlier.

![Add Choropleth](/images/dashboard/add-plot.png)

Next, add the **Average GDP per Capita by Country** scatter plot following the same process. As we are making a fairly simple and straight forward dashboard, we can just leave this plot immediate below the previous map.

![Add Scatter](/images/dashboard/add-plot2.png)

Again, immediately below, add the **World Happiness Data Table**.

![Add Table](/images/dashboard/add-plot3.png)

Now that we have added all the plots to the dashboard, for each plot where it says, "Enter a title..." insert plot titles: **Average Happiness by Country**, **Average GDP per Capita by Country** and **World Happiness Data Table** in the same order as we added the plots. Your result ought to look like below.

![Add Plot Titles](/images/dashboard/add-titles.png)

### 3.2. Style It

Now that we have the structure of our dashboard, we can style it. To do so, navigate to the *settings icon* directly opposite the dashboard title. When hovering you ought to see the option settings from the menu.

![Settings](/images/dashboard/settings.png)

After clicking *settings*, a panel ought to appear from the right-hand side of the screen. Here, we have the option of headers, colors, text, layout, and filter. First, in *Headers*, we can set the title, add a logo, and multiple links. For this tutorial, add **World Happiness 2015-2017** to the *Title* text box. Next, let's add the Sustainable Development Solutions Network logo. We can do this by simply adding the URL for the logo PNG: **http://unsdsn.org/wp-content/themes/sdsn/assets/img/sdsn_logo_fc.png**. Also, we can add an link to the data source by typing the text **Data Source: World Happiness Report** and then in the *URL* box, enter **http://worldhappiness.report/**.

![Header](/images/dashboard/headers.png)

In the next tab, *Colors*, we can manipulate the background, borders, and text colors. As you can see, the dashboard has already added these by default. That said, keeping with our plot themes, we will set *Header Background*, *Page Background*, *Box Background*, *Box Border*, and *Box Header Background* to **#444444**. Then, set *Header Font Color* and *Box Header Font Color* to **#FFFFFF**.

![Colors](/images/dashboard/colors.png)

*Text*, the third settings option, allows you to control all things text, including font color, family, and size, as well as header styles and text box styles. Again, like the Colors tab, some values are defined. However, here, we'll set the *Font Family* to **Raleway**. Make the header font larger by selecting **2.2em** in the *Header Font Size* and, additionally, change the *Header Font Weight* to **300**.

![Text](/images/dashboard/text.png)

In *Layout*, you have the option of setting the page layout as either a dashboard or a report. Here, we'll leave it as the default dashboard setting. The last settings category, *Filter*, provides you with the option to enable or disable the Search Bar or the Crossfilter feature. For this tutorial, leave the *Search Bar* as-is but let’s enable the *Crossfilter* feature by selecting **Enable** (for more information about this feature see the next section).

![Filter](/images/dashboard/filter.png)

Congrats, your dashboard is complete! Click **Save** on in the bottom right-hand side of the screen. In the pop-up, enter your filename and select either **Public** (visible to all), or **Private Link** (visible only to those who you share the link with), or **Private** (visible only to you) and hit **Save**. .

![Save](/images/dashboard/save.png)
