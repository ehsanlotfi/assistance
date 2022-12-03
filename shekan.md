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
