# Sankey 2 Stack Visual using Vega

This visual is based on the tutorial from the [Sankey Vega Elastic blog](https://www.elastic.co/blog/sankey-visualization-with-vega-in-kibana)
authored by Yuri Astrakhan.

The sankey visualization uses two associated values from a dataset and
creates a path-based visual of the values as left and right stacks in
the chart. You can also click on a specific stack values to see its
specific associations.

### Input variables

Most of the Vega input is the same with the inclusion of a few jinja variables
to update the input specific to the user's deployment.

+ ```index```: name of the Elasticsearch index (without the '*' at the end)

+ ```use_timeField```: does the data set have a timefield to use in filters

+ ```timefield```: time or date field used in the specific index allowing for
the ability to use the Kibana time filter

+ ```stack_1_field```: index field used for the left side of the chart

+ ```stack_1_label```: name to use for the stack1 chart axis label

+ ```stack_2_field```: index field used for the right side of the chart

+ ```stack_2_label```: name to use for the stack2 chart axis label

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
