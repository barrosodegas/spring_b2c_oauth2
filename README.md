# Configuration Server Project

### Goal
- Centralize access to properties used in client APIs in a secure way.

### Environment variables
- CONFIG_SERVER_USER=You user
- CONFIG_SERVER_PASSWORD=Your server password
- CONFIG_SERVER_PORT=XXXX
- CONFIG_SERVER_REPOSITORY_URI=Your SSH GIT URI
- CONFIG_SERVER_DEFAULT_LABEL=Your default branch

### Java version
- 17
- Encoded in UTF-8

### Spring boot version:
- 3.1.2

### To run this project you need
- Have java 17 installed locally
- Set the above environment variables
- Configure your local environment to handle Git repositories with SSH access


# Keycloak Oauth Server

### Goal
- Authenticate users and authorize access to sensitive data.

### Keycloak version
- 22.0.1

### Run by docker-compose yaml
- docker-compose -f docker-compose.yaml up -d
- Default Port: 8080
- Default user and password: admin

### Steps to create secutiry B2C access 
- Create a new realm with default configurations
- Create a new user with default configurations
- Create a credentials by password to user
- Create a new client with Client Authentication and Authorization
- Create a credentials by client_id and secret

### To run this project you need
- Have docker installed with docker compose in the latest version


# Customers Project
- B2C spring boot mvc project with oauth2, keycloak auth server and configuration server sample.

### Goal
- Allow protected access to customer listings.

### Environment variables
- CONFIG_SERVER_HOST=localhost:XXXX
- CONFIG_SERVER_FILE_PROPERTIES_NAME=Any file properties name like: customers of type: .yml or .properties
- CONFIG_SERVER_PROFILE=Profile env like: dev, qa or prod
- CONFIG_SERVER_USER=Your server user
- CONFIG_SERVER_PASSWORD=You server password
- CUSTOMER_SERVER_PORT=XXXX

### Java version
- 17
- Encoded in UTF-8

### Spring boot version:
- 3.1.2

### Spring boot properties
- spring.security.oauth2.client.registration.keycloak.client-id: Your keycloak client ID
- spring.security.oauth2.client.registration.keycloak.client-secret: You client secret key
- spring.security.oauth2.client.registration.keycloak.authorization-grant-type: authorization_code
- spring.security.oauth2.client.registration.keycloak.scope: openid
- spring.security.oauth2.client.registration.keycloak.redirect-uri: http://localhost:XXXX Customer Port/login/oauth2/code/Your Keycloak client ID
- spring.security.oauth2.client.provider.keycloak.issuer-uri: http://localhost:XXXX Keycloak Port/realms/Your keycloak realm
- spring.security.oauth2.client.provider.keycloak.user-name-attribute: preferred_username
- spring.security.oauth2.resourceserver.jwt.issuer-uri: http://localhost:XXXX Keycloak Port/realms/Your keycloak realm

### To run this project you need
- Have the configuration server project configured and running
- Have the Keycloak server configured and running
- Configure the environment variables mentioned above
- Have Java version 17 installed locally
- Have versioned in the Git properties project the yaml file that will be used in the project being post-fixed by the environment profile type.
  Example: customers-qa.yml
