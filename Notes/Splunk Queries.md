
failed login events
```sh
sourcetype=auth* "authentication failure" | stats count by user | sort -count
```

