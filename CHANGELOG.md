# 1.3.2 - Unreleased

## Added

- [Core] Added support for storing objects as variables 
- [Core] Added support for returning only the value of a variable using Get-UAVariable 

## Changed

- [Core] Fixed an issue where Invoke-UAScript would throw an exception when called without a credential
- [Core] Fixed an issue where invoking a script could result in double serialization of the input parameters. 
- [UI] Fixed an issue where you would edit a variable and it would lose it's type.
- [UI] Fixed an issue where variables with long names or values would make the UI unusable. 

# 1.3.1 - 4/17/2020

## Changed

- [Core/UI] Fixed an issue where the UA dashboard would fail to load
- [Core] Fixed an issue where grooming would only groom jobs that were recent.

# 1.3.0 - 4/16/2020

## Added 

- [Core/UI] Added support for presenting additional controls based on the param block of a script. 

## Changed

- [UI] Changed the location and behavior of the navigation bar. 

# 1.2.1 - 4/7/2020 

## Changed

- [Core] Fixed an issue where running a job with alternate credentials when hosted as a Windows Service would fail 
- [UI] Fixed an issue where the UD dashboard would not accept a UD license and would not display information about licensing. 

# 1.2.0 - 4/6/2020

## Added 

- [UI] Added a checkbox to take you to a script after creating it
- [Core\UI] Added support for Secret Management 
- [Core\UI] Added PowerShell Version option to schedules
- [UI] Added the ability to edit variablee
- [UI] Added the ability to sort jobs by status, start time and end time 

## Changed 

- [UI] Fixed an issue where the UI would go blank if the script text was completely deleted
- [UI] The default comment in the editor of a new script is the name of script
- [Core] Greatly improved the performance of viewing pipeline output
- [Core] Jobs are now run with -NoProfile set

# 1.1.1 - 3/19/2020

## Added

- [Core\UI] Added per-script grooming setting. 
- [UI] Added Jobs tab to the script page

## Changed

- [UI] The jobs tab now pages correctly to improve performance
- [UI] Improved the performance of the job page.
- [UI] Fixed an issue where hosting in IIS would not authenticate properly with Windows auth
- [Core] Improved the performance of the storage of job output logs

# 1.1.0 - 3/16/2020

## Added 

- [UI] Added a link to the scripts page from the jobs page
- [Core] Added One Time scheduling
- [UI] Added a New Script button to the scripts page 

## Changed

- [UI] - The web dashboard is now based on the desktop app
- [UI] Edit button now allows for editing in the UI
- [Core] Fixed the PowerShell resolver so it detects PowerShell versions correctly. 
- [UI] Improved the pipeline output table 
- [Core] Fixed issue with starting UA Server on Mac OSX
- [Core] Fixed issue where grooming could remove active jobs
 
# 1.0.1 - 2/27/2020

## Added

- [Module] Added grooming job to remove jobs and output that are 30+ days old
- [Desktop] Added the ability to manage PowerShell Versions 

## Changed 

- [Module] Fixed but with ErrorAction parameter on Set-UAScript
- [Module] /api/v1/script now accepts query string parameters for script parameters
- [Desktop] Provided a better error message when UA is alive but not accessible because authentication is enabled.
- [Desktop] UA Desktop is now code signed correctly. 
 
# 1.0.0 - 2/24/2020

## Added

- Added -ApiUrl for Start-UAServer so UA works correctly behind a reverse proxy like IIS
- Added -ErrorAction to Set-UAScript

## Changed

- Fixed issue where a mismatch between the $User variable and the current Identity would cause an exception
- InProcess parameter of Start-UAServer now blocks so it properly supports IIS.
- Fixed a crash that would happen after running a job. 
- Fixed issue with how AppToken was being set for jobs.
- Fixed an issue where deleting a script wouldn't delete associated schedules
- If the API connection fails within a job, it will not cause the job to fail. 

# 0.0.3-beta7 - 2/6/2020

## Added 

- Added -RepositoryPath to Start-UAServer so you can specify where the local Git repo is stored. 
- Added support for authentication on the Swagger page

## Changed

- UA will now work in the ISE
- Stop-UAServer now performs a graceful shutdown by default. Using the -Force parameter forces the process to terminate.
- Fixed an issue where an dashboard without authentication enabled would be in read-only mode

# 0.0.3-beta6 - 1-31-2020

## Added 

- Added Enable-UAAuthentication to make it easier to enable UA authentication. 

## Changed

- Fixed an issue where restarting the server would fail to return a system app token and you could no longer use the UA dashboard (401 error)
- Fixed an issue where scripts' tags would not be sync'd to git - https://github.com/ironmansoftware/universal-automation/issues/67
- Fixed issue with roles not being assigned
- Fixed issue with session AppToken not being used in the dashboard

# 0.0.3-beta5 - 1-22-2020

## Added

- Added UI controls for disabling manual invocation of scripts
- Tags are now stored in the git repo under `.ua/tags.psd1`

## Changed

- Fixed issue where a $null on the pipeline would cause a script to file - https://github.com/ironmansoftware/universal-automation/issues/74
- Fixed an issue where you couldn't cancel a script requesting feedback - https://github.com/ironmansoftware/universal-automation/issues/78
- No trial license required - https://ironmansoftware.com/simplifying-product-trial-licensing/

# 0.0.3-beta4 - 1-18-2020

## Added 

- Added built-in varaibles for $UAScript, $UAJob, and $UASchedule. https://github.com/ironmansoftware/universal-automation/issues/64
- Added -DisableManualInvocation to New-UAScript to prevent jobs from running ad-hoc - https://github.com/ironmansoftware/universal-automation/issues/59

## Changed

- Error output now lists the script stack trace. 
- Fixed an issue with not being able to save PowerShell Version settings - https://github.com/ironmansoftware/universal-automation/issues/71
- Fixed sorting of job tables (clicking now sorts correctly) 
- Fixed issue where schedules would be lost when editing the script content in the dashboard - https://github.com/ironmansoftware/universal-automation/issues/66

# 0.0.3-beta3 - 1-15-2020

## Changed

- Get-UAJob now supports paging, server-side filtering and sorting 
- UA dashboard active and historical job grids now use server-side processing
- Fixing an issue where an AppToken would be generated when executing a script even when AppTokens aren't being used. 
- Fixed issue where license activation would run every time the server was started 
- Fixed issue with dot sourcing files (https://github.com/ironmansoftware/universal-automation/issues/73)
- Fixed sorting of the ID column in the job grid (https://github.com/ironmansoftware/universal-automation/issues/46)

# 0.0.3-beta2 - 1-14-2020

## Changed

- Removed the diagrams component from UniversalAutomation.Dashboard so unlicensed UD dashboards will work. 
