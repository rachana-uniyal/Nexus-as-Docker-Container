# Nexus-as-Docker-Container

## Demo Project:

### Deploy Nexus as Docker Container

**Technologies used:** Docker, Nexus, DigitalOcean, Linux

**Project Description:**

- Create and Configure Droplet
- Set up and run Nexus as a Docker container


### Steps

1. Created a new Droplet
2. Configured Firewall rule to open port 22 for SSHing
3. Installed Docker on Droplet:

   ```bash
   apt update
   apt install docker.io
   ```

4. Created docker volume to persist Nexus data:

   ```bash
   docker volume create --name nexus-data
   ```

5. Ran Nexus as Docker container with necessary parameters:

   ```bash
   docker run -d -p 8081:8081 --name nexus -v nexus-data:/nexus-data sonatype/nexus3
   ```

6. Accessed Nexus in browser:

   - Access volume:
     
     - To see a list of docker volumes: `docker volume ls`
     - To see details (mount point, labels, etc.) of a specific volume: `docker inspect nexus-data`
```
