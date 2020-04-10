##  Solución de [engineering-project](https://github.com/expandaventures/engineering-project) - Daniel Torres

### Proceso de ejecución local

#### API HTTP Rest - [vehicles-api](https://github.com/toodaniels/vehicles-api)

[API en Heroku](https://vehicles-engineering-project.herokuapp.com/)

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