# Changelog

You can find all notable changes to Explorer for Endevor in this document.

## [1.11.1] &ndash; 2025-06-16

### Fixed

- Fixed an issue that caused Generate element to fail when "Do not override" processor group option was chosen.

## [1.11.0] &ndash; 2025-06-04

### Added

- All the connections that use deprecated Web Services v1 API base paths are marked with a warning icon in the **Endevor Elements** View.

### Changed

- Improved element editing experience including: ability to keep element open after saving, setting the CCID/Comment, Generate After Upload feature via the status bar, reduced user prompts and better compatibility with the File: Auto Save setting. If Files: Auto Save is enabled, your changes will be automatically saved in the session but will not be automatically synchronized with Endevor. To synchronize the changes, ensure that you manually save the changes by pressing Ctrl+S (Command+S on Mac).
- Changed the logic of location specification while uploading the element changes. Now no location is required to be provided and element will be uploaded to the same location where it was retrieved from.
- Changed the logic of the Generate with copyback feature. Now elements are copied back to the location that is assigned to the map versus prompting you to specify the location.
- Changed the logic of the Add Element feature. Now the location prompt aligns with the File Extension Resolution setting when suggesting a file extension to apply to the new element.
- Now connections and locations in the **Endevor Elements** view are marked with error icon versus warning icon when problems with establishing the connection or authorization issues are detected.
- Eliminate unnecessary elements fetching when the Clear All Filters command is used.
- Removed broken Getting Started Walkthrough item from the commands list. Use the Open Walkthrough command to access the extension walkthroughs.

### Fixed

- Fixed an issue that prevented users from seeing invalid statuses of the inventory locations and properly updating the connection details or credentials for them.
- Fixed an issue that prevented users from fetching dependencies for COBOL Language Support.

## [1.10.1] &ndash; 2025-04-29

### Fixed

- Fixed an issue that prevented users from casting packages without selecting component validation.
- Fixed issues with fetching dependencies for COBOL Language Support.

## [1.10.0] &ndash; 2025-02-21

### Added

- Added a package ID filter to reduce amount of packages information to initially retrieve.
- Added element text filter limit support. The default maximum amount of elements to be filtered is set to 10 000 and can be adjusted using a new extension setting.

### Changed

- By default, only the 'In Edit' status is pre-selected in the package status filter to reduce the amount of packages information to initially retrieve.
- By default, the 'Validate' Components Validation option is pre-selected in Cast Package Options.

### Fixed

- Fixed an issue that led to the internal errors for the specific processor configurations. This issue caused problems fetching the dependencies for COBOL Language Support VS Code extension integration.
- Fixed an issue that caused moved elements to be erroneously marked as out-of-sync.
- Fixed an issue that prevented edited elements from being uploaded back to Endevor if the DSN validation option is enabled.
- Fixed an issue with the partial system/subsystem masking that did not work when specified in the Endevor inventory location.
- Fixed an issue when element uploading fails with the Generate After option enabled.
- Corrected some misleading messages and titles.

## [1.9.2] &ndash; 2024-12-18

### Added

- Added a new **LSP Config Log** output channel that includes the detailed information useful for troubleshooting Endevor configuration retrieval errors.

### Fixed

- Fixed an issue that led to the internal critical parsing errors for the specific processor configurations. This issue caused problems fetching the dependencies for COBOL Language Support VS Code extension integration.
- Fixed an issue that prevented the extension from sending the telemetry events when the telemetry collection is enabled.
- Removed the misleading directory cleanup errors in the extension output channel.

## [1.9.1] &ndash; 2024-11-06

### Fixed

- Fixed an issue that prevented some users from having the processor includes to be resolved correctly. This issue caused problems fetching the dependencies for COBOL Language Support VS Code extension integration.

## [1.9.0] &ndash; 2024-09-23

### Added

- Added an ability to resolve out-of-sync elements. You can edit and resolve a conflict situation in a diff editor.

### Changed

- **Breaking Changes Alert:** REST API v1 `EndevorService/api/v1` and `EndevorService/rest` will no longer be supported in **Explorer for Endevor 2.0.0**. Ensure that you follow the instructions in the Readme to avoid any business disruptions when v2.0.0 is released.
- You can now see and select an element listing that is stored in a specific member in a listing data set.
- Inventory locations now support the element parameter.

## [1.8.2] &ndash; 2024-09-16

### Changed

