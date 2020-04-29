# Scatter Plot with Dynamic Axes

This visual is based on the Vega gallery example  [Zoomable Scatter Plot Example](https://vega.github.io/vega/examples/zoomable-scatter-plot/)

The reference scatter plot allows the user to both zoom and pan using mouse actions.

The added content includes:

* category coloring of data points
* circle sizing based on a named field value
* legends for the above category and sizing
* tooltip pop-up providing circle context

Elasticsearch supports dots in name whereas Vega isn't 'dot friendly.' Therefore
name aliases are used in transforms to get around the dot naming issue

### Input variables

The following are the variables used in the Vega text. All are required
except for the 2 tooltip fields.

+ ```index```: name of the Elasticsearch index (without the '*' at the end)

+ ```use_timeField```: does the data set have a timefield to use in filters

+ ```timefield```: time or date field used in the specific index allowing for
the ability to use the Kibana time filter

+ ```aggField```:  used for each circle representation

+ ```aggFieldAlias```:  alias name for aggField

+ ```xAxisField```:  field for x-axis scatter plot values

+ ```xAxisFieldAlias```:  alias name for xAxisField

+ ```yAxisField```:  field for y-axis scatter plot values

+ ```yAxisFieldAlias```:  alias name for yAxisField

+ ```colorByField```: field to color circles by category

+ ```colorByFieldAlias```: alias name for colorByField

+ ```includeSize```: dropdown to select if field sizes set by a field value

+ ```sizeByField```: field used to set circle sizes

+ ```sizeByFieldAlias```: alias name for sizeByField

***NOTE***: The text fields may require the use of
```.keyword``` to be used in this vega visual. This is included in the template
where required.

### Kibana and long URLs

If you get a browser error due to the length of the URL, you can enable
state:storeInSessionStorage in the Kibana management page. The default is
to have disabled, setting = False.

From the [Kibana docs for Advanced Options:](https://www.elastic.co/guide/en/kibana/current/advanced-options.html)

```state:storeInSessionStorage```

[experimental] Kibana tracks UI state in the URL, which can lead to problems
when there is a lot of information there and the URL gets very long. Enabling
this will store parts of the state in your browser session instead, to keep
the URL shorter.
