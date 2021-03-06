# Boldo - Server

Boldo can be found in any Paraguayan household. It is a magic tea that can calm all kind of stomachache.

This is the server for Boldo - a telemedicine solution for doctors and patients. 

The server exposes APIs that are consumed by the web app and the mobile app.

## Getting Started

1. This project has the following dependencies:

   - node.js (v12 or newer)
   - mongoDB (v4.2 or newer)
   - Optional dependency: 
     - Docker (v19 or newer) for building the image

2. Install dependencies: `npm i`

3. Create a `.env` file in the project's root folder and add these contents:

   ```
   SECRET = secure_server_secret
   MONGODB_URI = mongodb://localhost:27017/boldo
   
   # ###################### Online ######################
   # CLIENT_ADDRESS = https://boldo.penguin.software
   # KEYCLOAK_ADDRESS = https://sso-test.pti.org.py/auth
   IHUB_ADDRESS = https://sso-test.pti.org.py/api
   # BOLDO_CORS = https://boldo.penguin.software
   
   # ###################### Local ######################
   CLIENT_ADDRESS = http://localhost:3000
   KEYCLOAK_ADDRESS = http://localhost:8080/auth
   BOLDO_CORS = https://localhost:3000
   ```

4. Ensure the server runs in the timezone `America/Asuncion`!

5. `npm run dev` - to start server on [localhost:8008](http://localhost:8008)

## Run with docker

To build the docker image use the following command:

```
docker build -t boldo-server .
```

Remember to set your `.env` file.

 After that you can test it running the following command:

```bash
docker run --rm -it -p 8008:8008 boldo-server
```

## Contributing

The project is currently under heavy development but contributors are welcome. For bugs or feature requests or eventual contributions, just open an issue. Contribution guidelines will be available shortly.

## Authors and License

This project was created as part of the iHub COVID-19 project in collaboration between [Penguin Academy](https://penguin.academy) and [PTI (Parque Tecnológico Itaipu Paraguay)](http://pti.org.py).

This project is licensed under
[AGPL v3](LICENSE)
