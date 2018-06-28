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

Probe-endpoint-iperf offers iperf performance measurement in client- and server-mode. It defaults to port 5201.
```
-----------------------------------------------------------
Server listening on 5201
-----------------------------------------------------------
```

Probe-endpoint-http offers <> on port 80. It's based on [knut](https://github.com/mgumz/knut) and follows its syntax.
```
knut throws "." through "/"
knut throws "/tmp/dong.txt" through "/ding.txt"

knut started on :80, be aware of the trees!
```

Probe-endpoint-speedtest offers performance measurement using speedtest.net. It's based on tianon/speedtest from [dockerhub](https://hub.docker.com/r/adolfintel/speedtest/).

```
kubectl logs <POD> -c probe-endpoint-speedtest
Retrieving speedtest.net configuration...
Testing from SoftLayer Technologies (159.122.104.184)...
Retrieving speedtest.net server list...
Selecting best server based on ping...
Hosted by LeaseWeb (Frankfurt) [0.49 km]: 2.195 ms
Testing download speed................................................................................
Download: 596.01 Mbit/s
Testing upload speed....................................................................................................
Upload: 393.09 Mbit/s
```
