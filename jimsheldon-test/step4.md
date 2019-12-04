Start elastalert:
```
elastalert --config config.yml --debug --rule example_flatline.yml
```{{execute}}

You should see output similar to:
```
INFO:elastalert:Note: In debug mode, alerts will be logged to console but NOT actually sent.
                To send them but remain verbose, use --verbose instead.
INFO:elastalert:Starting up
INFO:elastalert:Queried rule Flatline Example from 2019-12-04 22:20 UTC to 2019-12-04 22:21 UTC: 11 / 11 hits
INFO:elastalert:Skipping writing to ES: {'hits': 11, 'matches': 0, '@timestamp': '2019-12-04T22:21:32.391805Z', 'rule_name': 'Flatline Example', 'starttime': '2019-12-04T22:20:32.320593Z', 'endtime': '2019-12-04T22:21:32.320593Z', 'time_taken': 0.07119917869567871}
INFO:elastalert:Ran Flatline Example from 2019-12-04 22:20 UTC to 2019-12-04 22:21 UTC: 11 query hits (0 already seen), 0 matches, 0 alerts sent
INFO:elastalert:Sleeping for 9.824992 seconds
```

Since the heartbeat process is writing more than 5 documents that match our
query every 30 seconds, no alert is triggered.

Now let's stop the heartbeat process
