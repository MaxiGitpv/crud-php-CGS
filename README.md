# ▶️ INSTALACIÓN

Usuarios y contraseña de CGS

<p>Usuario: Administrador</p>
<p>Clave: Administrador</p>

## CRUD-PHP-CGS

MODELO VISTA CONTROLADOR

## **Descripción**

Se realiza un breve resumen de las características principales de la adaptación del patrón Modelo Vista Controlador al lenguaje [PHP](https://www.juntadeandalucia.es/servicios/madeja/glossary/12/letterp#term571). Hasta la aparición de los diferentes frameworks dentro del mundo del desarrollo de [PHP](https://www.juntadeandalucia.es/servicios/madeja/glossary/12/letterp#term571), existían dudas sobre el éxito de la aplicación de este patrón a los desarrollos de [PHP](https://www.juntadeandalucia.es/servicios/madeja/glossary/12/letterp#term571). Actualmente, gracias a estos frameworks, su aplicación es más sencilla y los beneficios producidos son más reconocibles.

## **Características**

El patrón Modelo-Vista-Controlador para el diseño de aplicaciones Web es un estándar de la industria en el mundo Java. Hay muchos libros y recursos excelentes disponibles sobre el tema que ayudan a acelerar el proceso de aprendizaje para el equipo de desarrollo. En un breve repaso, MVC viene de Model, View, Controller, o bien: Modelo, Vista y Controlador. La idea básica de este patrón es separar nuestros sistemas en tres capas, el Modelo, la Vista y el Controlador.

- El **Modelo** se encarga de todo lo que tiene que ver con la persistencia de datos. Guarda y recupera la información del medio persistente que utilicemos, ya sea una base de datos, ficheros de texto, XML, etc.
- La **Vista** presenta la información obtenida con el modelo de manera que el usuario la pueda visualizar.
- El **Controlador**, dependiendo de la acción solicitada por el usuario, es el que pide al modelo la información necesaria e invoca a la plantilla(de la vista) que corresponda para que la información sea presentada.

Hay algo de esfuerzo necesario para aprender a utilizar un marco MVC en [php](https://www.juntadeandalucia.es/servicios/madeja/glossary/12/letterp#term571). Sin embargo, para el desarrollador de aplicaciones Web grandes, este esfuerzo debe ser recompensado por los numerosos beneficios de utilizar un patrón de diseño MVC, tales como:

- Aplica la modularidad y la partición de aplicación.
- Aumenta la creación de roles específicos en el desarrollo.
- Aumenta la capacidad de gestión de código.
- Aumento de la extensibilidad del código (Capacidad de adaptación a cambios).

# ESTRUCTURA DE ARCHIVOS

```jsx
/ProyectosPHP/
    ├── /app/
    │    ├── /ajax/
    │    │    └── buscadorAjax.php
	  │    │    └── usuarioAjax.php  
    │    ├── /controllers/
    │    │    └── loginController.php
	  │    │    └── searchController.php 
	  │    │    └── userController.php
	  │    │    └── viewsController.php   
    │    ├── /models/
    │    │    └── mainModel.php
    │    │    └── viewsModel.php
    │    ├── /views/
    │    │    └── /content/
    │    ├──  ├──    └── 404-view.php
    │    ├──  ├──    └── dashboard-view.php
    │    ├──  ├──    └── login-view.php
    │    ├──  ├──    └── logOut-view.php
    │    ├──  ├──    └── userList-view.php
    │    ├──  ├──    └── userNew-view.php
	  │    ├──  ├──    └── userSearch-view.php
	  │    ├──  ├──    └── userUpdate-view.php
    │    │    └── /css/
    │    ├──  ├──    └── bulma.min.php
    │    ├──  ├──    └── estilos.css
    │    ├──  ├──    └── sweetalert.min.css
    │    │    └── /fotos/
    │    ├──  ├──    └── default.php
    │    │    └── /img/
    │    ├──  ├──    └── cgs.png
    │    │    └── /inc/
    │    ├──  ├──    └── btn_back.php
    │    ├──  ├──    └── error_alert.php
    │    ├──  ├──    └── head.php
    │    ├──  ├──    └── navbar.php
	  │    ├──  ├──    └── script.php
	  │    ├──  ├──    └── session_start.php
    │    │    └── /js/
    │    ├──  ├──    └── ajax.js
    │    ├──  ├──    └── main.js
	  │    ├──  ├──    └── sweetalert2.all.min.js
    ├── /config/
    │    ├── /app.php/
    │    ├── /server.php/
    ├── /DB/
    │    ├── /db.sql/
    ├── .htaccess
    ├── autoload.php
    ├── index.php
    ├── LICENSE
    ├── README.md
    └── composer.json

```

.HTACCESS 

Este código nos facilita la interacción con las rutas 

```jsx
RewriteEngine On
Options All -Indexes
RewriteRule ^([a-zA-Z0-9/ñÑ-]+)$ index.php?views=$1  // 
```

CREAR BASES DE DATO EN MYSQL

```jsx

CREATE TABLE `usuario` (
  `usuario_id` int(10) NOT NULL,
  `usuario_nombre` varchar(70) COLLATE utf8_spanish2_ci NOT NULL,
  `usuario_apellido` varchar(70) COLLATE utf8_spanish2_ci NOT NULL,
  `usuario_email` varchar(100) COLLATE utf8_spanish2_ci NOT NULL,
  `usuario_usuario` varchar(30) COLLATE utf8_spanish2_ci NOT NULL,
  `usuario_clave` varchar(200) COLLATE utf8_spanish2_ci NOT NULL,
  `usuario_foto` varchar(535) COLLATE utf8_spanish2_ci NOT NULL,
  `usuario_creado` timestamp NOT NULL,
  `usuario_actualizado` timestamp NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_spanish2_ci;

--
-- Volcado de datos para la tabla `usuario`
--

INSERT INTO `usuario` (`usuario_id`, `usuario_nombre`, `usuario_apellido`, `usuario_email`, `usuario_usuario`, `usuario_clave`, `usuario_foto`, `usuario_creado`, `usuario_actualizado`) VALUES
(1, 'Maximo', 'Perea', 'mmaximo@gmail.com', 'Administrador', '$2y$10$F0J8k.lFjgGAK6I/tcbhyuMKSaitXy8ENMSBVZWErIoA6.VSU8MQy', '', '2023-07-06 21:48:05', '2023-07-06 21:48:05');

--
-- Índices para tablas volcadas
--

--
-- Indices de la tabla `usuario`
--
ALTER TABLE `usuario`
  ADD PRIMARY KEY (`usuario_id`);

--
-- AUTO_INCREMENT de las tablas volcadas
--

--
-- AUTO_INCREMENT de la tabla `usuario`
--
ALTER TABLE `usuario`
  MODIFY `usuario_id` int(10) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=2;
COMMIT;
```

CONECTORES BASE DE DATOS

ZONA HORARIA 

```jsx
// APP.PHP
<?php

const APP_URL="http://localhost/CRUD-Dasboard/";
const APP_NAME="CRUD CGS MVC POO";
const APP_SECCIOM_NAME="CGS";

date_default_timezone_set("America/Bogota") // stablecemos la zona horaria de nuestra ciudad
```

SERVER.PHP 

```jsx
//SERVER.PHP
<?php

// Establecemos la conexion a nuestra base de datos
const DB_SERVER="localhost";
const DB_NAME="crud";
const DB_USER="root";
const DB_PASS="";

```

AUTOLOAD