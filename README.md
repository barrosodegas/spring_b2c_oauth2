# Configuration server project

### Environment variables
- CONFIG_SERVER_PASSWORD=Your server password
- CONFIG_SERVER_PORT=XXXX
- CONFIG_SERVER_REPOSITORY_URI=Your SSH GIT URI
- CONFIG_SERVER_USER=You user
- CONFIG_SERVER_DEFAULT_LABEL=master or any

### Java version
- 17
- Encoded in UTF-8

### Spring boot version:
- 3.1.2

### Spring boot properties
- 

# Customers project
- B2C spring boot mvc project with oauth2, keycloak auth server and configuration server sample.

### Environment variables
- CONFIG_SERVER_HOST=localhost:XXXX
- CONFIG_SERVER_FILE_PROPERTIES_NAME=Any file properties name liek: customers of type: .yml or .properties
- CONFIG_SERVER_PASSWORD=You server password
- CONFIG_SERVER_PROFILE=Profile env like: dev, qa or prod
- CONFIG_SERVER_USER=Your server user
- CUSTOMER_SERVER_PORT=XXXX

### Java version
- 17
- Encoded in UTF-8

### Spring boot version:
- 3.1.2

# Keycloak oauth server

### Run by docker-compose yaml
- docker-compose -f docker-compose.yaml up -d
- Default Port: 8080
- Version 22.0.1
- Default user and password: admin
