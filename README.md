<h1 align="center">Monitoring Agent</h1>
<h3 align="center">aka "MAMA" the MAintainable Monitoring Agent</h3>

[![Build and Release](https://github.com/infraweavers/mama/workflows/Build%20and%20Release/badge.svg)](https://github.com/infraweavers/mama/actions?query=workflow%3A%22Build+and+Release%22)
[![Tests Status](https://github.com/infraweavers/mama/workflows/Test-Ubuntu/badge.svg)](https://github.com/infraweavers/mama/actions?query=workflow:Test-Ubuntu)
[![Tests Status](https://github.com/infraweavers/mama/workflows/Test-Windows/badge.svg)](https://github.com/infraweavers/mama/actions?query=workflow:Test-Windows)
[![Go Report Card](https://goreportcard.com/badge/github.com/infraweavers/mama)](https://goreportcard.com/report/github.com/infraweavers/mama)
[![License: MIT](https://img.shields.io/github/license/infraweavers/mama)](https://mit-license.org/)

### About

Aiming to be an easy to maintain monitoring agent that works cross platform, it is currently in active development.

### Example of current usage:

Linux:
```
$ curl -k -H "Content-Type: application/json" --data '{ "path": "C:\\Windows\\System32\\WindowsPowerShell\\v1.0\\powershell.exe", "args": [ "-command", "write-host \"Hello, World\"" ] }' https://test:secret@127.0.0.1:9000/v1/runscript
{"exitcode":0,"output":"Hello, World\n"}
```

Windows:
```
curl -k -H "Content-Type: application/json" --data "{ ""path"": ""C:\\Windows\\System32\\WindowsPowerShell\\v1.0\\powershell.exe"", ""args"": [""-Command"", ""Write-Host 'Hello, World'""]  }" https://test:secret@127.0.0.1:9000/v1/runscript
```

### Status

In active development.

### Current Features

* Execute a passed in script
* Continuous Integration/Delivery

### Future Planned Features

* Windows service
* Windows MSI
* Script signing enforcement
* `systemd` service
* Packaging for debian/ubuntu
* Cross platform

### Compiling and Executing

#### Windows

1. Install [GO](https://golang.org/doc/install)
2. `git clone https://github.com/infraweavers/mama %GOPATH%\src\mama`
3. `cd %GOPATH%\src\mama`
4. `go get .\...`
5. `go build -o monitoring-agent.exe` 
6. `.\monitoring-agent.exe`

#### Linux

1. Install [GO](https://golang.org/doc/install)
2. `git clone https://github.com/infraweavers/mama $GOPATH/src/mama`
3. `cd $GOPATH/src/mama`
4. `go get ./...`
5. `go build -o monitoring-agent` 
6. `./monitoring-agent`
