# Tidelift and Jenkins Pipeline Integration

Tidelift can integrate with Jenkins through [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/).

This example will complete a basic `tidelift alignment save`, causing Tidelift to check the project's manifest against the correct Tidelift Catalog. If alignment is below 100%, the CLI will return exit status `1`, and the build will fail.

It also can optionally be set to not fail the build when not fully aligned, but simply note the failed alignment as part of the build.

This example also includes a commented section showing a strategy to automagically create a project in Tidelift if it does not exist - at build time. This requires use of two API keys. See the example and line comments for more information.

This is meant to be an example to build upon.

# Instructions

## Assumptions

* The project does not contain a `.tidelift` file and project name and organization name are both configured as envars in Jenkins. If the project contains a `.tidelift` file, the example can be edited to accommodate that.
* This example is for a simple Maven-based project. You may need to tweak the `tools` configuration inside the Jenkinsfile based upon your project.


## Quick start
Modify the `Jenkinsfile-example` and use as the pipeline definition for the pipeline inside of Jenkins.

The example has a section which requires inputting a value for `TIDELIFT_ORG_API_KEY` and optionally `TIDELIFT_BOT_USER_API_KEY`. These keys should be stored using Jenkins' Pipeline credential mechanisms. More information on Jenkins credentials is available [here](https://www.jenkins.io/doc/book/pipeline/jenkinsfile/#handling-credentials).
