---
id: how-to-set-workflow-timeouts-in-python
title: How to set Workflow Timeouts in Python
sidebar_label: Workflow Timeouts
description: Set the timeout to either start_workflow() or execute_workflow().
tags:
- timeout
- python sdk
- code sample
---

<!-- DO NOT EDIT THIS FILE DIRECTLY.
THIS FILE IS GENERATED from https://github.com/temporalio/documentation-samples-python/blob/main/workflow_timeouts_retries/workflows_dacx.py. -->

Set the timeout to either the [`start_workflow()`](https://python.temporal.io/temporalio.client.Client.html#start_workflow) or [`execute_workflow()`](https://python.temporal.io/temporalio.client.Client.html#execute_workflow) asynchronous methods.

Available timeouts are:

- `execution_timeout`
- `run_timeout`
- `task_timeout`

<div class="copycode-notice-container"><div class="copycode-notice"><img data-style="copycode-icon" src="/icons/copycode.png" alt="Copy code icon" /> Sample application code information <img id="i-id30999745" data-event="clickable-copycode-info" data-style="chevron-icon" src="/icons/chevron.png" alt="Chevron icon" /></div><div id="copycode-info-id30999745" class="copycode-info">The following code sample comes from a working and tested sample application. The code sample might be abridged within the guide to highlight key aspects. Visit the source repository to <a href="https://github.com/temporalio/documentation-samples-python/blob/main/workflow_timeouts_retries/workflows_dacx.py">view the source code</a> in the context of the rest of the application code.</div></div>

```python
# ...
    result = await client.execute_workflow(
        YourWorkflow.run,
        "your timeout argument",
        id="your-workflow-id",
        task_queue="your-task-queue",
        # Set Workflow Timeout duration
        execution_timeout=timedelta(seconds=2),
        # run_timeout=timedelta(seconds=2),
        # task_timeout=timedelta(seconds=2),
    )
```