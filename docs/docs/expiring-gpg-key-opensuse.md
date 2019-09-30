1. Use the existing docker image with `osc` tool installed. If you want,
you can install it locally and follow these steps.
```
docker run --name=osc --rm -it rtcamp/nginx-build bash
docker exec -it osc bash
```

2. Extend the expiry date for the key,
```
osc signkey --extend home:rtCamp
```

3. Get the updated key,
```
osc signkey home:rtCamp > public.key
```

4. Upload to a keyserver,
```
gpg --import public.key
gpg --keyserver keyserver.ubuntu.com --send-key '3050AC3CD2AE6F03'
```