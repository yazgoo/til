# limit program CPU usage

```
systemd-run --user --scope -p 'CPUQuota=300%' -p 'MemoryMax=16G' sbt run
```
