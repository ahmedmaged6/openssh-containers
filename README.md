# Docker SSH Server and Client Setup

This project demonstrates how to create and configure two Docker containers: one as an SSH server and the other as an SSH client. The containers are managed using Docker Compose.

## Features
- **SSH Server**: A container running an OpenSSH server configured for root login.
- **SSH Client**: A container designed to interact with the SSH server.
- Built from a common Dockerfile.
- Utilizes `docker-compose` for simplified management.

## Prerequisites
- Docker and Docker Compose installed on your machine.

## Usage
1. Clone this repository:
   ```bash
   git clone https://github.com/ahmedmaged6/openssh-containers.git
   cd openssh-containers
   ```

2. Build and start the containers:
   ```bash
   docker-compose up -d --build
   ```

3. Access the SSH client container:
   ```bash
   docker exec -it openssh-containers-ssh-client-1 bash
   ```

4. From the SSH client, connect to the SSH server:
   ```bash
   ssh root@openssh-containers-ssh-server-1
   ```
   The default password is `0`.


## Cleanup
Stop and remove the containers:
```bash
docker-compose down
```

## Notes
- The `ssh-server` service is configured to always restart.
- The `ssh-client` service runs indefinitely with `sleep infinity`.

---

