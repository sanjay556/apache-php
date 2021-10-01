# apache-php

Apache php Dockerfile with http2 enabled

```
docker run -d -p 8000:80  \
  -v /your/php/source/code:/var/www/html \
  --name my-application  apache-phpss:latest
```
