## Vue.js

### How to start new project in docker-compose

Service in compose.yml file:

```yml
  vue:
    build:
      context: .
      dockerfile: ./compose/local/vue/Dockerfile
    volumes:
      - ./vue:/app
    depends_on:
      - django
    ports:
      - 5000:8080
```

Dockerfile:

```Dockerfile
FROM node:14.3.0

RUN npm install -g vue
RUN npm install @vue/cli
RUN npm install axios

WORKDIR /app

CMD npm run serve
```

Launch build process:

    docker-compose -f local.yml build

If such trouble is appeared:

    npm ERR! Response timeout...

try to use another version of Node.


Check weither vue-cli has been installed:

    docker-compose -f local.yml run --rm vue vue --version

Creating new vue project:

    docker-compose -f local.yml run --rm vue vue create <project_name>
