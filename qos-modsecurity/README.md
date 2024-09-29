# Qos-ModSecurity

```
docker build -t httpd-modsecurity . --no-cache
```

```
cp -rp backup volumes
```
- `-p`: Preserva proprietário, permissões e timestamps.
- `-r`: Copies recursively.

```
docker-compose up -d
```

```
docker ps -a
```

```
docker rm apache_server
```

```
docker image rm httpd-modsecurity
```