- The Workspace Sync **Sync** and **Pull** element commands now honor the inventory location Element parameter if the parameter is specified in the team configuration file.
- The Print a Listing feature now enables you to select multiple available listings for printing for the elements from up the map.

### Fixed

- Fixed an issue that prevented the SCL source code from being highlighted when the Show SCL action for the package is used.
- Fixed an issue that disallowed returning to the package status filter when no packages were found in the Package view.
- Fixed an issue with fetching configuration for the HLASM/COBOL extensions integration feature that did not respect the certificate validation option from the Endevor connection.
- Fixed an issue that prevented the blame lines from being rendered when multiple Element change level comparing tabs are opened.
- Fixed an issue that prevented the extension from sending the telemetry events when telemetry collection is enabled.

## [1.8.1] &ndash; 2024-07-22

### Fixed

- Show only one DSN name in the multiple listing selector if a few of the listing members are available to print.
- Fixed an issue with the Element up the map view updates after successful Move or Delete Elements action.
- Fixed multiple issues for better integration with the Language extensions.

## [1.8.0] &ndash; 2024-06-20

### Added

- Added an ability to explore full element history, including the original elements up the map in the Element History view.
- Added an ability to update existing packages by overwriting or appending elements to the package SCL.
- Added an ability to create a package with the name generated using the GENPKGID exit.
- Added a package action that shows the package SCL.
- Added a **Show All Elements Up the Map** filter to the Element view.
- Added an Element text filter to the Element view.
- Added Element Delete action support and the corresponding flag to the extension settings.
- Added an ability to select multiple listings for printing.
- Added an extension setting that lets you enable or disable CCID/comments input for the element actions

### Fixed

- Fixed an issue with Endevor profile schemes registration in Zowe team configuration files.
- Fixed an issue with the validation of Endevor connection/Inventory location profile names.
- Fixed an issue when the **Upload Element** results were reported as failed whereas only the Generate after Upload part was finished unsuccessfully.
- Fixed an issue with the Move Element action that occasionally fails with an authorization error when the token is almost expired.
- Fixed an issue that prevented the Edit or Retrieve Element actions from being used if an Endevor connection/Inventory location uses forbidden characters in the name.
- Endevor Synchronized Workspaces Sync/Pull actions now follow the extension Auto Signout setting.

### Changed

- A directory structure for retrieved elements now includes ENV/STGNUM/SYS/SUBSYS/TYPE and aligns with the synchronized workspace directories structure.
- Retrieve Element action now shows a dialog to select the workspace folder if more than one of folders is opened at the same time or not opened at all.
- Changed the VSCode version requirement. Ensure that you use VSCode 1.82.0 or higher.
- The text search feature requires the Endevor Web Services 2.15 or higher. Ensure that you meet the requirement so that you can use the text filter.

## [1.7.2] &ndash; 2024-03-22

### Added

- Added an additional C1MSGSA report type to the request records in the Endevor Reports view.

### Fixed

- Fixed an issue that prevented the editor from closing after upload.
- Fixed an issue with prompting to continue an edit session even if no changes were made to elements.
- Fixed an issue preventing file extensions from being properly rendered while editing.

### Changed

- Reduced logging traces when working with profiles.
- Suppressed unnecessary error logging when deleting internal temporary files.

## [1.7.1] &ndash; 2024-03-06

### Fixed

- Fixed an issue that prevented the extension from starting in certain environments.

## [1.7.0] &ndash; 2024-03-04

### Added

- Added the ability to create, cast, and reset packages.
- Added a package view with the ability to filter by package states and user packages.
- Added basic support and highlighting for Software Control Language (SCL).
- Added a functionality that lets you override a processor group before uploading an element.
- Added an extension setting that lets you set the condition of an element upload after the edit. The default behavior is to upload an element after the save action.
- Added a functionality that lets you view local changes in an edited element before uploading the element back to Endevor.
- Added a functionality that lets you compare changes between selected element revisions in the Element History view.
- Integration with HLASM Language Support 1.12.0 and higher.

### Changed

- Default Zowe profile is now propagated to the top of the Elements view when starting the extension.
- Interrupted or canceled element editing session can now be restored by opening the same element for editing.
- Temporary internal element files are now hidden.
- The update, discard, and show changes element actions are now available from the element editor context menu.
- Reduced the amount of potential element change loss during editing when VS Code is restarted or crashed.
- The generate element in place action is now available from the element editor context menu.
- The generate all elements in the subsystem feature is disabled by default. You can enable the feature in the extension settings.
- Overriding the processor group dialogs for add, upload, generate element is disabled by default. You can enable the feature in the extension settings.
- Element History view is now using the built-in VS Code split editor that provides improved user experience when working with changes.
- Profiles for the pull or synchronize workspace actions can now be chosen from the VS Code status bar. The selectors also show recently used profiles on the top.
- Element signin action now uses a sign out API call that no longer requires you to specify a CCID or Comment.
- Improved UI elements to increase user experience.

