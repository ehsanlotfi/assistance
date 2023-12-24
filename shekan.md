## set shekan DNS
```
wmic nicconfig where (IPEnabled=TRUE) call SetDNSServerSearchOrder ("178.22.122.100", "185.51.200.2")
```
###### OR
```
netsh interface ipv4 set dns "Ethernet" static 185.51.200.2
netsh interface ipv4 add dns "Ethernet" 178.22.122.100 index=2
```

## set default DNS
```
wmic nicconfig where (IPEnabled=TRUE) call SetDNSServerSearchOrder ()
```
###### OR
```
netsh interface ip set dns "Ethernet" dhcp
```

### Toggle 
```
@echo off
setlocal enabledelayedexpansion

set "currentDNS="
for /f "tokens=2 delims=: " %%a in ('netsh interface ipv4 show dns "Ethernet" ^| find "DNS Servers"') do (
    set "currentDNS=%%a"
)

if defined currentDNS (
    netsh interface ipv4 set dns "Ethernet" dhcp
    echo Shekan is OFF !
) else (
    netsh interface ipv4 set dns "Ethernet" static 185.51.200.2
    netsh interface ipv4 add dns "Ethernet" 178.22.122.100 index=2
    echo Shekan is ON !
)

pause

```
