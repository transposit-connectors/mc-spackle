# START HERE - Manual E2E testing

## Step 1 - instructions

This is what you need to test:

- join the #spa-lerts-demo channel - https://app.slack.com/client/T010SD75AP7/C010F9S7BNX
- run the `/trigger-demo` slash command to trigger a new incident
- create an incident channel
- join the incident channel
- click on the `Runbooks` button
- open this runbook (`Manual E2E testing`)
- Continue through the steps to run workflows
- close the incident

## Step 2 - run workflow

Click the `Run workflow!` button to test this workflow.

[Run workflow!](https://console.demo.transposit.com/mc/t/spackle/actions/e2e_test_workflow)

## Step 3 - no auth check

This test is for making sure we show a "no auth" modal after the input prompt loading screen. It requires
user auth for "AWS Budgets" so as long as you haven't added your user auth to that, or if you haven't signed in to Transposit with this slack workspace, it should show you an error modal.

[Run workflow](https://console.demo.transposit.com/mc/t/spackle/actions/no_auth_shows_modal)
