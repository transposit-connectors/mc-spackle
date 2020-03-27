# Investigating Transposit Staging (on AWS)

## What are you trying to do?

If you've ever heard the phrases

... _"Is anyone else having trouble logging into `staging`?"_

... _"Is `staging` really slow right now?"_

... _"Can someone help me debug this failure on `staging`? This is the *request-id*."_

then this runbook is for you.

Included in this runbook are a handful of steps to _start_ investigating potential problems on `staging`.

This runbook is not meant to contain _every_ means of investigation; it contains just the most common ones.

## Check alerts in alarm

Show all the alerts that are alarming.

[Display alerts in alarm](https://console.demo.transposit.com/mc/t/spackle/actions/display_alarming_alarms)

## Check ECS tasks are deployed with the right ECR image

## Check basic microservice stats

Here you can get a quick view of the basic metrics for each ECS service corresponding to each microservice.

[auth](https://console.demo.transposit.com/mc/t/spackle/actions/basic_auth_dashboard)
[code](https://console.demo.transposit.com/mc/t/spackle/actions/basic_code_dashboard)
[execution](https://console.demo.transposit.com/mc/t/spackle/actions/basic_execution_dashboard)
[web](https://console.demo.transposit.com/mc/t/spackle/actions/basic_web_dashboard)

_Note shown: *schedule*, *accounts*, *task*, *apps*_

## Check basic EC2 instance stats

Here you can get a quick view of the basic metrics for each non-bastion EC2 instance.

[CPU Utilization](https://console.demo.transposit.com/mc/t/spackle/actions/graph_ec2_cpu_utilization)

## Query cloudwatch logs

If you've used the existing hosted app https://scan-cw-logs-btf3u.transposit.io/, then the following action _(restricted to just querying `staging`)_ should look familiar!

[scan_cw_logs](https://console.demo.transposit.com/mc/t/spackle/actions/scan_cw_logs)

Need some inspiration on what to filter by? Try one of these:
```
"ERROR"
"<request-id of particular failures>"
```

## External API monitoring and availablity

We use [Checkly](https://app.checklyhq.com/) to monitor our api availablity and response time from different locations.

Use the action below to get the results of the latest runs, if any results are red or have high values this means that we have a problem with our API performance.

[checkly (staging)](https://console.demo.transposit.com/mc/t/spackle/actions/checkly_staging)