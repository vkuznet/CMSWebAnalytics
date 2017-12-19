# CMSWebAnalytics
A project to perform CMS web analytics.

### Tasks
- write Go-based parser to parse apache log files. Here is an example of apache
  entry:
```
[12/Dec/2017:00:59:59 +0100] cmsweb.cern.ch xxxx:yyyy:zzz:a8::100:21a "GET /couchdb/reqmgr_workload_cache/pdmvserv_task_B2G -RunIISummer16DR80Premix-02387__v1_T_171015_165132_2461 HTTP/1.1" 200 [data: 3358 in 26751 out 7823 body 197194 us ] [auth: TLSv1.2 DHE-RSA-AES256-GCM-SHA384 "/DC=YY/DC=BLA/OU=FOO/CN=bla" "-" ] [ref: "-" "WMCore.Services.Requests/v001" ]
```
- create output DataFrames (in CSV and JSON) formats with the following content:
  - date,service,request_count
  - date,service,DN,request_count
  the later DataFrame will be used to identify most active users
- use go-stomp package to send data to CERN MONIT system, see examples
  github.com/thomasmodeneis/go-amq-poc and github.com/go-stomp/stomp

