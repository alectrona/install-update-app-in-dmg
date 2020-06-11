# install-update-app-in-dmg
Script to Install or Update a macOS Application Inside a DMG

The following script will allow you to ether install or update a macOS app that is packaged inside a dmg. This script will determine if the app is installed and in use, and if so, will give the user the opportunity to postpone or update the application. If the user chooses to update the application, it will close, update, then re-open for the user. However, if the installed app is the same version as what has been downloaded, the process will not continue as there is no update necessary.

## Requirements for Use Without Modification
This script is intended to be used as a payload in a Jamf Pro policy but can easily be adapted to be used in other MDM environments. The prompting mechanism being used is jamfHelper, but this can be modified to use CocoaDialog without too much trouble.

## Script Parameters
| Parameter | Variable Name | Description |
| --------- | ------------- | ----------- |
| 4 | downloadURL | Static url or command that can be used to return a dynamic url |
| 5 | appFileName | Full name of the app; i.e. "Google Chrome.app" |
| 6 | versionComparisonKey | Key in the app's Info.plist that you want to use to compare version; i.e. CFBundleShortVersionString |
| 7 | commandToGetDownloadURL | (Optional) Specify whether the value in the downloadURL parameter is treated like command and evaluated ("true" OR empty) |