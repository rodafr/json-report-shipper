json-report-shipper
===========

Extension of:
JSON reporting plugin for [Gauge](http://gauge.org)

This plugin ships the JSON report to an API.

Installation
------------
### Offline installation
* Build the plugin first ...
```
gauge install json-report-shipper --file <path_to_plugin_zip_file>
```

### Usage

Add this plugin to your Gauge project by registering it in `manifest.json` file. 


By default, reports are generated in `reports/json-report-shipper` directory of your Gauge project. You can set a custom location by setting the below mentioned property in `default.properties` file of `env/default` directory.

```
# The path to the gauge reports directory. Should be either relative to the project directory or an absolute path
gauge_reports_dir = reports
```

You can also choose to override the reports after each execution or retain all of them as follows.

```
# Set as false if gauge reports should not be overwritten on each execution. A new time-stamped directory will be created on each execution.
overwrite_reports = true
```

Set the API URL in your environment file(s) like so:
```
# Report API url
report_api_url = http://127.0.0.1:8080/api/reports
```


Build from Source
-----------------

### Requirements
* [Golang](http://golang.org/)

### Compiling

```
go run build/make.go
```

For cross-platform compilation

```
go run build/make.go --all-platforms
```

### Installing
After compilation

```
go run build/make.go --install
```

Installing to a CUSTOM_LOCATION

```
go run build/make.go --install --plugin-prefix CUSTOM_LOCATION
```

### Creating distributable

Note: Run after compiling

```
go run build/make.go --distro
```

For distributable across platforms: Windows and Linux for both x86 and x86_64

```
go run build/make.go --distro --all-platforms
```