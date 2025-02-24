Starting up NGINX and echo-server
```
docker compose up -d nginx echo-server
```

To test the rate limit, use (requests will be blocked when the limit is exceeded):
```
docker compose run --rm -it ab -n 1000 -c 50 http://nginx/
```

To test the bypass rate limit, in assets, use (all requests will be served):
```
docker compose run --rm -it ab -n 1000 -c 50 http://nginx/test.css
```
or:
```
docker compose run --rm -it ab -n 1000 -c 50 http://nginx/test.js
```