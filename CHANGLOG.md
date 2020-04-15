# generator-craftplugin Changelog

## 1.5.1 - 2020.04.15
### Changed
* Updated to use the new Twig Extension class namespace to avoid deprecation errors

### Fixed
* Make sure that `api_version_3_0 plugins` & modules have the default asset bundle with the properly lowercase namespace

## 1.5.0 - 2020.03.30
### Added
* Include the following in the 'extra' section: `developer`, `developerUrl`, & `documentationUrl`
* Move `hasCpSettings` and `hasCpSection` to plugin class

### Fixed
* Use `fs.writeFileSync()` for Node 10+ compatibility
* Update `_cpsection.twig` to use the `{% actionButton %}` block instead of `extraPageHeaderHtml`
* Fix module generated controller routes
* Docs link to Craft 3 docs
* Fixed iconpath for widgets and utilities for Modules
* Remove deprecated `composer/installers` from the `composer.json`
* Fixed docblock comments for `serializeValue` for Fields

## 1.4.3 - 2018.02.09
### Changed
* Improved the module's `_Service.php` template
* Removed `schemaVersion` from the `composer.json`'s `extra` array
* Added the public property `$schemaVersion` in the plugin's primary class

## 1.4.2 - 2018.02.05
### Changed
* Fixed an issue with the translation and AssetBundle aliases

## 1.4.1 - 2018.01.26
### Changed
* Fixed module namespacing for controllers & aliases
* Fixed an issue with empty names for various module components

## 1.4.0 - 2018.01.19
### Added
* Added support for modules via `module_api_version_3_0`

### Changed
* Fixed the Craft 3 API `Tasks` to generate proper Craft 3 Queue `Jobs`
* Added Code Comment documentation to Craft 3 API `Tasks`

## 1.3.13 - 2018.01.18
### Added
* Handle a default name for Fields in the Craft 3 API, in case they are left blank

## 1.3.12 - 2018.01.13
### Added
* Fixed a typo in `someFunction`

## 1.3.11 - 2017.12.13
### Added
* Removed `repositories` from `composer.json`

## 1.3.10 - 2017.12.04
### Added
* Added Craft app API inspections for PhpStorm in the templates

### Changed
* Updated the `craftcms/cms` version to `^3.0.0-RC1` in the `composer.json` template

## 1.3.9 - 2017.11.29
### Changed
* Update how twig extensions are registered

## 1.3.8 - 2017.10.07
### Changed
* Fixed an issue with code comments being turned off is not respected from the command line
* The code comments setting is now stored from session to session

## 1.3.7 - 2017.09.25
### Changed
* Fixed an issue with undefined indexes for the Craft 3.x APIs
* Fixed the generated CP assets for the Craft 3.x APIs

## 1.3.6 - 2017.09.02
### Added
* Fixed the Yii asset bundle aliases, which should be the directory name, not the kebab-handle

## 1.3.5 - 2017.07.28
### Added
* Craft 3 beta 23 compatibility

## 1.3.4 - 2017.07.12
### Added
* `config.php` files should be kebab-case, too

## 1.3.3 - 2017.07.10
### Added
* More kebab-case fixes

## 1.3.2 - 2017.07.09
### Added
* Initial Craft 3 beta 20 compatibility
* Switched over to `yarn`

### Changed
* For beta 20, extra.handle in composer.json should be "foo-bar" instead of "fooBar"
* src/translations/en/foobar.php now renamed to foo-bar.php
* Craft::t() calls now pass 'foo-bar' as the first argument instead of 'foobar'
* the |t filters in the generated template(s) are now |t('foo-bar') (these were incorrectly not passing any category currently, meaning that they will default to the site category)
* defineTemplateComponent() is now replaced with a listener for the defineComponents event on craft\web\twig\variables\CraftVariable
* Installation instructions in the readme should only cover Composer installs (Beta 20 dropped support for manual plugin installs)

## 1.3.1 - 2017.06.29
### Changed
* Changed the date format to YYYY-MM-DD for `CHANGLOG.md`

## 1.3.0 - 2017.05.18
### Added
* Added a `.craftplugin` file that defines the settings of the plugin
* Added the ability to add components on ad-hoc via `yo craftplugin --controllerName="Something"`
* Added a video to the documentation showing how all of this works
* Added more documentation on using `yo craftplugin`

## 1.2.37 - 2017.04.27
### Changed
* Refresh the Yii schema caches after adding tables in the `Install.php` migration

## 1.2.36 - 2017.04.19
### Changed
* Renamed `someField` -> `someAttribute` to fix Twig errors on the plugin Settings page

## 1.2.35 - 2017.04.19
### Changed
* Fixed the `Install.php` migration to sync with Craft beta changes of `Connection` -> `DbConfig`

