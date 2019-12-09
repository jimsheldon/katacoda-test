ElastAlert has many
[rule types](https://elastalert.readthedocs.io/en/latest/ruletypes.html)
available, in this example we will use the
[flatline](https://elastalert.readthedocs.io/en/latest/ruletypes.html#flatline)
rule type.

In the editor view on the right, double-click the `example_flatline.yml` file.
Let's examine each line of this file:

### Common Options

These options are common to any ElastAlert rule.

<pre class="file" data-filename="example_flatline.yml" data-target="replace">
name: Flatline Example
</pre>

**name:** The name of the rule. This *must be unique across all rules*. The name will be
used in alerts and used as a key when writing and reading search metadata back
from Elasticsearch.

<pre class="file" data-filename="example_flatline.yml">
type: flatline
</pre>

This can be any supported
[rule type](https://elastalert.readthedocs.io/en/latest/ruletypes.html).

<pre class="file" data-filename="example_flatline.yml">
index: heartbeat
</pre>

**index:** The name of the index that will be searched. Wildcards can be used here, such
as: `index: logstash-someapp-*`.


<pre class="file" data-filename="example_flatline.yml">
filter:
- query:
    query_string:
      query: "host: elasticsearch"
</pre>

**filter:** A list of Elasticsearch query DSL filters that is used to query Elasticsearch.
For more information writing filters, see
[Writing Filters](https://elastalert.readthedocs.io/en/latest/recipes/writing_filters.html#writingfilters).

In this example, each heartbeat document has the field `host: elasticsearch`, so
we can write our alert based on that.

<pre class="file" data-filename="example_flatline.yml">
alert:
- debug
</pre>

**alert:** Each rule may have any number of
[alerts](https://elastalert.readthedocs.io/en/latest/ruletypes.html#alerts)
attached to it.

The [debug](https://elastalert.readthedocs.io/en/latest/ruletypes.html#debug)
alert logs to standard output.

### Flatline Options

These options are specific to flatline rules.

<pre class="file" data-filename="example_flatline.yml">
threshold: 5
</pre>

**threshold:** The minimum number of events for an alert *not* to be triggered.

<pre class="file" data-filename="example_flatline.yml">
timeframe:
  seconds: 30
</pre>

**timeframe:** The time period that must contain less than `threshold` events.
