# Changelog TYPO3 Crawler

## Crawler 9.0.1-dev
Released:

### Added
* Documentation on how to use the Crawler for cache warmup during deployments
* Add better error handling to getPhpBinary + More tests for getPhpBinary
* Add SonarCloud to Pipeline
* More tests for QueryRepository
* More tests for ProcessRepository

### Changed
* Switched locallang.xml to xlf for crowdin support
* Corrected typos in Documentation and signals
* Cleanup CrawlerController - functions moved to respected Repository
* Moved HTMl from BackendModule showLog to Fluid template
* Switched from serialized to json-data for Queue information

### Deprecated
#### Classes

#### Functions & Properties
* ProcessService->countInARun
* ProcessService->crawlerController
* ProcessService->processLimit
* ProcessService->queueRepository
* ProcessService->verbose
* CrawlerController->cleanUpOldQueueEntries()
* CrawlerController->flushQueue()
* CrawlerController->getLogEntriesForSetId()
* Process->getTimeForFirstItem()
* Process->getTimeForLastItem()
* ProcessService->multiProcess()
* ProcessService->reportItemStatus()
* ProcessService->startRequiredProcesses()

### Removed
#### Classes
* EventDispatcher
* EventObserverInterface

#### Functions & Properties
* Process->row
* Queue->row
* CrawlerApi->countEntriesInQueueForPageByScheduleTime()


### Fixed
* Changed result handling for Crawling in case of 500 errors on directRequests
* Set correct tableName for mountPoint queries
* Fallback to alturl is added to ensure crawling of pages including PDF files
* Get fe_user from $GLOBALS['TSFE'] instead of $request->getAttribute()

## Crawler 9.0.0
Crawler 9.0.0 was released on April 14th, 2020

### Added

