Approach allows to filter logs by appName using file.(appName) or by module name file.(appName).(moduleName)

Logs paths:
```
-logs
----monkey
-------plugin1.jsonl
-------plugin2.jsonl
----anotherApp
-------anotherApp.json
```
Fluen bit configuration:
```yaml
inputs:
	# https://docs.fluentbit.io/manual/pipeline/inputs/tail  
	# It is for applications without specific directory for application logs. App name would be parsed from the file name <appName>.jsonl  
	- name: tail  
	  tag: file_not_modular.*  
	  path: /logs/*.jsonl  
	  db: /storage/file_logs1.db # keep track of monitored files and offsets.  
	  parser: json  
	  key: message # see https://docs.fluentbit.io/manual/pipeline/inputs/tail  
	  refresh_interval: 10 # the interval of refreshing the list of watched files in seconds.  
	  storage.type: filesystem  
	  path_key: logfile_path  
	  
	# https://docs.fluentbit.io/manual/pipeline/inputs/tail  
	# It is for applications with modular logging structure /<appName>/<compName>.jsonl  
	- name: tail  
	  tag: file_modular.*  
	  path: /logs/*/*.jsonl  
	  db: /storage/file_logs2.db # keep track of monitored files and offsets.  
	  parser: json  
	  key: message # see https://docs.fluentbit.io/manual/pipeline/inputs/tail  
	  refresh_interval: 10 # the interval of refreshing the list of watched files in seconds.  
	  storage.type: filesystem  
	  path_key: logfile_path
filters:
    - name: rewrite_tag  
      match: file_modular.*  
      rule: $logfile_path /(.*/)([^/]+)/([^/]+)\.jsonl  file.$2.$3 false  
      emitter_name: re_emitted_modular_files  
#      emitter_name: re_emitted_docker  
  
    - name: rewrite_tag  
      match: file_not_modular.*  
      rule: $logfile_path /(.*/)([^/]+)\.jsonl  file.$2 false  
      emitter_name: re_emitted_files
   - name: record_modifier  

	- name: modify  
	  match: file.flog-app*  
	  hard_rename:  
	    - host _host 
```