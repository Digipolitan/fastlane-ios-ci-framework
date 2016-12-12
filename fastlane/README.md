fastlane documentation
================
# Installation
```
sudo gem install fastlane
```
# Available Actions
### ci_framework_begin
```
fastlane ci_framework_begin
```
Run this lane when the CI environment handle a new build

#### Example:

```
fastlane ci_framework_begin product_name:DGFrameworkTemplate
```

#### Options

* **product_name**: The framework name.

  * **environment_variable**: DG_PRODUCT_NAME

  * **type**: string

  * **optional**: true

* **project**: The project to use.

  * **environment_variable**: DG_PROJECT

  * **type**: string

  * **optional**: true

* **skip_slack**: Skip slack notification even if a SLACK_URL is define.

  * **type**: boolean

  * **optional**: true

  * **default_value**: false

#### Environment variables

* **SLACK_URL**: The slack Hook URL

  * **type**: string

  * **optional**: true


### ci_framework_tests
```
fastlane ci_framework_tests
```
Build and run all tests in the CI environment

#### Example:

```
fastlane ci_framework_tests workspace:NAME.xcworkspace
```

#### How to install ?

This lane require actions define in [Digipolitan/fastlane-common](https://github.com/Digipolitan/fastlane-common)

```
import_from_git(
  url: 'https://github.com/Digipolitan/fastlane-common'
)
```

#### Options

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

#### Environment variables

* **SLACK_URL**: The slack Hook URL

  * **type**: string

  * **optional**: true


### ci_framework_deploy
```
fastlane ci_framework_deploy
```
CI deployment lane, do something only on a master branch

Deploy to **github**, **carthage** and **cocoapods**

#### How to install ?

This lane require actions or lanes define in [Digipolitan/fastlane-ios-framework](https://github.com/Digipolitan/fastlane-ios-framework)

- `framework_deploy_github` lane **if github_repository_name != nil**

- `framework_deploy_cocoapods` lane **if skip_cocoapods != true**

```
import_from_git(
  url: 'https://github.com/Digipolitan/fastlane-ios-framework'
)
```

#### Options

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

* **product_name**: The framework name.

  * **environment_variable**: DG_PRODUCT_NAME

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

#### Environment variables

* **SLACK_URL**: The slack Hook URL

  * **type**: string

  * **optional**: true



----

This README.md is auto-generated and will be re-generated every time [fastlane](https://fastlane.tools) is run.
More information about fastlane can be found on [https://fastlane.tools](https://fastlane.tools).
The documentation of fastlane can be found on [GitHub](https://github.com/fastlane/fastlane/tree/master/fastlane).
