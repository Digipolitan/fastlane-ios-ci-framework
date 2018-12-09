fastlane documentation
================
# Installation

Make sure you have the latest version of the Xcode command line tools installed:

```
xcode-select --install
```

Install _fastlane_ using
```
[sudo] gem install fastlane -NV
```
or alternatively using `brew cask install fastlane`

# Available Actions
### ci_framework_deploy
```
fastlane ci_framework_deploy
```
Framework CI deployment lane, do something only on a master branch

Deploy to **github**, **carthage** and **cocoapods**

#### How to install ?

This lane require actions or lanes define in [Digipolitan/fastlane-ios-framework](https://github.com/Digipolitan/fastlane-ios-framework)

- `framework_deploy_github` lane **if github_repository_name != nil**

- `framework_deploy_cocoapods` lane **if skip_cocoapods != true**

```
import_from_git(
  url: 'https://github.com/Digipolitan/fastlane-common'
)
import_from_git(
  url: 'https://github.com/Digipolitan/fastlane-ios'
)
import_from_git(
  url: 'https://github.com/Digipolitan/fastlane-ios-framework'
)
```

#### Options

* __**target_scheme**__: The scheme into the Xcode project to execute, the scheme is required on the CI environement

  * **environment_variable**: TARGET_SCHEME

  * **type**: string

  * **optional**: false on CI

* __**xcodeproj**__: The Xcode project to select.

  * **environment_variable**: XCODEPROJ

  * **type**: string

  * **optional**: true

* __**product_name**__: The framework name.

  * **environment_variable**: PRODUCT_NAME

  * **type**: string

  * **optional**: true

* __**github_token**__: The GitHub access token use to push the release to GitHub, check how to generate access token [here](https://help.github.com/articles/creating-an-access-token-for-command-line-use/)

  * **environment_variable**: GITHUB_TOKEN

  * **type**: string

  * **optional**: true

* __**github_repository_name**__: The GitHub repository name such as 'company/project'

  * **environment_variable**: GITHUB_REPOSITORY_NAME

  * **type**: string

  * **optional**: true

* __**skip_cocoapods**__: Skip cocoapods deployment

  * **environment_variable**: SKIP_COCOAPODS

  * **type**: boolean

  * **default_value**: false

* __**skip_carthage**__: Skip carthage deployment

  * **environment_variable**: SKIP_CARTHAGE

  * **type**: boolean

  * **default_value**: false

* __**skip_codecov**__: Skip the codecov.io link

  * **environment_variable**: SKIP_CODECOV

  * **type**: boolean

  * **default_value**: false

#### Environment variables

* __**SLACK_URL**__: The Slack Hook URL

  * **type**: string

  * **optional**: true

* __**COCOAPODS_TRUNK_TOKEN**__: The CocoaPods access token use to push the release to CocoaPods

  * **type**: string

  * **optional**: true



----

This README.md is auto-generated and will be re-generated every time [fastlane](https://fastlane.tools) is run.
More information about fastlane can be found on [fastlane.tools](https://fastlane.tools).
The documentation of fastlane can be found on [docs.fastlane.tools](https://docs.fastlane.tools).
