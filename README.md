# About

"Maintenance Exporter" is a prometheus exporter that exports a metric to signal 
wether or not a maintenance window is active. This metric can then be used in 
[alerting rules](https://prometheus.io/docs/prometheus/latest/configuration/alerting_rules/#alerting-rules) 
to suppress alerting during the maintenance window.

# Example

If the `config.yaml.sample` is used, the following metrics would be produced:
```
> curl -s http://localhost:9099/metrics 
maintenance_active{name="weekend"} 0
maintenance_active{service="UUID as a service",service_level="staging",name="staging restore",team="haxx0rz"} 0
maintenance_active{service_level="development",name="testy mctestface"} 1
```


