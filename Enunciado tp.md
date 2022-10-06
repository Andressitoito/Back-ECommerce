# Trabajo Final 
## React - Ecomercce 
Se desarrollará como practica final un ecommerce simil a [este](adaecommerce.netlify.app), este pondrá en práctica todo lo visto a lo largo de la cursada . Cuenta con una api creada con [strapi](https://strapi.io/),una aplicación hecha con js que nos permite gestionar y configurar una api. Además de usar un servicio en principio gratuito para alojar las diferentes partes de nuestro sistema.

El proyecto deberá de contar con las siguientes vistas:

 - Home: Vista principal
 - Lista de productos: Deberá mostrar los productos y deberá contar con un paginado y con filtros.
 - Detalle del producto: Deberá mostrar la foto del producto y detalle del mismo,ademas de poder agregar este producto al carrito
 -  Checkout: Deberá mostrar el carrito de compras y la opción de comprar los items.Si el usuario no está logeado debe aparecer para poder hacer el login y/o el registro.
 - Error : Deberá mostrar un error si se accede a una url equivoca
 - Mis datos: una vista privada(solo si estamos logeado) donde solo se podrán ver mis compras y mis datos como el email.

Además, el Layout contará con los siguientes componentes:
- Header: Este mostrar un logo o el nombre del ecommerce, las rutas accesibles, el usuario, si no está logedo permita logearse o registrarse. Si lo está que muestre la ruta de mis datos y la opcion de singout. Por último un botón que despliegue el carrito.
- Carrito: es un acceso rápido que permite realizar cualquier acción del carrito, agregar, quitar o eliminar todos los productos.
- Footer: Muestra información de redes

## Endpoints
Para los endpoints contamos con una url base, en nuestro ejemplo será ecommerce.api/api

GET -> /products  -> Retorna todos los productos
GET -> /products/:id  -> Retorna información de un solo producto

POST -> /auth/local -> payload : {email,password} -> Retorna el token jwt para authenticarnos
POST -> /auth/local/register -> payload:{username,email,password} -> Retorna el token jwt  para authenticarnos y registra un nuevo usuario

Endpoints protegidos 
GET -> /orders -> Retorna todas las compras realizadas por el usuario
POST -> /orders -> payload:{
	data: { 
			Item(Items del carrito), 
			users_permissions_users(id del usuario)
			}
	} -> Retorna si la compra se realizó con exitos
Para las rutas protegidas a la consulta hay que agregar en el header la siguiente opción:
  Authorization:  Bearer {TOKEN JWT}

## Librerías 
Se recomienda utilizar la cantidad necesaria y mínima de librería para poder resolver el trabajo práctico. Una lista de las recomendadas

 - De estilos pueden usar chakra ui, bootstrap, marerial ui, styled component, emotion, sass, css ,etc. pero una sola.
 - Sistema de rutas pueden utilizar react router dom o otro
 - Global state pueden utilizar el que mas les guste recoil,zustand,redux,useState,etc
 - Fetching pueden utilizar Axios de ser necesario
 - Formateador de código pueden utilizar eslint/prettier
 - Validación de formulario pueden usar react custom hook o formik.

## Inspiraciones:

 - https://www.merkal.com/
 - https://es.shopify.com/ejemplos
