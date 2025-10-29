
### set value
```bash
curl -X POST http://www.thomas-hub.com:8083/api/count \
 -H "Authorization: Bearer 123456" -H "Content-Type: application/json" \
 -d '{"op":"set","value":4}'
```


### increment

```bash
curl -X POST http://www.thomas-hub.com:8083/api/count \
 -H "Authorization: Bearer 123456" -H "Content-Type: application/json" \
 -d '{"op":"inc","value":1}'
```