### Fixed

- Fixed an issue that overloaded the extension OUTPUT channel with confusing error messages.
- Fixed an issue that caused replacement of a previously opened listing tab with a newly opened one.
- Fixed an issue that caused permanent disablement of certificate validation for Endevor connections.
- Fixed an issue with showing the wrong listing after the generate element with copyback action is performed.
- Fixed the name validation procedure that caused the creation of connections that could break the element editing functionality.

## [1.6.0] &ndash; 2023-11-21

### Added

- Added preliminary Zowe API ML authentication support.
- Added a service and location with source information to log messages.
- Added an Activity panel to display performed Endevor Web Services requests during the working session with an ability to see the response statuses and reports.
- Added a View type details command.
- Added a toggle to allow the explorer tree to show empty types. The default state is not to show.

### Changed

- Added a verification step to the generating elements in the subsystem functionality. You must confirm your action before generation is started.
- Adjusted the Retrieve with dependencies progress reporting functionality to avoid multiple progress bars appearing.
- Enhanced element details with additional information.
- Updated the generate and add a new element commands with a processor group override option.

### Fixed

- Fixed an issue that overloaded the extension OUTPUT channel with confusing error messages.

## [1.5.4] &ndash; 2023-07-04

### Fixed

- Introduced enhancements to the logging and telemetry reporting capabilities.

## [1.5.3] &ndash; 2023-06-13

### Fixed

- Introduced minor logging mechanism improvements.

## [1.5.2] &ndash; 2023-05-26

### Fixed

- Fixed an issue with Generate with Copyback action which performed a Generate in place instead in case Override Signout was needed.
- Fixed the workspace pull command by incorporating the provided ccid and comment to the request.

## [1.5.1] &ndash; 2023-05-10

### Fixed

- Fixed an issue with Add an Element command which prevented local elements being added to Endevor.

## [1.5.0] &ndash; 2023-05-02

### Added

- Enhanced the filtering functionality for an Endevor inventory location. You can now also apply filters by element type.
- Added the generate a sandbox/subsystem feature with a summary batch report table.
- Added the history view feature. You can now see the list of element revisions and specific changes in every revision.
- Added the feature that enables you to view the C1MSGS1 Endevor batch report as a result of the generate element action.
- Added the Token Authentication feature through PassTickets.
- Added the feature that enables you to edit the Endevor connection details.

### Fixed

- Fixed the VS Code source control manager issue that prevented the diff editor for modified elements from being available after conflict resolution.

### Changed

- Added the no-source description indicator to the tree elements.
- Enhanced the tooltips for service, location, and element nodes.
- Removed Zowe CLI profiles now have the **Delete** option, instead of **Hide**.
- Headers are removed for all printed content, excluding listings.

## [1.4.3] &ndash; 2023-03-22

### Fixed

- Fixed an issue with retrieval of the remote elements for conflict resolution.

## [1.4.2] &ndash; 2023-02-14

### Fixed

- Fixed an issue with the up-the-map view which showed an incomplete list of the elements if the same element name is used for different types.

## [1.4.1] &ndash; 2023-01-26

### Fixed

- Fixed an issue with an infinite element-fetching loop after recovering from invalid credentials.

### Changed

- Element CCID is now an optional element attribute due to specific Endevor configurations where the CCID may not be specified at all.

## [1.4.0] &ndash; 2023-01-13

### Added

- Added a function that enables you to switch between the in-place only and in-place with up the map elements view for an Endevor inventory location.
- Added a filtering functionality for an Endevor inventory location. You can now apply filters by element name, last action CCID, or a combination of these.

### Fixed

- Fixed the inability to download dependent elements when using the retrieve with dependencies function.
- Fixed the infinite and non-cancellable elements fetching process during the first opening of the Endevor inventory location if the first attempt ended up with an error.
- Fixed the incorrect focusing on the Explorer for Endevor view for the add connection and inventory location function when the extension is used for the first time.
- Fixed the flickering of the Explorer for Endevor view on the extension startup.

