# Probe Endpoint

A helm chart to create a probe/testing endpoint

**Note**: This is WIP with README-driven design

The probe endpoint can be deployed in order to create an IP endpoint for several testing purposes:

* Ping
* iperf
* HTTP download/upload test
* speedtest

## Installation

The probe endpoint is deployed using helm:

```
helm install probe-endpoint
```

## Configuration

Configuration is done using the helm values file or by directly setting respective values via command line.
