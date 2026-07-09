
failed login events
```js
sourcetype=auth* "authentication failure" | stats count by user | sort -count
```

