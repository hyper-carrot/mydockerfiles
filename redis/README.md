## Usage

1. Build image

```bash
sudo docker build -t="<image name>" .
```

2. Run container

```bash
sudo docker run -d -t -p 6379 -v /path/to/redis/config/file:/opt/conf <image name> /opt/conf/redis.conf
```

3. Check redis status

```bash
sudo docker exec -i <image name> ps aux | grep redis
```

4. Connect redis

```bash
redis-cli -p `sudo docker port <image name> 6379 | awk -F":" '{print $2}'`
```