## 1.2.34 - 2017.04.12
### Added
* Updated `composer.json` to add more common editor settings, `/vendor`, etc.

## 1.2.33 - 2017.04.11
### Added
* Added `asset-packagist` to `composer.json` for Scrutinizer & manual plugin install

## 1.2.32 - 2017.03.27
### Added
* Added an example of accessing a plugin's settings from a service

## 1.2.31 - 2017.03.25
### Changed
* Fixed the docblock for the `install` migration
* Better log statement formatting

## 1.2.30 - 2017.03.24
### Changed
* Changed the `install` migration to use `$this->driver = Craft::$app->getConfig()->getDb()->driver;`
* Brought the `config.php` file in line with the changes in Craft 3 beta 8

## 1.2.29 - 2017.03.24
### Changed
* The `install` migration is now coded more defensively, to add & drop tables only if they don't exist already
* Changed `hasSettings` -> `hasCpSettings` in the `composer.json`

## 1.2.28 - 2017.03.16
### Changed
* Changed the `XXXX plugin loaded` log message so that we're no longer concatenating a translated string with a non-translated string

## 1.2.27 - 2017.03.14
### Changed
* Removed pointless `DIRECTORY_SEPARATOR` in `renderTemplate()` calls

## 1.2.26 - 2017.03.14
### Changed
* Fixed EJS syntax errors in the `Install.php` migration

## 1.2.25 - 2017.03.14
### Changed
* Added `dateCreated`, `dateUpdated`, and `uid` to the `Install.php` migration
* Added a `foreignKey` example in the `Install.php` migration

## 1.2.24 - 2017.03.14
### Fixed
* Changed the translation category `toLowerCase()` for compliance with Craft `3.0.0-beta-7`

## 1.2.23 - 2017.03.13
### Fixed
* Added a `$` in front of the `@property` variables
* Fixed errant output when `codeComments` was on

## 1.2.22 - 2017.03.12
### Added
* Added code inspection typehinting for the `$plugin` static variable in the plugin's main class
* Added code inspection typehinting for services via `@property` on plugin's main class

### Fixed
* Fixed an issue with it not including `yii\base\Event` by default

## 1.2.21 - 2017.03.12
### Changed
* Require `craftcms/cms` in `composer.json` again
* Translations are a lowercase version of the pluginHandle

## 1.2.20 - 2017.03.05
### Changed
* Refactored the `_Record.php` template to be in line with the current Craft 3 beta

## 1.2.19 - 2017.03.04
### Added
* Modern-style `[]` for `config.php`

## 1.2.18 - 2017.03.03
### Added
* Check for whether our plugin is being installed in `EVENT_AFTER_INSTALL_PLUGIN` event handlers

## 1.2.17 - 2017.02.25
### Added
* Added a `.gitignore` file for the Craft 3.x API

## 1.2.16 - 2017.02.24
### Added
* Ensure that PHP reserved words are not used for the plugin name; appened "Plugin" if so
* Ensure that PHP reserved words are not used for a component name; append the component type if so

## 1.2.15 - 2017.02.15
### Added
* Added `getContentColumnType()`, `normalizeValue()`, & `serializeValue()` to `Fields.php`
* Added merging of parent rules for `Fields.php`

### Fixed
* Fixed missing `use craft\events\PluginEvent;` in `_Plugin.php`

## 1.2.14 - 2017.02.15
### Changed
* Removed deprecated methods for events like `onAfterInstall`
* Added an example of using `Plugins::` events

## 1.2.13 - 2017.02.14
### Fixed
* Switched the translation back to use the `pluginCamelHandle` doh

## 1.2.12 - 2017.02.14
### Fixed
* Fixed the composer URL in the README.md to be kebab-case
* Switched the translation back to use the `pluginDirName`

## 1.2.11 - 2017.02.14
### Changed
* Composer package names and github-related names are now in kebab-case

## 1.2.10 - 2017.02.10
### Changed
* Removed the `[]` around the version number in `CHANGELOG.md`
* Fixed the incorrect `.png` suffix for the plugin asset bundle icon

## 1.2.9 - 2017.02.08
### Changed
* Removed `extra.pluginDocumentationUrl` from `composer.json`

### Added
* Added `support.docs` to `composer.json`
* Added `support.issues` to `composer.json`

## 1.2.8 - 2017.02.08
### Changed
* `pluginName`, `pluginAuthorName`, `pluginDescription` and `copyrightNotice` are now all output unescaped

## 1.2.7 - 2017.02.08
### Changed
* `extra.name` is now the actual plugin name in the `composer.json`
* Removed `extra.version` in the `composer.json` since it's already specified in `version`
* Removed `extra.description` in the `composer.json` since it's already specified in `description`
* Removed `extra.developer` in the `composer.json` since it's already specified in `authors[]`
* Removed `extra.developerUrl` in the `composer.json` since it's already specified in `authors[]`

