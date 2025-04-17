# netdata-monitoring-task
# Task 7: Monitor System Resources Using Netdata

## Objective
Monitor system performance metrics using Netdata and Docker.

## Tools Used
- Docker
- Netdata (open-source monitoring tool)

## Commands Used

```bash
docker run -d --name=netdata -p 19999:19999 --cap-add SYS_PTRACE `
  -v netdataconfig:/etc/netdata `
  -v netdatalib:/var/lib/netdata `
  -v netdatacache:/var/cache/netdata `
  -v /etc/passwd:/host/etc/passwd:ro `
  -v /etc/group:/host/etc/group:ro `
  -v /proc:/host/proc:ro `
  -v /sys:/host/sys:ro `
  -v /etc/os-release:/host/etc/os-release:ro `
  netdata/netdata
