# 3-Level Circle Packing Visual using Vega

This visual is based on the tutorial from the [Vega Gallery: Cicle Packing](https://vega.github.io/vega/examples/circle-packing/)

Circle packing uses a nest transform to show 3-level grouping of the data.
A tooltip pop-up gives the value associated to a selected circle.

### Input variables

Most of the Vega input is the same with the inclusion of a few jinja variables
to update the input specific to the user's deployment.

+ ```index```: name of the Elasticsearch index (without the '*' at the end)

+ ```use_timeField```: does the data set have a timefield to use in filters

+ ```timefield```: time or date field used in the specific index allowing for
the ability to use the Kibana time filter

+ ```outerCircle_field```: outer most circle grouping

+ ```middleCircle_field```: middle level circle grouping

+ ```innerCircle_field```: inner most circle grouping

***NOTE***: The text fields may require the use of
```.keyword``` to be used in this vega visual.

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
