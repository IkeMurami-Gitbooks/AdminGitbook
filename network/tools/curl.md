# curl

## File Upload

```
curl -X "POST" "https://example.com/upload" \
    -H "Accept: application/json" \
    -H "Authorization: Bearer ejHj..." \
    -H "Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryjt9EifFdUkYVAkki" \
    -F 'image=@"test_out.png"' \
    -x http://127.0.0.1:8080
    
...
----WebKitFormBoundaryjt9EifFdUkYVAkki
Content-Disposition: form-data; name="image"; filename="test_out.png"

...
```

