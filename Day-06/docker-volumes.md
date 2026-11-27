# Docker Day 6 – Docker Volumes

## 1. What is a Docker Volume?

A Docker Volume is used to store data outside the container's writable layer.

Volumes help preserve data even if a container is deleted.

## 2. Why Docker Volumes?

- Persistent data storage
- Data sharing between containers
- Backup and restore
- Data remains after container removal

## 3. Important Commands

### List volumes
```bash
docker volume ls
```

### Create a volume
```bash
docker volume create myvolume
```

### Inspect a volume
```bash
docker volume inspect myvolume
```

### Run a container with a volume
```bash
docker run -it --name volume-test -v myvolume:/data alpine sh
```

### Remove a volume
```bash
docker volume rm myvolume
```

## 4. Practical Test

Inside the container:
```bash
echo "Hello Docker Volume" > /data/test.txt
cat /data/test.txt
```

Exit the container:
```bash
exit
```

Remove the container:
```bash
docker rm volume-test
```

Create another container using the same volume:
```bash
docker run --rm -v myvolume:/data alpine cat /data/test.txt
```

Expected output:
```text
Hello Docker Volume
```

## 5. Important Learning

Docker Volumes store persistent data independently of a container.

Deleting a container does not automatically delete its named volume.
