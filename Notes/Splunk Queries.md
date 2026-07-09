
failed login events
```
sourcetype=auth* "authentication failure" | stats count by user | sort -count
```

