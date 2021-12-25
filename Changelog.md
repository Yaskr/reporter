# 0.4.6

- Fixed CodeceptJS reporter to report tests failed in hooks

# 0.4.5

- Fixed "Total XX artifacts publicly uploaded to S3 bucket" when no S3 bucket is configured
- Improved S3 connection error messages

# 0.4.4

- Fixed returning 0 exit code when a process fails when running tests in parallel via `start-test-run`. Previously was using the last exit code returned by a process. Currently prefers the highest exit code that was returned by a process.

# 0.4.3

- Added `TESTOMATIO_DISABLE_ARTIFACTS` env variable to disable publishing artifacts.

# 0.4.2

- print version of reporter
- print number of uploaded artifacts
- print access mode for uploaded artifacts

# 0.4.1

Added `global.testomatioArtifacts = []` array which can be used to add arbitrary artifacts to a report.

```js
// inside a running test:
global.testomatioArtifacts.push('file/to/upload.png');
```

# 0.4.0

- Playwright: Introduced playwright/test support with screenshots and video artifacts

> Known issues: reporting using projects configured in Playwright does not work yet

- CodeceptJS: added video uploads

# 0.3.16

- CodeceptJS: fixed reporting tests with empty steps (on retry)

# 0.3.15

- Finish Run via API:

```
TESTOMATIO={apiKey} TESTOMATIO_RUN={runId} npx @testomatio/reporter@latest --finish
```

# 0.3.14

- Create an empty Run via API:

```
TESTOMATIO={apiKey} npx @testomatio/reporter@latest --launch
```

# 0.3.13

- Checking for a valid report URL
- Sending unlimited data on test report

# 0.3.12

- Fixed submitting arbitrary data on a test run
- Jest: fixed sending errors with stack traces
- Cypress: fixed sending reports

# 0.3.11

- Fixed circular JSON reference when submitting data to Testomatio

# 0.3.10

- Minor fixes

# 0.3.9

- Making all reporters to run without API key

# 0.3.8

- Fixed `npx start-test-run` to work with empty API keys

# 0.3.7

- Fixed release

# 0.3.6

- Update title and rungroup on start for scheduled runs.

# 0.3.5

- Added `TESTOMATIO_RUN` environment variable to pass id of a specific run to report

# 0.3.4

- Minor fixes

# 0.3.3

- [CodeceptJS] Fixed stack trace reporting
- [CodeceptJS] Fixed displaying of nested steps
- [CodeceptJS][mocha] Added assertion diff to report

# 0.3.2

- Fixed error message for S3 uploading

# 0.3.1

- [CodeceptJS] Better formatter for nested structures and BDD tests

# 0.3.0

- Added `TESTOMATIO_TITLE` env variable to set a name for Run
- Added `TESTOMATIO_RUNGROUP_TITLE` env variable to attach Run to RunGroup
- Added `TESTOMATIO_ENV` env variable to attach additional env values to report
- [CodeceptJS] **CodeceptJS v3 support**
- [CodeceptJS] Dropped support for CodeceptJS 2
- [CodeceptJS] Added support for before hooks
- [CodeceptJS] Log of steps
- [CodeceptJS] Upload screenshots of failed tests to S3
- [CodeceptJS] Updated to use with parallel execution
