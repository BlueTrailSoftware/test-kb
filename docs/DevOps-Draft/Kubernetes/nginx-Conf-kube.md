```nginx
# auto detects a good number of processes to run
worker_processes auto;

#Provides the configuration file context in which the directives that affect connection processing are specified.
events {
    # Sets the maximum number of simultaneous connections that can be opened by a worker process.
    worker_connections 8000;
    # Tells the worker to accept multiple connections at a time
    multi_accept on;
}

http {
    # what times to include
    include /etc/nginx/mime.types;
    # what is the default one
    default_type application/octet-stream;

    # Sets the path, format, and configuration for a buffered log write
    log_format compression '$remote_addr - $remote_user [$time_local] '
    '"$request" $status $upstream_addr '
    '"$http_referer" "$http_user_agent"';

    server {
        # listen on port 8080
        listen 8080;
        listen [::]:8080;

        # TIME OUTS
        proxy_connect_timeout 600; 
        proxy_send_timeout 1800; 
        proxy_read_timeout 1800; 
        send_timeout 1800;

        # save logs here
        access_log /var/log/nginx/access.log compression;

        # GZIP
        gzip on;
        gzip_http_version 1.0;
        gzip_comp_level 5; # 1-9
        gzip_min_length 256;
        gzip_proxied any;
        gzip_vary on;

        # MIME-types
        gzip_types
        application/atom+xml
        application/javascript
        application/json
        application/rss+xml
        application/vnd.ms-fontobject
        application/x-font-ttf
        application/x-web-app-manifest+json
        application/xhtml+xml
        application/xml
        font/opentype
        image/svg+xml
        image/x-icon
        text/css
        text/plain
        text/x-component;

        # where the root here
        root /var/www;
        # what file to server as index
        index index.html index.htm;

        location / {
            # First attempt to serve request as file, then
            # as directory, then fall back to redirecting to index.html
            try_files $uri $uri/ /index.html;
        }

        # Media: images, icons, video, audio, HTC
        location ~* \.(?:jpg|jpeg|gif|png|ico|cur|gz|svg|svgz|mp4|ogg|ogv|webm|htc)$ {
            expires 1M;
            access_log off;
            add_header Cache-Control "public";
        }

        # Javascript and CSS files
        location ~* \.(?:css|js)$ {
            try_files $uri =404;
            expires 1y;
            access_log off;
            add_header Cache-Control "public";
        }

        # Any route containing a file extension (e.g. /devicesfile.js)
        location ~ ^.+\..+$ {
            try_files $uri =404;
        }
    }
}
```

