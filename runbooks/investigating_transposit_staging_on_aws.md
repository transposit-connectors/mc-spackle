# Investigating Transposit Staging

## What are you trying to do?

If you've ever heard the phrases

... _"Is anyone else having trouble logging into *staging*?"_

... _"Is *staging* really slow right now?"_

... _"Can someone help me debug this failure on *staging*? This is the `request-id`."_

then this runbook is for you.

Included in this runbook are a handful of steps to _start_ investigating potential problems on _*staging*_.

This runbook is not meant to contain _every_ means of investigation; it contains just some common ones.

## Check alerts in alarm

Show all the alerts that are alarming.

[Display alerts in alarm](https://console.demo.transposit.com/mc/t/spackle/actions/display_alarming_alarms)

## Check basic microservice stats

Here you can get a quick view of the basic metrics for each ECS service corresponding to each microservice.

[auth](https://console.demo.transposit.com/mc/t/spackle/actions/basic_auth_dashboard)
[code](https://console.demo.transposit.com/mc/t/spackle/actions/basic_code_dashboard)
[execution](https://console.demo.transposit.com/mc/t/spackle/actions/basic_execution_dashboard)
[web](https://console.demo.transposit.com/mc/t/spackle/actions/basic_web_dashboard)

_Not shown: *schedule*, *accounts*, *task*, *apps*_

## Check basic EC2 instance stats

Here you can get a quick view of the basic metrics for each non-bastion EC2 instance.

[CPU utilization graphs](https://console.demo.transposit.com/mc/t/spackle/actions/graph_ec2_cpu_utilization)
[Show EC2 instance states](https://console.demo.transposit.com/mc/t/spackle/actions/show_ec2_status)

## Check ECS tasks are deployed with the right ECR image

Make sure that all ECS tasks are using the same image and that the image is tagged latest.

[Check Image Versions](https://console.demo.transposit.com/mc/t/spackle/actions/check_most_recent)

## Run very important AWS lambda scripts

Let's run some of our AWS lambda scripts. Here's one.

[Run AWS Lambda script](https://console.demo.transposit.com/mc/t/spackle/actions/lambda_something_something)

## Check recent JIRAs

Here you can get the last 10 JIRA bugs that were filed.

[Last 10 JIRA bugs](https://console.demo.transposit.com/mc/t/spackle/actions/recent_jiras)

## Query cloudwatch logs

If you've used the existing hosted app [scan-cw-logs](https://scan-cw-logs-btf3u.transposit.io/), then the following action _(restricted to just querying `staging`)_ should look familiar!

[Scan CW logs](https://console.demo.transposit.com/mc/t/spackle/actions/scan_cw_logs)

Need some inspiration on what to filter by? Try one of these:

```
"ERROR"
"<request-id of particular failures>"
```

## External API monitoring and availablity

We use [Checkly](https://app.checklyhq.com/) to monitor our api availablity and response time from different locations.

Use the action below to get the results of the latest runs, if any results are red or have high values this means that we have a problem with our API performance.

[checkly (staging)](https://console.demo.transposit.com/mc/t/spackle/actions/checkly_staging)
