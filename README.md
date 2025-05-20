# Tp part 01 - Docker

#### Question 1-1 :

- using the -e flag to set environment variables is important for _security_ reasons. especially for sensitive data like passwords.so with the -e flag they stay out of the image while being pushed into github, and they will be provided securely at the runtime.

#### Question 1-2 :

- we need to use volumes for persistent data so it can't be lost once we remove the container.

#### Question 1-4:

- When we make a Docker image for a Java app, there are two parts : building the app and running the app.a multi-stage build is used to build the app and then a final image is created with the built app.

#### Question 1-5:

- now i have my backedn and my http server in different containers, so by using the reverse proxy server http server can take the requests from the clients and forward to them

#### Question 1-6:

- it's important to use docker compose cause then it's eaiser to manage the containers and the network and automated instead of running everthing manually.

#### Question 1-7:

```bash
docker-compose build
```

=>Builds or rebuilds services defined in the compose file.


```bash
docker-compose build
```

=>Builds or rebuilds services defined in the compose file.

