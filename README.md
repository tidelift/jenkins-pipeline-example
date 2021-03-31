# Tidelift and Jenkins Pipeline Integration

Tidelift can integrate with Jenkins through [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/).

This example will complete a basic `tidelift alignment save`, causing Tidelift to check the project's manifest against the correct Tidelift Catalog. If alignment is below 100%, the CLI will return exit status `1`, and the build will fail.

This is meant to be an example to build upon.

# Instructions

## Assumptions

* The project already has a `.tidelift` file with correct `TIDELIFT_ORGANIZATION` and `TIDELIFT_PROJECT` variables set. See the Tidelift [documentation](https://docs.tidelift.com/article/92-dot-tidelift-files) for more on `.tidelift` files.
* This example is for a Maven-based project. You may need to tweak the `tools` configuration inside the Jenkinsfile based upon your project.


## Quick start
Add the `Jenkinsfile-example` configuration in this repository to your project repository, rename it to `Jenkinsfile`, and examine it, especially the comments.

The example has a section which requires inputting a value for `TIDELIFT_API_KEY`. This key should be stored using Jenkins' Pipeline credential mechanisms. More information on Jenkins credentials is available [here](https://www.jenkins.io/doc/book/pipeline/jenkinsfile/#handling-credentials).
