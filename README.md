﻿### Collect system stats from raspberry and save it into a dockerized postgres database :

Folder structure :
```
rpi_telemetery
|__client
|  |__rpi4b.go
|__server
	|__main.go
```
#### step 1 : 
```
git clone https://github.com/devashishRaj/rip_telemetry.git
```

then cd into client folder:

#### step2 : build executable file for raspberry pi :
```
GOARM=6 GOARCH=arm GOOS=linux go build rpi_telemetery/client/rpi4b.go
```

#### step3: transfer build file to your raspy , eg: use scp if it's on same network 

```
scp tcpC <username>@<ip address>:<path to save file>
```
#### step4: run file 
```
<path to file>/rpi4b
```

#### step 5 : run main.go on server side where database is setup
```
go run main.go
```

__NOTE__ : make sure postgres is set up for , refer Postgres.MD 