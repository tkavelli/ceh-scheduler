# Scheduled endpoint request

Minimal infrastructure for periodically requesting a private HTTPS endpoint.
This repository contains scheduling configuration only, with no application
source, business logic, operational data or credentials.

The endpoint URL and authorization token are repository secrets: SCHEDULER_URL
and SCHEDULER_TOKEN. Responses stay in temporary runner storage and are removed
after checking the boolean health result. Public logs contain only a generic
success or failure message; do not add URLs, response payloads or counters.

Runs use standard GitHub-hosted Linux runners. There is no repository checkout,
third-party action, pull-request trigger, artifact upload or cache. The workflow
token has no repository permissions. Only the owner should dispatch or modify it.

This is temporary infrastructure. GitHub schedules can be delayed or disabled
following 60 days without repository activity; they are not a delivery SLA.
Disable the workflow when replacing it. Keep any diagnostics in private systems.

References:
- https://docs.github.com/en/actions/reference/runners/github-hosted-runners
- https://docs.github.com/en/actions/reference/workflows-and-actions/workflow-syntax#onschedule
- https://docs.github.com/en/actions/how-tos/manage-workflow-runs/disable-and-enable-workflows