## 1.2.6 - 2017.02.08
### Fixed
* Fixed the incorrectly hard-code version in the `composer.json`

## 1.2.5 - 2017.02.06
### Changed
* Fixed an issue with the generated Element template that would throw a PHP error

## 1.2.4 - 2017.02.05
### Changed
* Ensured that the calls to getPublishedUrl() correspond to the published assets directory
* Removed deprecated view.registerCssResource() and view.registerJsResource() calls

### Added
* Added proper namespacing for the Field JavaScript

## 1.2.3 - 2017.02.05
### Fixed
* Changed the default class name from the reserved word `Default` to the plugin handle if no name is provided

## 1.2.2 - 2017.02.02
### Fixed
* Updated the console controllers and web controllers to return something more useful
* Fixed the generated route URIs to kebab-case the plugin handle
* Fixed the action URIs in the comments for controllers to kebab-case the plugin handle
### Changed
* plugin -> craft-plugin in `composer.json`

## 1.2.1 - 2017.01.31
### Fixed
* Removed errant tabs from the `composer.json` file

## 1.2.0 - 2017.01.30
### Added
* Craft 3 beta support

## 1.1.39 - 2017.01.28
### Added
* Added config.php
### Fixed
* Fixed the logo in README.md
* Handle a case where a plugin has no services

## 1.1.38 - 2017.01.28
### Added
* Added CP Sections

## 1.1.37 - 2017.01.27
### Added
* Added an example of how to access resources from AssetBundles
### Changed
* Refactored the `assetbundles` multiple times

## 1.1.36 - 2017.01.26
### Added
* AssetBundle all the things
### Changed
* Use yii\base\Event as appropriate
* Switch to a better CHANGELOG format
* General cleanup

## 1.1.35 - 2017.01.21

* [Added] Added Elements
* [Added] Added pluginChangelogUrl

## 1.1.34 - 2017.01.20

* [Added] Added Fields
* [Improved] New-style arrays for the translations
* [Improved] Moved icon.svg & icon-mask.svg to /src
* [Improved] Moved commands to console/controllers
* [Improved] Moved component templates to templates/_components/

## 1.1.33 - 2017.01.16

* [Fixed] Fixed broken translations

## 1.1.32 - 2017.01.16

* [Added] Added Tasks component for the 3.0.x API
* [Improved] Cleaned up the translations

## 1.1.31 - 2017.01.15

* [Added] Added Utilities component
* [Added] Added the ability to generate multiple ConsoleCommands
* [Improved] Code comments now are more complete, and if disabled, @inheritdoc is used
* [Removed] Removed releases.json from the 3.0.x API
* [Improved] Implemented CHANGELOG.md
* [Improved] Cleaned up the plugin code

## 1.1.30 - 2017.01.12

* [Added] Added section comments
* [Added] Added widgets
* [Improved] Cleaned up the css/js/template naming
* [Improved] Use DIRECTORY_SEPARATOR everywhere instead of /'s
* [Improved] Added an example Site and CP route for each controller

## 1.1.29 - 2017.01.12

* [Improved] Added Console Commands to the 3.0.x API
* [Improved] PSR-2 linted code for the 3.0.x API
* [Improved] Various code-cleanup and fixes

## 1.1.28 - 2017.01.09

* [Improved] We now call `parent::init()` in our overriden init() method in the 2.5.x API

## 1.1.27 - 2017.01.09

* [Fixed] Fixed an issue that would cause the generator to fail if you had empty Controller or Services names

## 1.1.26 - 2017.01.09

* [Fixed] Fixed a regression error that would cause Craft CMS API 2.5.x plugins to fail
* [Added] Added CHANGELOG.md to move the changelog to
* [Improved] Updated README.md

## 1.1.25 - 2017.01.08

* [Added] Added CHANGELOG.md
* [Improved] Updated README.md

## 1.1.24 - 2017.01.08

* [Improved] More Craft 3 API improvements / additions
* [Improved] Updated README.md

## 1.1.23 - 2016.10.03

* [Added] Initial Craft 3 support
* [Updated] Updated README.md

## 1.1.22 - 2016.09.18

* [Fixed] Fixed an issue the FieldType namespacing JS code
* [Updated] Updated README.md

## 1.1.21 - 2016.06.29

* [Fixed] Fixed an issue with Composer support to the generated plugins
* [Updated] Updated README.md

## 1.1.20 - 2016.06.22

* [Added] Added Composer support to the generated plugins
* [Updated] Updated README.md

## 1.1.19 - 2016.06.19

* [Fixed] Fixed a bug where empty service names would generate errors
* [Updated] Updated README.md

## 1.1.18 - 2016.06.16

