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

####Options

* **github_repository_name**: The github repository name such as 'company/project'

  * **environment_variable**: GITHUB_REPOSITORY_NAME

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


### travis_framework_deploy_github
```
fastlane travis_framework_deploy_github
```
Travis github deployment lane

This lane must be run only on the **master** branch

####Options

* **github_repository_name**: The github repository name such as 'company/project'

  * **environment_variable**: GITHUB_REPOSITORY_NAME

  * **type**: string

  * **optional**: true

* **skip_slack**: Skip slack notification even if a SLACK_URL is define.

  * **type**: boolean

  * **optional**: true

  * **default_value**: false

####Environment variables

* **GITHUB_TOKEN**: The GitHub access token use to push the release to GitHub, check how to generate access token [here](https://help.github.com/articles/creating-an-access-token-for-command-line-use/)

  * **type**: string

  * **optional**: false

* **COCOAPODS_TRUNK_TOKEN**: The CocoaPods access token use to push the release to CocoaPods, check below to retrieve CocoaPods token

  * **type**: string

  * **optional**: false

####How to pass environement variable to Travis

Take a look to the Travis [documentation](https://docs.travis-ci.com/user/environment-variables/)

####How to retrieve CocoaPods Trunk Token ?

First setup your CocoaPods trunk [as follow](https://guides.cocoapods.org/making/getting-setup-with-trunk.html)

After that run this command :

```
grep -A2 'trunk.cocoapods.org' ~/.netrc
```

The output sould be something like this :

```
machine trunk.cocoapods.org
  login user@example.com
  password XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```

The password 'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX' is your CocoaPods trunk token



----

This README.md is auto-generated and will be re-generated every time [fastlane](https://fastlane.tools) is run.
More information about fastlane can be found on [https://fastlane.tools](https://fastlane.tools).
The documentation of fastlane can be found on [GitHub](https://github.com/fastlane/fastlane/tree/master/fastlane).
