# Microsoft .NET Core ASP.NET Prometheus Example

This example project is based on this [post](https://www.olivercoding.com/2018-07-22-prometheus-dotnetcore/).

```console
$ dotnet --version
3.1.401
$
$ dotnet new mvc -o dotnetcore-prometheus-example
$
$ cd $_
$
$
$ dotnet run
$
$ dotnet add package prometheus-net.AspNetCore
$
```

```console
$ curl --insecure --head https://localhost:5001/metrics
HTTP/2 200
date: Tue, 15 Sep 2020 12:54:39 GMT
content-type: text/plain; version=0.0.4; charset=utf-8
server: Kestrel

$
curl --insecure https://localhost:5001/metrics
# HELP PathCounter Counts requests to endpoints
# TYPE PathCounter counter
PathCounter{method="HEAD",endpoint="/metrics"} 1
PathCounter{method="GET",endpoint="/metrics"} 2
# HELP dotnet_collection_count_total GC collection count
# TYPE dotnet_collection_count_total counter
dotnet_collection_count_total{generation="0"} 0
dotnet_collection_count_total{generation="2"} 0
dotnet_collection_count_total{generation="1"} 0
# HELP process_open_handles Number of open handles
# TYPE process_open_handles gauge
process_open_handles 174
# HELP process_start_time_seconds Start time of the process since unix epoch in seconds.
# TYPE process_start_time_seconds gauge
process_start_time_seconds 1600174459.87
# HELP process_working_set_bytes Process working set
# TYPE process_working_set_bytes gauge
process_working_set_bytes 101765120
# HELP dotnet_total_memory_bytes Total known allocated memory
# TYPE dotnet_total_memory_bytes gauge
dotnet_total_memory_bytes 6424792
# HELP process_private_memory_bytes Process private memory size
# TYPE process_private_memory_bytes gauge
process_private_memory_bytes 187420672
# HELP process_virtual_memory_bytes Virtual memory size in bytes.
# TYPE process_virtual_memory_bytes gauge
process_virtual_memory_bytes 21876895744
# HELP process_cpu_seconds_total Total user and system CPU time spent in seconds.
# TYPE process_cpu_seconds_total counter
process_cpu_seconds_total 1.3899999
# HELP process_num_threads Total number of threads
# TYPE process_num_threads gauge
process_num_threads 20
$
```
