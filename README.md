# fhir-server
A fast, open source, HL7 FHIR server

This project provides [HL7 FHIR DSTU2](http://hl7.org/fhir/DSTU2/index.html) models and a generic FHIR server implemented in Go and using MongoDB as storage. This is not a complete implementation, as it is tuned toward the primary use cases of the [Intervention Engine](https://github.com/intervention-engine/ie), [eCQM Engine](https://github.com/mitre/ecqm), [Patient Matching Test Harness](https://github.com/mitre/ptmatch)
 +and [Synthetic Mass](https://github.com/synthetichealth/syntheticmass) projects.

The code in this project is a small wrapper around the [FHIR Server Library](https://github.com/intervention-engine/fhir).

## Building and Running fhir-server Locally
To install the FHIR server, please begin by referencing the following sections of the Intervention Engine install guide:

- (Prerequisite) [Install Git](https://github.com/intervention-engine/ie/blob/master/docs/dev_install.md#install-git)
- (Prerequisite) [Install Go](https://github.com/intervention-engine/ie/blob/master/docs/dev_install.md#install-go)
- (Prerequisite) [Install MongoDB](https://github.com/intervention-engine/ie/blob/master/docs/dev_install.md#install-mongodb)
- (Prerequisite) [Run MongoDB](https://github.com/intervention-engine/ie/blob/master/docs/dev_install.md#run-mongodb)
- Clone this repository into your GOPATH

Before you can run the FHIR server, you must install its dependencies via `go get` and build the `fhir` executable:

```
$ cd $GOPATH/src/github.com/mitre/fhir-server
$ go build
```

The above commands do not need to be run again unless you make (or download) changes to the *fhir* source code.

Once the executable is built, you can run it without any arguments:

```
$ ./fhir-server
```

If you are concurrently modifying the *fhir* source code, sometimes it is easier to combine the build and run steps into a single command (forcing a recompile on every run):

```
$ go run server.go
```

The *fhir* server accepts connections on port 3001 by default.

If you wish to test the server with synthetic patient data, please reference [Generate and Upload Synthetic Patient Data](https://github.com/intervention-engine/ie/blob/master/docs/dev_install.md#generate-and-upload-synthetic-patient-data).

## License

Copyright 2016 The MITRE Corporation

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
