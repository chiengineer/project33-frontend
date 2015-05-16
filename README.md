# project33-frontend
Front end for project-33

Run with `grunt serve`

nginx config for development:

```
server {
    listen       80;
    server_name  localhost;

    location / {
        root   html;
        index  index.html index.htm;
        proxy_pass  http://127.0.0.1:9000;
    }

    location /api {
      proxy_pass  http://127.0.0.1:8282;
    }

    error_page   500 502 503 504  /50x.html;
    location = /50x.html {
        root   html;
    }
}
```

connect to `http://localhost` to connect, backend server running with `script/server` will operate correctly