* [Fixed] Fix service comment naming error
* [Updated] Updated README.md

## 1.1.17 - 2016.05.02

* Code Comments fixes
* [Updated] Updated README.md

## 1.1.16 - 2016.05.02

* Code Comments fixes
* [Updated] Updated README.md

## 1.1.15 - 2016.05.02

* Code Comments fixes
* [Updated] Updated README.md

## 1.1.14 - 2016.04.28

* We now `return $value;` in the FieldType's `prepValue()` and `prepValueFromPost()` template
* [Updated] Updated README.md

## 1.1.13 - 2016.04.26

* Fixed an issue with the FieldType Javascript
* [Updated] Updated README.md

## 1.1.12 - 2016.04.22

* Added a "Code Comments" checkbox, so that you can disable the verbose comments in the generated code scaffolding
* [Updated] Updated README.md

## 1.1.11 - 2016.04.21

* Fixed widget settings issues
* [Updated] Updated README.md

## 1.1.10 - 2016.04.12

* Fixed widget naming issues
* [Updated] Updated README.md

## 1.1.9 - 2016.02.22

* We now lowercase the plugin name and handles before Camel-izing them, if the string contains any whitespace
* [Updated] Updated README.md

## 1.1.8 - 2016.02.18

* Fixes/enhancements to the `_Widget.php` template
* [Updated] Updated README.md

## 1.1.7 - 2016.01.28

* Numbers are now allowed in the plugin name and sub-handle names, so `News2Buffer` for example is okay now
* [Updated] Updated README.md

## 1.1.6 - 2016.01.28

* Added some useful comments to the `Plugin.php` thanks to `ch.ris`
* [Updated] Updated README.md

## 1.1.5 - 2016.01.25

* Added the ability to create `ConsoleCommands`
* [Updated] Updated README.md

## 1.1.4 - 2016.01.24

* Made the `requires` dependencies an array, to allow for multiple dependencies
* Added an a new `Settings` component that determines if the plugin has AdminCP settings, and includes the appropriate templates/resources only if so
* Added the ability for BOILERPLATE_FILES to have dependencies just like templates
* [Updated] Updated README.md

## 1.1.3 - 2016.01.20

* Craft Commerce "Purchasables" now adds an ElementType, Model, and Record
* Fixed an error in the naming of the plugin's Settings.twig template
* [Updated] Updated README.md

## 1.1.2 - 2016.01.19

* Added a Craft Commerce Purchasable ElementType template
* [Updated] Updated README.md

## 1.1.1 - 2016.01.11

* We now create per-FieldType and per-Widget CSS/JS/Twig templates, named appropriately
* Cleaned up the Widget.php template
* We now create Body and Settings Twig template for Widgets
* Made the naming of certain templates more consistent
* [Updated] Updated README.md

## 1.1.0 - 2016.01.09

* In preparation for Craft 3.0, added support for multiple API targets for the plugin scaffolding
* Moved all of the configuration out of the Javascript and into a directory of `.json` files, one file per API target
* [Updated] Updated README.md

## 1.0.9 - 2016.01.07

* Fixes
* [Updated] Updated README.md

## 1.0.8 - 2016.01.07

* Added the ability to enter as many *Name's as you need, for multiple template files.  Just separate them with a ,
* Sanitized all of the templates to remove trailing white space, and converted all tabs to 4 spaces
* [Updated] Updated README.md

## 1.0.7 - 2016.01.06

* Template fixes
* [Updated] Updated README.md

## 1.0.6 - 2016.01.06

* Added Tasks to the templates
* [Updated] Updated README.md

## 1.0.5 - 2016.01.06

* Added Widgets to the templates
* Added additional Record and Model templates if you select ElementTypes
* Minor generated code cleanup
* [Updated] Updated README.md

## 1.0.4 - 2016.01.06

* Added support for named Services and Controllers
* Cleaned up the naming scheme for all plugin components; null values will be properly handled for all of the *Name's
* [Updated] Updated README.md

## 1.0.3 - 2016.01.05

* You can now access the generator via the web at [pluginfactory.io](http://pluginfactory.io)
* Added support for command line arguments being passed to the generator
* [Updated] Updated README.md

## 1.0.2 - 2016.01.04

* Added sub-questions for `ElementTypes`, `FieldTypes`, `Models`, and `Records` so that you can specify the name for each
* [Updated] Updated README.md

## 1.0.1 - 2016.01.04

* Added the `store` property to some questions that should retain the default answers the user gives
* Added a selectable list of components that you want included in your plugin, so you can tailor it to exactly what you want included
* Added `field.html`, `field.css`, and `field.js` templates for FieldTypes
* [Updated] Updated README.me

## 1.0.0 - 2016.01.03

* Initial release

Brought to you by [nystudio107](http://nystudio107.com)
