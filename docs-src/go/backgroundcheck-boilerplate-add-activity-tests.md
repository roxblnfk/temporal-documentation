---
id: backgroundcheck-boilerplate-add-activity-tests
title: Add Activity function tests
sidebar_label: Test Activity code
description: How to test Activity code
tags:
- testing
- developer guide
- go sdk
---

<!-- DO NOT EDIT THIS FILE DIRECTLY.
THIS FILE IS GENERATED from https://github.com/temporalio/documentation-samples-go/blob/main/backgroundcheck_boilerplate/tests/backgroundcheckboilerplate_dacx_test.go. -->

We can test Activity code for the following conditions:

- Error when invoking the Activity Execution.
- Error when checking for the result of the Activity Execution.
- Activity return values. Check to ensure the return value is expected.

:::copycode Sample application code

The following code sample comes from a working and tested sample application.
The code sample might be abridged within the guide to highlight key aspects.
Visit the source repository to [view the source code](https://github.com/temporalio/documentation-samples-go/blob/main/backgroundcheck_boilerplate/tests/backgroundcheckboilerplate_dacx_test.go) in the context of the rest of the application code.

:::

```go
// Test_SSNTraceActivity tests the SSNTraceActivity function
func (s *UnitTestSuite) Test_SSNTraceActivity() {
	// Create a test environment
	env := s.NewTestActivityEnvironment()
	// Register Activity with the enviroment
	env.RegisterActivity(activities.SSNTraceActivity)
	// Run the Activity in the test enviroment
	future, err := env.ExecuteActivity(activities.SSNTraceActivity, ssn)
	// Check there was no error on the call to execute the Activity
	s.NoError(err)
	// Check that there was no error returned from the Activity
	var result string
	s.NoError(future.Get(&result))
	// Check for the expected return value.
	s.Equal("pass", result)
}
```
