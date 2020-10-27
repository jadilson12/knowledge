---
description: >-
  If you are using Docker-Machine, make sure your are talking to the right one.
  Execute the command docker-machine ls to find which one is currently active.
  It is also recommended to always redo the com
---

# How to Do a Clean Restart of a Docker Instance

### Procedure



1. Stop the container\(s\) using the following command:

   ```text
   docker-compose down
   ```

2. Delete all containers using the following command:

   ```text
   docker rm -f $(docker ps -a -q)
   ```

3. Delete all volumes using the following command:

   ```text
   docker volume rm $(docker volume ls -q)
   ```

4. Restart the containers using the following command:

   ```text
   docker-compose up -d
   ```

