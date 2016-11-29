fastlane documentation
================
# Installation
```
sudo gem install fastlane
```
# Available Actions
### travis_framework_tests
```
fastlane travis_framework_tests
```
Build and run all tests for the given environment

####Example:

```
fastlane travis_framework_tests workspace:NAME.xcworkspace
```

####How to install ?

This lane require the `tests` lane define in [Digipolitan/fastlane-ios-common](https://github.com/Digipolitan/fastlane-ios-common)

```
import_from_git(
  url: 'https://github.com/Digipolitan/fastlane-ios-common'
)
```

####Options

* **workspace**: The workspace to use.

  * **environment_variable**: DG_WORKSPACE

  * **type**: string

  * **optional**: true

* **name**: The framework name.

  * **environment_variable**: DG_FRAMEWORK_NAME

  * **type**: string

  * **optional**: true

* **project**: The project to use.

  * **environment_variable**: DG_PROJECT

  * **type**: string

  * **optional**: true

* **scheme**: The scheme into the workspace to execute.

  * **environment_variable**: DG_SCHEME

  * **type**: string

  * **optional**: true

* **skip_slack**: Skip slack notification even if a SLACK_URL is define.

  * **type**: boolean

  * **optional**: true

  * **default_value**: false

####Environment variables

* **SLACK_URL**: The slack Hook URL

  * **type**: string

  * **optional**: true


### travis_framework_after_success_action
```
fastlane travis_framework_after_success_action
```
Travis after success lane, the action depend of the current git branch

For all branches run **code coverage** and submit stat to slack

After that only for the **master branch**, deploy framework to **github** and **cocoapods**

####How to install ?

This lane require the `coverage` lane define in [Digipolitan/fastlane-ios-common](https://github.com/Digipolitan/fastlane-ios-common)

```
import_from_git(
  url: 'https://github.com/Digipolitan/fastlane-ios-common'
)
```

This lane require :

- `framework_deploy_github` lane **if github_repository_name != nil**

- `framework_deploy_cocoapods` lane **if skip_cocoapods != true**

Define in [Digipolitan/fastlane-ios-framework](https://github.com/Digipolitan/fastlane-ios-framework)

```
import_from_git(
  url: 'https://github.com/Digipolitan/fastlane-ios-framework'
)
```

####Options

* **github_repository_name**: The GitHub repository name such as 'company/project'

  * **environment_variable**: DG_GITHUB_REPOSITORY_NAME

  * **type**: string

  * **optional**: true

* **workspace**: The workspace to use.

  * **environment_variable**: DG_WORKSPACE

  * **type**: string

  * **optional**: true

* **project**: The project to use.

  * **environment_variable**: DG_PROJECT

  * **type**: string

  * **optional**: true

* **scheme**: The scheme into the workspace to execute.

  * **environment_variable**: DG_SCHEME

  * **type**: string

  * **optional**: true

* **skip_slack**: Skip slack notification even if a SLACK_URL is define.

  * **type**: boolean

  * **optional**: true

  * **default_value**: false

* **skip_cocoapods**: Skip cocoapods deployment

  * **type**: boolean

  * **optional**: true

  * **default_value**: false

* **skip_carthage**: Skip carthage deployment

  * **type**: boolean

  * **optional**: true

  * **default_value**: false

####Environment variables

* **SLACK_URL**: The slack Hook URL

  * **type**: string

  * **optional**: true



----

This README.md is auto-generated and will be re-generated every time [fastlane](https://fastlane.tools) is run.
More information about fastlane can be found on [https://fastlane.tools](https://fastlane.tools).
The documentation of fastlane can be found on [GitHub](https://github.com/fastlane/fastlane/tree/master/fastlane).
