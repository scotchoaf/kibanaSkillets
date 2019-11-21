# Source-Destination Traffic Map

This visual is based on the Vega gallery example  [Airport Connections](https://vega.github.io/vega/examples/airport-connections/)

Source are shown as map circles. Hover over a circle shows all destination associations.

The added content includes:

* uses Kibana world map view
* Ability to adjust line thickness and color using UI inputs
* single click to see all lines visible for testing or full src-dst view

### Input variables

The following are the variables used in the Vega text.

+ ```index```: name of the Elasticsearch index (without the '*' at the end)

+ ```use_timeField```: does the data set have a timefield to use in filters

+ ```timefield```: time or date field used in the specific index allowing for
the ability to use the Kibana time filter

+ ```src_id```:  field for source locations such as country code or name

+ ```src_lon```:  source longitude value field

+ ```src_lat```:  source latitude value field

+ ```src_country```:  source country name for tooltip pop-up title

+ ```dst_id```:  field for destination locations such as country code or name

+ ```dst_lon```:  destination longitude value field

+ ```dst_lat```:  destination latitude value field

***NOTE***: text fields may require the use of
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