* Support for TYPO3 9.5.14+
* Support for TYPO3 10LTS
* Execution Strategy classes [@bmack](https://github.com/bmack)
* Middleware implementation for Crawler and FE User Authentication [@ichhabrecht](https://github.com/ichhabrecht) [@bmack](https://github.com/bmack)
* GuzzleHttp as http client [@bmack](https://github.com/bmack)
* symfony/console for CommandController for CLI and Scheduler Tasks
* Backend Module uses Fluid for templating [@bmack](https://github.com/bmack)
* Add worker support (e.g. for indexed_search) and change procInstruction registration [@cdro](https://github.com/cdro)
* `_RECURSIVE` option to the subpartParams Configuration of the lookup `_TABLE` instructions [@ vzz3](https://github.com/vzz3)
* Rector to CI Pipeline [@TomasVotruba](https://github.com/TomasVotruba)
* PHPStan to CI Pipeline [@TomasVotruba](https://github.com/TomasVotruba)
* Behaviour Driven Tests to CI Pipeline
* Depency for typo3/cms-info
* Code of Conduct
* DDEV Devbox

### Changed
* Implemented Doctrine for Database handling [@cdro](https://github.com/cdro)
* Migrated FE hooks to PSR-15 middleware [@bmack](https://github.com/bmack)
* Switched to Site Handling instead of sys_domain [@bmack](https://github.com/bmack)
* Use TYPO3 Logging API for CrawlerController [@bmack](https://github.com/bmack)
* Switched from ClickMenu to ContextMenu API [@bmack](https://github.com/bmack)
* Migrate access of 'extConf' to TYPO3 9 API [tstahn](https://github.com/tstahn)
* Updated Extension Icons [@bmack](https://github.com/bmack)
* Documentation is updated
* From EXT:lang to EXT:core for V10 compatibility

### Removed
* Support for TYPO3 8
* Support for TYPO3 7
* PHP support for `<7.2` [@TomasVotruba](https://github.com/TomasVotruba)
* Remove root_template_pid option [@bmack](https://github.com/bmack)
* Dependency for `helhum/typo3-console`
* RealURL support
* "legacy" Scheduler Tasks
* nc_staticfile_cache hook not needed for TYPO3 9 LTS+

##### Classes
* AuthenticationService [@bmack](https://github.com/bmack)
* CommandLineController

##### Functions
* BackendModule->loadExtensionSettings()
* CrawlerApi->isPageInQueue()
* CrawlerApi->isPageInQueueTimed()
* CrawlerApi->getUnprocessedItems()
* CrawlerApi->countUnprocessedItems()
* CrawlerApi->removeQueueEntrie()
* CrawlerController->CLI_deleteProcessesMarkedDeleted()

## Sorry !!!
We don't have any changelogs between version 5.1.3 and 9.0.0, version 7 and 8 was never released, we jumped to 9.0.0

## Crawler 5.1.3
Crawler 5.1.3 was released on July 21st, 2017.

### Changes
    [RELEASE] Release of crawler 5.1.3
    [TASK] Added Cache to TypoScriptUtility

## Crawler 5.1.2
Crawler 5.1.2 was released on November 24th, 2016.

### Changes
    [RELEASE] Release of crawler 5.1.2
    [BUGFIX] Scheduler Tasks broken after upgrade to 5.1.1 (composer) (#154)
    [BUGFIX] Fixed incorrect class name in ClassAliasMap (#153)

## Crawler 5.1.1
Crawler 5.1.1 was released on November 21th, 2016.

### Changes
    [RELEASE] Release of crawler 5.1.1
    [BUGFIX] It's not possible to "add process" after upgrade to 5.1.0 (#145)
    [BUGFIX] #1442236317: MenuItem "" is not valid (More information) (#148)
    [BUGFIX] Not possible to add new scheduler tasks (not only Crawler tasks) after upgrade to 5.1.0 (#144)
    [BUGFIX] Scheduler Tasks broken after upgrade to 5.1.0 (#142)

## Crawler 5.1.0
Crawler 5.1.0 was released on November 15th, 2016.

### Changes
    [FEATURE] Remove assignment of queue items to process if process gets killed by cleanup hook
    [FEATURE] Adjust namespace of ProcessCleanupTask (#138)
    [CLEANUP] Streamline ext_emconf.php and ext_localconf.php
    [TASK] Convert locallang_db.xml to xlf Resolves #134
    [TASK] Auto detect TypoScript Template
    [TASK] Moving hooks to Classes/Hooks and create utilities for Hooks and Scheduler tasks
    [TASK] Move "scheduler"-classes into "Classes/Tasks"
    [TASK] Set version to 5.0.10-dev


## Crawler 5.0.9
Crawler 5.0.9 was released on September 16th, 2016.

### Changes
    [RELEASE] Release of crawler 5.0.9
    [BUGFIX] Switch to PHP 5.3 compatible array syntax
    [TASK] Set version to 5.0.9-dev

## Crawler 5.0.8
Crawler 5.0.8 was released on September 16th, 2016.

### Changes
    [RELEASE] Release of crawler 5.0.8
    [FEATURE] Emit signals before/after a queue item is processed
    [TASK] Update README.md
    [TASK] Add scheduler task for process cleanup hook
    [TASK] Set version to 5.0.8-dev

## Crawler 5.0.7
Crawler 5.0.7 was released on September 6th, 2016.

### Changes
    [RELEASE] Release of crawler 5.0.7
    [FEATURE] Adjust autoload configuration for TYPO3 7+ (#117)
    [TASK] Update exception for "no typoscript template found" (#114)
    [TASK] Remove deprecated API call (#112)
    [TASK] Adjust composer psr-4 autoloading - fixes issue #115
    [TASK] Set version to 5.0.7-dev

## Crawler 5.0.6
Crawler 5.0.6 was released on August 22nd, 2016.

### Changes
    [RELEASE] Release of crawler 5.0.6
    Revert "Merge pull request #104 from AOEpeople/feature/remove-curl"
    #107 Fixes deprecated notices (#108)
    [TASK] Set version to 5.0.6-dev

## Crawler 5.0.5
Crawler 5.0.5 was released on August 15th, 2016.

### Changes
    [RELEASE] Release of crawler 5.0.5
    [FEATURE] Remove option to request pages by HTTP/HTTPS
    [FEATURE] Remove option to follow redirects
    [FEATURE] Introduce backend utility class to clean up ext_tables.php
    [TASK] Remove obsolete validator class (#101)
    [BUGFIX] Remove dependency for workspaces (#97)
    replace deprecated function call in TCA file, add renderType for select fields (#96)
    [BUGFIX] Crawler context menu throws fatal error
    [TASK] Deleting old tx_crawler_processes entries ends up in slow query
    [BUGFIX] Fix broken displayCond
    Revert "[TASK] Re-enable Workspace after Core Issue #70052 fixed"
    [TASK] Missing "hide"/"disable" field in the configuration record form
    [TASK] config.absRefPrefix not respected by tx_crawler_lib::getFrontendBasePath()
    [TASK] Set version to 5.0.5-dev
    [TASK] Remove "Add Process"-button when no more queue-item can be assigned

## Crawler 5.0.4
Crawler 5.0.4 was released on March 18th, 2016.

### Changes
    [RELEASE] Release of crawler 5.0.4
    [TASK] Replace deprecated parameter
    Revert "[TASK] config.absRefPrefix not respected by tx_crawler_lib::getFrontendBasePath()"
    [TASK] Re-enable Workspace after Core Issue #70052 fixed
    Improve configuration record documentation
    [TASK] config.absRefPrefix not respected by tx_crawler_lib::getFrontendBasePath()
    [TASK] Add Travis Config for both TYPO3 6 and 7LTS
    [TASK] Remove deprecated call of GeneralUtility::loadTCA()
    [TASK] Set version to 5.0.4-dev

## Crawler 5.0.3
Crawler 5.0.3 was released on March 10th, 2016.

### Changes
    [RELEASE] Release of crawler 5.0.3
    [TASK] Split Unit and Functional tests
    Update .travis.yml
    Renamed tests -> Tests
    [TASK] Update Travis script to be prepared for TYPO3 7 LTS compatibility update later
    [TASK] Update Documentation
    [TASK] #86620 Add refresh hooks so that the refresh button also removes orphan and old processes.
    [BUGFIX] Links on refresh icon/queue id do not work in TYPO3 7.6
    Set version to 5.0.2-dev
    [FIX] Fixed to ensure traversable else return


## Sorry
We don't have any changes logs later than this.