### Changed

- The Endevor inventory location view now displays in-place elements only by default.
- Absence of a listing for a particular element is now recognized separately while using the Show listing command. A proper notification is shown instead of the error.

## [1.3.2] &ndash; 2022-11-24

### Fixed

- Fixed an issue with the fetching of Endevor elements for environments where the Stage ID does not correspond to the Stage number.

## [1.3.1] &ndash; 2022-11-23

### Fixed

- Fixed an issue with collapsing the explorer tree on refresh.
- Fixed an issue with fetching environments, systems and subsystem outside of the specified Endevor map.

### Changed

- Improved the Endevor workspace sync related messages.

## [1.3.0] &ndash; 2022-11-04

### Added

- Added the experimental feature that enables you to create a workspace and synchronize it with Endevor on the mainframe.
- Added an ability to correct Endevor connection information and credentials for the current VSCode session.
- Added cancellation for the connection testing and explorer tree refresh operations.
- Added Zowe V2 Conformance information to README.
- Added Get Started with Explorer for Endevor VSCode Walkthrough.
- Added Introduction to the Endevor Synchronized Workspace VSCode Walkthrough.

### Fixed

- Fixed the immediate user lockout if mainframe credentials were specified incorrectly.
- Fixed the up the map elements fetching if the Endevor location was specified using wildcards.
- Fixed the code regression messages. Now the messages are identified as warnings and are more visible.

### Changed

- Improved the extension UI. Now Explorer for Endeovor is provided with welcome views and the get started walkthrough.
- Improved the indication of the error messages for incorrect credentials or connection issues.
- Improved the Endevor connection and inventory location related dialogs and messages.

## [1.2.0] &ndash; 2022-08-12

### Added

- Added the functionality to create Endevor connections that work independently from Zowe profiles.
- Added the compatibility with the Zowe Secure Credential Store.
- Added the functionality that reads the Zowe Global Team and User Configuration files.
- Added the **Add an Inventory Location** button to the explorer tree.
- Added the explorer tree nodes tooltips based on their real values.
- Added the dialogs descriptions about the real connection and inventory location values.
- Added the UI option to submit the extension issue.
- Added the **Cancel** button to the Endevor Web Services URL and Endevor configurations validation.
- Added the extension setting that resolves the retrieved file extension based on the different strategies.
- Added more telemetry events.

### Fixed

- Fixed the performance issue with the long list of elements that are fetched from Endevor.
- Fixed the issue with ignoring the rejectUnauthorized value from the Zowe Base profiles.
- Fixed the issue with displaying non-existing Zowe profiles in the explorer tree.
- Fixed the issue that causes the refreshing of the explorer tree after errors.
- Fixed the issue that causes invalid Zowe profiles be accessible in the explorer tree.

### Changed

- Changed the edited elements file system path to an internal one.
- Changed the dialogs with an option to create an Endevor connection or inventory location right away.
- Changed the explorer tree to show full element names.

## [1.1.1] &ndash; 2022-05-23

### Added

- Added the function that tests connections to Endevor services in the Endevor profiles creation step.
- Support for v1 Endevor REST API (Endevor version 18.0).
- Added the override signout capability for the signout feature.

### Fixed

- Fixed the issue that prevented you from using the default HTTPS port value in the Endevor profiles creation step.

## [1.1.0] &ndash; 2022-04-01

### Added

- Added the generate an element with copyback and generate with no source features.
- Added the Signout-overriding functionality to the generate an element feature.

### Changed

- The **Remove profile** context menu item is changed to **Hide profile** to avoid confusion.
- Now multiple notification messages are displayed in one message upon successful element generation.
- Changed the VS Code version requirement. Ensure that you use VS Code 1.58.0 or higher.

### Fixed

- Fixed an issue with the signout error recovery attempt when an element is edited and uploaded into a different location.
- Fixed an issue that prevented the extension from updating an Endevor map tree after uploading the edited element into a new location.

## [1.0.2] &ndash; 2022-03-25

### Fixed

- Fixed an issue that prevented the extension from building an Endevor map tree if lowercased values were used in an Endevor location profile.
- Fixed an issue that caused the extension activation failure in the VSCode version 1.63.2 or lower.

## [1.0.1] &ndash; 2022-03-17

### Added

- Added alphabetical sorting to all levels of the explorer tree.

### Fixed

- Fixed an issue that caused the wrong representation of elements in the explorer tree.

