CircleCI orb
---

Execute your CloudQA test suites using CircleCI orb.

### Build status
[![CircleCI Build Status](https://circleci.com/gh/cloudqa-io/circle-ci-orb.svg?style=shield "CircleCI Build Status")](https://circleci.com/gh/cloudqa-io/circle-ci-orb) [![CircleCI Orb Version](https://img.shields.io/badge/endpoint.svg?url=https://badges.circleci.io/orb/cloudqa/suite-runner)](https://circleci.com/orbs/registry/orb/cloudqa/suite-runner) [![GitHub License](https://img.shields.io/badge/license-MIT-lightgrey.svg)](https://raw.githubusercontent.com/cloudqa-io/circle-ci-orb/master/LICENSE) [![CircleCI Community](https://img.shields.io/badge/community-CircleCI%20Discuss-343434.svg)](https://discuss.circleci.com/c/ecosystem/orbs)

### Set up
Set up an environment variable in your CircleCI build called `CLOUDQA_API_KEY`. This will be used
automatically by the job.

### Examples
Example executing a test suite:
```
version: 2.1
  orbs:
    suite-runner: cloudqa/suite-runner@2.0.3
  workflows:
    test-my-app:
      jobs:
        - suite-runner/execute:
            suite-id: '<your-cloudqa-suite-id>'
            browser: 'Chrome'
            build-tag: 'Circle CI demo'
            variables: 'cicd1=1,cicd2=2,cicd3=6'
            is-sequential-execution: false
            environment-name: 'QA'
            image: 'cimg/base:stable'
```
