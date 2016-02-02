# Getting Started With gRPC in Cisco IOS XR
## Cisco IDL
The definition of Cisco IDL can be found at:
```
IDL/ems_grpc.proto
```

The following operations act on modeled data and are supported in IOS XR 6.0.0:
* `GetConfig` - Retrieves configuration data.  Takes model path in JSON format as input argument. Returns configuration data in JSON format and error string.
* `MergeConfig` - Merges configuration data. Takes modeled data in JSON format as input argument. Returns error string.
* `DeleteConfig` - Deletes configuration data. Takes modeled data in JSON format as input argument. Returns error string.
* `ReplaceConfig` - Replaces configuration data. Takes modeled data in JSON format as input argument. Returns error string.
* `GetOper` - Retrieves operational (state) data.  Takes model path in JSON format as input argument. Returns operational (state) data in JSON format and error string.

The following operations act on CLI data and are supported in IOS XR 6.0.0:
* `CliConfig` - Merges configuration data.  Takes CLI configuration as input argument. Returns error string.
* `ShowCmdTextOutput` - Retrieves show-command output. Takes CLI show command as input argument. Returns CLI output and error string.

## gRPC Server
The gRPC server on Cisco IOS XR can be configured using its configuration model (Cisco-IOS-XR-man-ems-cfg.yang) or using the command line.  The minimum configuration just requires you to enable the gRPC service.  By default, the service runs on port 57400 without using TLS.  Requests must include user credentials  as metadata for AAA authentication whether TLS is enabled or not.  The service provides configuration options to specify port (57344-57999), TLS, address family (IPv4/IPv6) and maximum number of concurrent requests (per-user and total).

## Basic gRPC Service Configuration Using CLI
```
grpc
!
```

## Customized gRPC Service Configuration CLI
```
grpc
 port 57344
 tls
 !
 max-request-total 32
!
```

## Examples
You can find configuration examples in the [getting started guides for OpenConfig](https://github.com/CiscoDevNet/openconfig-getting-started). Examples in JSON and CLI format are relevant for gRPC.
