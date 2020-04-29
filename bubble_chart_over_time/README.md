# Time-Based Bubble Chart using Vega-Lite

This visual is based on the tutorial from the [Vega-Lite Gallery: Bubble Chart](https://vega.github.io/vega-lite/examples/circle_natural_disasters.html)

Bubble charts are circles mapped over time and grouped by a category. The size
of the bubble is determine by a count field in the data.

Elasticsearch supports dots in name whereas Vega isn't 'dot friendly.' Therefore
name aliases are used in transforms to get around the dot naming issue

### Input variables

Most of the Vega input is the same with the inclusion of a few jinja variables
to update the input specific to the user's deployment.

+ ```chartTitle```: title displayed at the top of the chart

+ ```index```: name of the Elasticsearch index (without the '*' at the end)

+ ```timefield```: time or date field used in the specific index allowing for
the ability to use the Kibana time filter

+ ```bubbleGroup```: field used to create bubble categories

+ ```bubbleGroupAlias```: alias for the bubbleGroup field name

+ ```countField```: numberic field used to set bubble size

+ ```countFieldAlias```: alias for the countField field name

+ ```legendTitle```: legend title associated to bubble values

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
