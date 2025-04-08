---
name: Licenses Dataset Analysis
tools: [Python, HTML, vega-lite]
image: assets/pngs/cars.png
description: Analyzing the licenses dataset for HW 5.1.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

### Plot 1: Bar Chart of License Types

<vegachart schema-url="{{ site.baseurl }}/assets/json/license_bar1.json" style="width: 100%"></vegachart>

This plot contains a bar chart of license types and their respective counts. Using `mark_bar()` to create a bar chart, the y-axis was 
encoded with counts, and the x-axis was encoded with license types sorted by counts. The license types were colored with the `category10` 
color scheme because of the distinct colors present, which is a good choice to represent distinct categories. To obtain the relevant data, 
I transformed the original dataset by grouping by license type and counting `_id`, along with some other minor reformatting. This is not 
an interactive plot, but a pan/zoom feature has been added to visualize the wide disparities between counts.

### Plot 2: Bar Chart of License Types by License Status

<vegachart schema-url="{{ site.baseurl }}/assets/json/license_bar2.json" style="width: 100%"></vegachart>

This plot contains a bar chart of license types and their respective counts for a specified license status. Using `mark_bar()` to create
a bar chart, the y-axis was encoded with counts, and the x-axis was encoded with license types sorted by counts. This was done after
filtering the data set by a specific license status through `transform_filter()`. The license types were colored with the `sinebow`
color scheme because of the distinct colors present, which is a good choice to represent distinct categories. To obtain the relevant data,
I transformed the original dataset by grouping by both license status and license type while counting `_id`, along with some other minor
reformatting. This plot is interactive and takes the relevant data and applies a `transform_filter` by a license status dropdown 
`status_dropdown`, selecting rows of data with `status_select`. A pan/zoom feature has been added to visualize the wide disparities between counts.

<!-- these are written in a combo of html and liquid --> 
<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/licenses_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="..." text="The Analysis" %}
</div>