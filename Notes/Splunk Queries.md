
failed login events
```splunk
sourcetype=auth* "authentication failure" | stats count by user | sort -count
```

