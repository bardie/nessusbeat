# Nessusbeat

Nessusbeat provides a [Beat](https://www.elastic.co/products/beats) that
monitors a local
[Nessus](https://www.tenable.com/products/nessus-vulnerability-scanner)
installation's reports directory and exports, parses, and outputs scan
results to supported Beat outputs.


## Getting Started with Nessusbeat

### Requirements

* [Golang](https://golang.org/dl/) 1.7

https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-14-04

```bash
go get github.com/bardie/nessusbeat
```
### Configuration

```yaml
nessusbeat:
  report_path: /opt/nessus/var/nessus/users/admin/reports
  #cacert_path:
  #api_url:
  #api_username:
  #api_password:
```

### Build

To build the binary for Nessusbeat run the command below.
This will generate a binary in the same directory with the name
nessusbeat.

```
make
```


### Run

To run Nessusbeat with debugging output enabled, run:

```
./nessusbeat -c nessusbeat.yml -e -d "*"
```

To run on startup, see the [init-scripts](https://github.com/darvid/nessusbeat/tree/master/init-scripts)
folder for example configuration files for each init system.

### Roadmap

- [ ] Add option to poll remote Nessus and SecurityCenter
- [ ] Add ability to filter scans
- [ ] Support authentication via API key and secret