## [1.0.0] &ndash; 2022-02-23

### Added

- Added the telemetry event-recording functionality.
- Added a `[MAP]` folder to the tree view. You can use the folder to store the elements that are found up the map.
- Added a `Show logs` button to the notification panel, which enables you to open the output of the extension.

### Changed

- Multiple error logging and notification events.

### Fixed

- Fixed an issue in the URI building process. Characters that may potentially break the building process are escaped.
- Fixed an issue that erroneously allowed upload dialogs to use wildcards as input.
- Fixed an issue that caused the conflict resolution command to fail when resolving reoccurring conflicts.
- Fixed an issue with retrieving and editing multiple elements with the auto signout option. Now the retrieve and edit commands correctly process all the selected elements in groups by location profiles.
- Fixed an issue with showing multiple elements for editing. An "editor already opened" error does not appear anymore.
- Fixed an issue that caused editors to close when discarding changes.

## [0.14.2] &ndash; 2022-02-01

### Fixed

- Fixed the password length limit from 8 to 100 characters. You can now take advantage of a passphrase if the passphrase is configured on the server. Unlike a password, a passphrase is case-sensitive.

## [0.14.1] &ndash; 2021-12-21

### Fixed

- Fixed the issue that caused the accept/discard change buttons to disappear in the diff editor while saving an edited element.

### Changed

- Updated the documentation. Changed the old product names to new ones.

## [0.14.0] &ndash; 2021-11-25

### Added

- Added the sign out and sign in features.
- Added the Automatic Signout setting.
- Added the Add an Element feature.

## [0.13.2] &ndash; 2021-11-12

### Added

- Added the compatibility for the latest Endevor WebServices charset response headers

## [0.13.1] &ndash; 2021-08-27

### Added

- Added the alphabetical sorting into the Endevor type nodes of the tree view.

### Changed

- Updated the documentation.

## [0.13.0] &ndash; 2021-07-05

### Added

- Added the conflict resolution feature for uploaded elements.

### Changed

- Removed Zowe CLI and CA Endevor plug-in for Zowe CLI from the client installation prerequisites.

## [0.12.1] &ndash; 2021-05-25

### Fixed

- Fixed an issue with rejectUnauthorized when listing endevor instances

## [0.12.0] &ndash; 2021-05-10

### Added

- Added the following new features that enable you to:
  - Create Endevor profiles and Endevor inventory location profiles
  - Use Zowe CLI base profiles
  - Perform an Edit action
  - Perform a Generate action
  - Print a listing
- Added the number of parallel HTTP requests supported by Endevor setting. You can now balance the Endevor load for smaller Endevor instances with a limited amount of resources

### Changed

- Updated the tree view. This will remove your profiles from the tree
  > Ensure that you add your profiles back by clicking **Add a new profile**.
- Updated the documentation

## [0.11.1] &ndash; 2020-12-11

### Fixed

- Fixed the issue with activation when you delete a profile from Zowe CLI

## [0.11.0] &ndash; 2020-11-13

### Added

- Added the output channel, "Explorer for Endevor", for logs

### Changed

- Moved Endevor Location connections from workspace settings to user settings
  > Ensure that you delete the `endevor.connections` entry from the Workspace settings if it exists.
- Improved messaging for core functionalities
- Updated the documentation

### Fixed

- Fixed the connections persistence

## [0.10.0] &ndash; 2020-06-25

### Added

- Added the profile interoperability feature for Endevor Plug-in for Zowe CLI, which enables you to:
  - create a profile
  - use existing profiles
  - automatically load the default profile
- Added the dependency on `@broadcom/endevor-for-zowe-cli` npm package
- Added the dependency on `@zowe/imperative` npm package
- Updated the documentation

### Removed

- Endevor Bridge for Git support
- The dependency on `request` npm package

## [0.9.1] &ndash; 2020-03-02

### Changed

- Updated the documentation
- Changed the license to EPL 2.0
- Added an open-source release. Moved the project codebase to the public repository under EPL 2.0 License

## [0.9.0] &ndash; 2019-09-13

### Added

- Added the New Host Creation feature

### Changed

- UX Enhancements

## [0.8.1] &ndash; 2019-08-21

### Changed

- Changed the category in package.json
- Expanded the list of prerequisites

### Fixed

- Fixed Theia 0.9

## [0.8.0] &ndash; 2019-08-16

Enhancements:

### Added

- Added the third-party license texts

### Changed

- Changed the extension name
- Corrected the links
