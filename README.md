# ForceMigration
Salesforce force.com migration tools

## Configs

This build.xml requires two build.properties files.

#### /Program Files/Force Migration/sample/build.properties

This file contains usernames and passwords and must be filled out and placed at /Program Files/Force Migration/sample/build.properties

#### build.properties.local

This file must be in every build folder. It does not need any changes, but can be manipulated to control some functions

**sf.sourceRoot** = This is the root directory for your builds. It is set to the current working directory by default.

**sf.sourceHome** = This is the what the build script calls. (Can probably be collapsed into sourceRoot)

**sf.manifest** = This is the location of the package.xml that is used for all retrieval

**sf.runTests** = This controls what level of tests are run. Ensure the level you want is uncommented. Tests are always run in prod.


**sf.source.orgName** = <sourceOrgName>
**sf.source.username** = <usernmae>
**sf.source.password** = <PasswordWithSecurityToken>
**sf.source.serverurl** = https://test.salesforce.com/
**sf.source.maxPoll** = 20

**sf.target.orgName** = <targetOrgName>
**sf.target.username** = <usernmae>
**sf.target.password** = <PasswordWithSecurityToken>
**sf.target.serverurl** = https://test.salesforce.com/
**sf.target.maxPoll** = 20

## Usage

You must create a new folder with a copy of the build.xml, build.properties.local and package.xml for each build that you want to do. The package.xml must contain the items that you want to pull/push in the proper metadata format.

Metadata Reference: https://developer.salesforce.com/docs/atlas.en-us.204.0.api_meta.meta/api_meta/meta_types_list.htm

#### The following build commands can be issued:

**SprintRetrieveAndTestDeploy** = Retrieve the metadata from source and run the test only deployement in target org.
**SprintDeploy** = Depoy the metada in target org.

**DiffPackageComponents** = Retrive metata from source and target. And open it in diffmerge to compare.
