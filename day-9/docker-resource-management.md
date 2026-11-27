# Docker Day 9 – Container Resource Management

## Objective
Learn how to monitor and limit CPU and memory usage of Docker containers.

## 1. Memory Limit

Command:

```bash
docker run -d --name memory-test --memory=100m alpine sleep 3600
```

Explanation:
- `-d`: Run in background
- `--name`: Assign container name
- `--memory=100m`: Set maximum memory limit to 100 MB
- `alpine`: Docker image
- `sleep 3600`: Keep container running for one hour

Verify:

```bash
docker inspect memory-test --format='{{.HostConfig.Memory}}'
```

Expected output:

```text
104857600
```

## 2. CPU Limit

Command:

```bash
docker run -d --name cpu-test --cpus=0.5 alpine sleep 3600
```

Explanation:
- `--cpus=0.5`: Limit the container to half a CPU core.

Verify:

```bash
docker inspect cpu-test --format='{{.HostConfig.NanoCpus}}'
```

Expected output:

```text
500000000
```

## 3. Monitor Resource Usage

```bash
docker stats
```

Displays:
- CPU usage
- Memory usage and limit
- Network I/O
- Block I/O
- Process count

Press `Ctrl + C` to exit.

## What I Learned

- How to set a Docker memory limit.
- How to set a Docker CPU limit.
- How to monitor container resource usage.
- How to verify resource limits using `docker inspect`.

## Quiz Result

Score: 30/30

Status: Completed
