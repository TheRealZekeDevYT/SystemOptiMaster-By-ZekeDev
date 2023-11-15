# SystemOptiMaster-By-ZekeDev
This a .bat file if you don,t want to download the file







@echo off

:MENU
cls
echo ************************************
echo *       Welcome to My Tool         *
echo *    Created by Zeke               *
echo *     SystemOptiMaster             *
echo ************************************
echo.
echo 1: Show IP Configuration
echo 2: Release and Renew IP Address
echo 3: Flush DNS Cache
echo 4: Display Routing Table
echo 5: Display DHCP Class ID
echo 6: Ping a Website
echo 7: Display Network Statistics
echo 8: Trace Route to a Website
echo 9: List Disk Information
echo 10: Check Disk for Errors
echo 11: Defragment Disks
echo 12: Run System File Checker (SFC)
echo 13: Perform System Maintenance Tasks
echo x: Exit
set /p choice="Enter your choice: "

if "%choice%"=="1" goto SHOWIP
if "%choice%"=="2" goto RELEASEANDRENEW
if "%choice%"=="3" goto FLUSHDNS
if "%choice%"=="4" goto SHOWROUTE
if "%choice%"=="5" goto SHOWDHCP
if "%choice%"=="6" goto PINGWEBSITE
if "%choice%"=="7" goto NETSTAT
if "%choice%"=="8" goto TRACERTWEBSITE
if "%choice%"=="9" goto LISTDISKINFO
if "%choice%"=="10" goto CHKDSK
if "%choice%"=="11" goto DEFRAG
if "%choice%"=="12" goto RUNSFC
if "%choice%"=="13" goto CUSTOMTASK
if /i "%choice%"=="x" goto :EOF

echo Invalid choice. Please try again.
pause
goto MENU

:SHOWIP
echo.
ipconfig /all
echo.
pause
goto MENU

:RELEASEANDRENEW
echo.
ipconfig /release
ipconfig /renew
echo IP address released and renewed successfully.
echo.
pause
goto MENU

:FLUSHDNS
echo.
ipconfig /flushdns
echo DNS cache flushed successfully.
echo.
pause
goto MENU

:SHOWROUTE
echo.
ipconfig /allcompartments /all
echo.
pause
goto MENU

:SHOWDHCP
echo.
ipconfig /showclassid
echo.
pause
goto MENU

:PINGWEBSITE
echo.
set /p website="Enter website to ping: "
ping %website%
echo.
pause
goto MENU

:NETSTAT
echo.
netstat -a
echo.
pause
goto MENU

:TRACERTWEBSITE
echo.
set /p target="Enter website to trace route to: "
tracert %target%
echo.
pause
goto MENU

:LISTDISKINFO
echo.
echo Disk information:
diskpart /s "%~dp0diskinfo.txt" 
type "%~dp0diskinfo.txt"
echo.
pause
goto MENU

:CHKDSK
echo.
echo Checking disk for errors...
chkdsk C: /f /r
echo.
pause
goto MENU

:DEFRAG
echo.
echo Defragmenting disks...
defrag C: /U /V
echo.
pause
goto MENU

:RUNSFC
echo.
echo Running System File Checker (SFC)...
sfc /scannow
echo.
pause
goto MENU

:CUSTOMTASK
echo.
echo This option performs system maintenance tasks such as clearing temporary files, optimizing system performance, and ensuring system integrity. Selecting this option will run various maintenance commands.
echo.
pause
goto MENU


