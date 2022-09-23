---
id: testing-activities
title: Testing Activities
description: Testing provides a framework to facilitate Workflow and integration testing.
sidebar_label: Test Activities
tags:
  - guide-context
---

Activities can be tested with a mock Activity environment, which provides a way to mock Activity context, listen to heartbeats, and cancel the Activity. This allows you to test the Activity in isolation by calling it directly, without needing to create a Worker to run the Activity.