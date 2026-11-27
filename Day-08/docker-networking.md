# Day 8 – Docker Networking

## Topics Covered
- Docker Network Basics
- Bridge Network
- Custom Bridge Network
- Container-to-Container Communication
- Container Name Resolution

## Practical Commands

```powershell
docker network ls
docker network create my-custom-network
docker run -dit --name web1 --network my-custom-network alpine
docker run -dit --name app1 --network my-custom-network alpine
docker ps
docker exec app1 ping -c 4 web1
```

## Practical Result

- Created a custom bridge network.
- Connected two Alpine containers.
- Successfully communicated using the container name `web1`.
- Ping test: 4 packets received, 0% packet loss.

## Learning Outcome

Learned how Docker containers communicate with each other through a custom bridge network using container name resolution.
