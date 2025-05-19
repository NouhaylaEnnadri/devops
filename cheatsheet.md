---

##  Cheatsheet: DevOps & Docker Basics 


### Docker Images

####  Build an image from a Dockerfile

```bash
docker build -t my_image_name .
```

* `-t my_image_name` → Tags the image with a name so you can reuse it.
* `.` → Tells Docker to look for a `Dockerfile` in the current directory.

---

#### Remove an image

```bash
docker rmi my_image_name
```

- `rmi` = "remove image".

---

### Docker Containers

#### ▶ Run a container

```bash
docker run --name my_container \
  -d \
  -p 8080:80 \
  my_image_name
```

**ps:**

- `--name my_container` → Assigns a custom name to your container.
- `-d` → Detached mode (runs in the background).
- `-p 8080:80` → Port mapping:

  - Left side `8080` = your **host's port**.
  - Right side `80` = the **container’s internal port** (where the app runs).

- `my_image_name` → The image you want to run the container from.

---

#### Stop a container

```bash
docker stop my_container
```

#### Remove a container

```bash
docker rm my_container
```

#### View container logs

```bash
docker logs my_container
```

#### Get shell access inside a container

```bash
docker exec -it my_container sh
```

- `-it` = interactive terminal.
- `sh` = run shell inside the container.

---

### Docker Volumes (Persistent Storage)

####  Mount a named volume

```bash
docker run -v my_volume:/var/lib/postgresql/data ...
```

- `my_volume` = name of the volume (host-side).
- `/var/lib/postgresql/data` = location inside the container (PostgreSQL’s data directory).
- Data will persist even if the container is deleted.

---

###  Docker Networks (Enable Container Communication)

####  Create a custom bridge network

```bash
docker network create app-network
```

####  Run containers on the same network

```bash
docker run --network app-network ...
```

- This lets containers talk to each other by name (e.g., `postgres_container` can be accessed as `postgres_container` from another container on the same network).

---
