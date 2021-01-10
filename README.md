# App-wordpress
Instalar Wordpress
-Descargar el paquete y descomprimir en su servidor de PHP. https://es.wordpress.org/download/
-Crear una base de datos en PHPMyAdmin
-Instalar Wordpress


## Postman
Hacer la siguiente petición GET:
```
 /wp-json/wp/v2/posts
```
http://localhost:80/nombre-proyecto/wp-json/wp/v2/posts


## JWT
Ir a Plugings->Añadir nuevo->JWT Authentication for WP REST API e instalar
Abrir .htaccess y agregar:

RewriteCond %{HTTP:Authorization} ^(.*)
RewriteRule ^(.*) - [E=HTTP_AUTHORIZATION:%1]
SetEnvIf Authorization "(.*)" HTTP_AUTHORIZATION=$1

## Abrir wp-config y agregar:

define('JWT_AUTH_SECRET_KEY', 'your-top-secret-key');
define('JWT_AUTH_CORS_ENABLE', true);

# Obtener Token
Hacer la siguiente petición POST:

http://localhost:80/nombre-proyecto/wp-json/jwt-auth/v1/token

## Agregar Headers:

```
Content-Type      application/json
```

## Body raw:
```
{
	"username": "bluuweb",
	"password": "123123"
}
```

## Y tendrás como respuesta:

{
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9sb2NhbGhvc3RcL3dvcmRwcmVzcy1hcGlcL3dvcmRwcmVzcy0xXC93b3JkcHJlc3MiLCJpYXQiOjE1NzIyNzQ4NzgsIm5iZiI6MTU3MjI3NDg3OCwiZXhwIjoxNTcyODc5Njc4LCJkYXRhIjp7InVzZXIiOnsiaWQiOiIxIn19fQ.7eG3MIBl6ITJ26xEfNJDpnwykdpiNXoxaP_zC-9qhxk",
    "user_email": "contacto@bluuweb.cl",
    "user_nicename": "bluuweb",
    "user_display_name": "bluuweb"
}

## POST: Crear entrada
Hacer la siguiente petición POST:

```
http://localhost:80/nombre-proyecto/wp-json/wp/v2/posts
```
## Headers:

```
Authorization
```

Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9sb2NhbGhvc3RcL3dvcmRwcmVzcy1hcGlcL3dvcmRwcmVzcy0xXC93b3JkcHJlc3MiLCJpYXQiOjE1NzIyNzQ4NzgsIm5iZiI6MTU3MjI3NDg3OCwiZXhwIjoxNTcyODc5Njc4LCJkYXRhIjp7InVzZXIiOnsiaWQiOiIxIn19fQ.7eG3MIBl6ITJ26xEfNJDpnwykdpiNXoxaP_zC-9qhxk
Body x-www-form-urlrencoded

title     Entrada prueba 1
content   Entrada prueba 1 contenido
status    publish

## Instalación Vue CLI
Hacer este paso solo si no tienes instalado Vue CLI
```
npm install @vue/cli -g
```

## Nuevo proyecto de Vue
```
vue create app-wordpress-api
cd app-wordpress-api
```

## Agregar Vuetify
```
vue add vuetify
```

## Vue-axios
https://www.npmjs.com/package/vue-axios

```
npm install --save axios vue-axios
```

import axios from 'axios'
import VueAxios from 'vue-axios'
 
Vue.use(VueAxios, axios)

### // Agregamos la URL base de nuestra API
axios.defaults.baseURL = 'http://localhost:80/nombre-proyecto/';

## App.vue Inicial asi
<template>
  <v-app>
    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

## router/index.js
{
  path: '/crud',
  name: 'crud',
  component: () => import(/* webpackChunkName: "about" */ '../views/Crud.vue')
},
## Project setup

```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
