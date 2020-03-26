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

## Check ECS tasks are deployed with the right ECR image

## Check basic microservice stats

## Query cloudwatch logs

If you've used the existing hosted app https://scan-cw-logs-btf3u.transposit.io/, then the following action _(restricted to just querying `staging`)_ should look familiar!

[scan_cw_logs](https://console.demo.transposit.com/mc/t/spackle/actions/scan_cw_logs)

Need some inspiration on what to filter by? Try one of these:
```
"ERROR"
"<request-id of particular failures>"
```