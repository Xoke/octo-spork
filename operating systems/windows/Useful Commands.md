# Useful Commands

### GUI General Checks

* mdsched - Memory Diagnostics Scheduler - check memory

### Command Line (run cmd as administrator)

* chkdsk /f
  * Fix - quick check and fix (on reboot)
* chkdsk /r
  * Repair - longer check each sector (on reboot)
* sfc /scannow
  * System File Checker
* dism /online /cleanup-image /restorehealth
  * Deployment Image Services and Management
* winget upgrade --all
