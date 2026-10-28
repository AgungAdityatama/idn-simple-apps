# Create env variable

```
vim .env
```

```
DB_NAME=training
DB_HOST=ipaddress
DB_USER=peserta
DB_PASS=password
APP_PORT=3000
```

sonar-scanner-npm \
 -Dsonar.host.url=http://172.23.13.86:9000 \
 -Dsonar.token=sqp_54f9e51bc0dd43d3d4d74ca96ecc7aec1ee5f11a \
 -Dsonar.projectKey=idn-simple-apps

sonar-scanner \
 -Dsonar.projectKey=idn-simple-apps \
 -Dsonar.sources=. \
 -Dsonar.host.url=http://172.23.13.86:9000 \
 -Dsonar.token=sqp_33ce22003ee0f7ef9a01250d296c7bc6e607115c
