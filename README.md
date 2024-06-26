# Install guide

## Run with docker

### Backend
```bash
 mvn clean package
 docker build --build-arg JAR_FILE=target/*.jar -t myorg/myapp .
 docker run -p 8090:8070 myorg/myapp
```

### Frontend
to be continued ...

### Database
to be continued ...

## Run with docker-compose

```bash
 mvn clean package
 sudo docker-compose build
 sudo docker-compose up
```

## Run local

- Change string in frontend/src/package.json
```json
 "proxy": "http://localhost:8080",
```

- Run in root folder of project
```bash
 mvn spring-boot:run -Dspring-boot.run.profiles=test
 cd frontend
 npm start
```

## Endpoints API

| REQUEST | Endpoint                  | Description                                    |
|---------|---------------------------|------------------------------------------------|
| GET     | `/`                       | Main page                                      |
| GET     | `/items`                  | List of Market items                           |
| GET     | `/items/{item_id}`        | Item with `id` information                     |
| POST    | `/items/{item_id}/delete` | Delete item with `id` (Admin account required) |
| POST    | `/items/create`           | Create item (Admin account required)           |
|         | `/register`               | User registration                              |
|         | `/login`                  | User authorization                             |
| GET     | `/account/{username}`     | Account information                            |


## Requirements

* java 21
* mvn 3.8.7
* docker

---

## To do
- [x] Connect Database (Postgres)
- [ ] Login
    - [x] JWT token support
    - [ ] userEntity registration (with google?)
    - [ ] admin role
- [ ] Html forms
- [ ] CSS
- [ ] Add Logic to Database
  - [x] Item price update
  - [x] Users registration
  - [ ] order creation
  - [ ] userEntity order history
  - [ ] userEntity money
- [x] Docker