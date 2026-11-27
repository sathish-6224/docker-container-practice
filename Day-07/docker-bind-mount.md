# Docker Day 7 – Bind Mount

## 1. What is Bind Mount?

A Bind Mount connects a specific folder or file from the host machine to a directory inside a Docker container.

## 2. Why Bind Mount?

- Share files between Windows and containers
- Modify files from the host machine
- Useful for application development
- Changes on the host can be reflected inside the container

## 3. Important Command

```bash
docker run -it --name bind-test -v /host/path:/app alpine sh
```

## 4. Verify Bind Mount

Inside the container:

```bash
ls -l /app
cat /app/test.txt
```

## 5. Volume vs Bind Mount

| Docker Volume | Bind Mount |
|---|---|
| Managed by Docker | Uses a specific host path |
| Stored in Docker-managed storage | Uses a host folder or file |
| Good for persistent data | Good for sharing project files |

## 6. Learning Summary

Bind Mount allows a host directory to be connected to a container directory. It is useful for development and sharing files.
