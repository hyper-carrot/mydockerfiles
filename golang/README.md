## Usage

1. Build image

```bash
sudo docker build -t="<image name>" .
```

2. Check go runtime & version

```bash
sudo docker run -i -t <image name>
```

2. Run container

```bash
sudo docker run -d -t -p <expose port> -v /path/to/gopath/src:/projects/golang/src <image name> <go command & params> 
```
