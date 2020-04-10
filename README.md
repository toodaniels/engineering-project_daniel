##  Solución de [engineering-project](https://github.com/expandaventures/engineering-project) - Daniel Torres

### Proceso de ejecución local

#### API HTTP Rest - [vehicles-api](https://github.com/toodaniels/vehicles-api)

[API en Heroku](https://vehicles-engineering-project.herokuapp.com/api/v1)

Clonar repo:

    git clone https://github.com/toodaniels/vehicles-api.git
    cd vehicles-api 
Instalar dependencias con npm:

	npm i 

Instalar dependencias con yarn:

	yarn 

Crear archivo con variables de entorno:
		
	touch .env 

Editar archivo .env:

	PORT=5000
    MONGO_URL="Mongo url"

Ejecutar :
		
		npm start 

#### API APP - [vehicles-app](https://github.com/toodaniels/vehicles-app)

[APP en heroku](https://vehicles-daniel-torres.herokuapp.com/)
Clonar repo:

    git clone https://github.com/toodaniels/vehicles-app.git

Instalar dependencias con npm:

	npm i 

Instalar dependencias con yarn:

	yarn 

Crear archivo con variables de entorno:
		
	touch .env 

Editar archivo .env para conectar a la API Rest:

		REACT_APP_API = 'http://localhost:5000'

Ejecutar :
		
		npm start 


## CURL

### Signup user - POST /api/v1/signup

	curl -d '{"email":"test535@gmail.com", "password":"test535", "name":"Daniel Torres"}' -H "Content-Type: application/json" -X POST https://vehicles-engineering-project.herokuapp.com/api/v1/signup


Response 201 Created

	Content-Type : application/json;

### Signin user- POST /api/v1/signin

	curl -d '{"email":"test535@gmail.com", "password":"test535"}' -H "Content-Type: application/json" -X POST https://vehicles-engineering-project.herokuapp.com/api/v1/signin



Response 200 OK

	Content-Type : application/json;

Use <ACCESS_TOKEN> = response["token"]

### Create Vehicle - POST /api/v1/auth/vehicles

	curl -d '{"plate":"test535", "location":[0, 1]}' -H "Content-Type: application/json" -H "Authorization: Bearer <ACCESS_TOKEN>"  -X POST https://vehicles-engineering-project.herokuapp.com/api/v1/auth/vehicles

Response 201 Created

	Content-Type : application/json;

### Get user vehicles - GET /api/v1/auth/vehicles

	curl -H "Authorization: Bearer <ACCESS_TOKEN>" https://vehicles-engineering-project.herokuapp.com/api/v1/auth/vehicles


Response 200 OK

	Content-Type : application/json;


### Update vehicle - PUT /api/v1/auth/vehicles/:plate

	curl -d '{"plate":"test535", "location":[1, 2]}' -H "Content-Type: application/json" -H "Authorization: Bearer Bearer <ACCESS_TOKEN>"  -X PUT https://vehicles-engineering-project.herokuapp.com/api/v1/auth/vehicles/test535


Response 204 No Content

### Delete vehicle - DELETE /api/v1/auth/vehicles/:plate

	curl -H "Authorization: Bearer <ACCESS_TOKEN>"  -X DELETE https://vehicles-engineering-project.herokuapp.com/api/v1/auth/vehicles/test535

Response 204 No Content
