author: ricochet
title: NODEJS, EXPRESS, MONGODB
subtitle: IES Virgen del Carmen (Jaén)
lang: en
cover: images/imagen.png
theme: ribbon

## NODEJS, EXPRESS, MONGODB


 - **NodeJS:** Es una plataforma o entorno de ejecución para desarrollar con Javascript del lado del servidor. Está diseñado para generar aplicaciones web de forma altamente optimizada.
 - **ExpressJS:**  Es un framework sobre NodeJS que nos permite trabajar con el protocolo HTTP y tener sistemas de rutas.
 - **MongoDB:**  Es una base de datos NoSQL que nos permite trabajar con documentos json binarios (bson), en lugar de utilizar el sistema clásico de tablas y relaciones, lo que hace que se muy veloz. Tiene colecciones de documentos y estos documentos son objetos json (bson) y los datos se almacenan de manera binaria para aumentar le rendimiento.

## Creación de la base de la app

    mkdir ~/app
    sudo npm install express -g
    sudo npm i -g express-generator
    sudo express (Creará el esqueleto de la app)

## Mongoose - Biblioteca de JavaScript
Usaremos Mongoose para:

 - Enlazar MongoDB y Nodejs
 - Definir modelos de datos 

![configuración mongoose](https://lh3.googleusercontent.com/SNqzWBz-IatMPQoWFXs9BtxLugOYWXDXpWEyRLAJh38lOexLSc0J1icCF2FZ0WKWwtaotM8af9mj "Config")

## Jade - Motor de plantillas
### layout.jade

![enter image description here](https://lh3.googleusercontent.com/idDFrSXZRiY2HZjMo-VAV9t5mObO7cuvAF42JmtdKW9YGbF6dVPzZL6ElcmeYsiXQD6fIFHluM5o "Bootstrap")

### index.jade
![Creación de la pizzapp](https://lh3.googleusercontent.com/5tok6kDaZW4V6w3f203Kfox--4P7KY7skOt4bEF4903746v0eYnAzG1gnF0279FelHKdTs53Yu-O)

### menu.jade
![enter image description here](https://lh3.googleusercontent.com/04dEeGGVZlC4IYBSdM1WEHDsuI67_Owz7w5Pk2pxYsoeg2rPvwHBkW3Fp71z1P0hmHg2LhzOLjbW)

![enter image description here](https://lh3.googleusercontent.com/Qs24Zb9elh5Pcic7YFTGzGDk6ykyGHuwjxhVdRgOfroVYsWOmd7czbmkW7-0mrYR5zUsiZzMD-1l)

### login.jade
![enter image description here](https://lh3.googleusercontent.com/1N9vMtFtdkdr5BIhGA-scR7rbk_snKKtklgeMKj6oCFiUz0OM_TRUwoqQydkguAQZnd7Z0GwSnLb)

## Autenticación - Passport
Para la autenticación usaremos Passport, un middleware de Node que gestiona la autenticación de usuarios.

![enter image description here](https://lh3.googleusercontent.com/fT4IQB-eJ3Scleuekg0Hv0_urStmXB1c_rLi8gEg9Rmy0J2Sa6HHhqc1x2b3fsXgWMLIwkJ-lwP4)

### En app.js

 1. Creamos la sesión (express-session)
 2. Iniciamos passport
 3. Enlazamos la sesión al usuario  concreto

![enter image description here](https://lh3.googleusercontent.com/tPuyMlWbqiV0g6V2jdFeByIoNoSygKupR_i4QL32_LSYxU1RBFhjjZ3_2zzqPBXY-RaE5ztui6_N)

### user.model.js
Creamos el modelo del usuario (mongoose)

![enter image description here](https://lh3.googleusercontent.com/iG1DdvYPSaBlgUFI8Gj1u336r1ujzWT7AdP-aeecpQQtB5ywk_OLC4oTKWZGIV83i8YukM7SRgbw)


![enter image description here](https://lh3.googleusercontent.com/rWWZ3bwlD6hfEVFP_Nlmk_G3_W2M9_sUhbGkJ7A6Z2obgvqBJmUZ4K3qLhixBWhBpQisJfPbZ38n)

Una vez se envíe el formulario de inicio de sesión se 

![enter image description here](https://lh3.googleusercontent.com/q8WlZFVJgcC5vXJMs60sUHmopA-J6vAinh1CgH5wtFXchlnaXdqGVjzRDFosYDq-rh8C1fcKZG0p)

En caso de que las credenciales sean correctas el usuario iniciará sesión

![enter image description here](https://lh3.googleusercontent.com/1WFWXmr7vz-MHvgIPzaI8r2T1oDo_M_R70qy6oWBov9WObY7KP5b_L568Y8VfQgxafo3g2G_m82D)

Si por el contrario falla la autenticación se producirá una redirección a la la ruta **/user/login**

![enter image description here](https://lh3.googleusercontent.com/ryrnmfO36m0dGzIqfiEnB6TMtiyepjahUzh9xeEoaC-tqwd6bJNs8xQzw2ow3SSMZe--b1uNUXGg)


![enter image description here](https://lh3.googleusercontent.com/JseEZQBkXwv3nVh8aOQQo8mDai7pwG69iy_tzadpQFzvLpEh3Z6Xjfk28LEX1fua_U1Hw4hix-RM)

### register.jade

![enter image description here](https://lh3.googleusercontent.com/8vHKF_uomoWUfjPlOHsfnDMQ1Rd9Ws2_sYtr0fF1I5FkFsLcCAWFTl6TLxfUKiWcEygEmp-c9mYY)

![enter image description here](https://lh3.googleusercontent.com/NeMbvODpTc0a98REbLPKMKKH9aT4q7dnyMlzgIRFYx1ub-mYoHSSiyodMnomimH0mKgw1haUm3b2)

![enter image description here](https://lh3.googleusercontent.com/IYwHVAt7s711cTSJFPx1i9TKtPirkml4URxeuLszvoETyZChzMILYtDgmcEbIeT8atW4KHO4vdXo)

Ahora en nuestra base de  datos **pizzapp** se habrá creado el usuario recién creado.

### order.model.js

Definimos el modelo de los pedidos

![enter image description here](https://lh3.googleusercontent.com/CChxv-waYNBvXp2kQtL75-8tyukoYaE4urPIE9RMHoykz3C6X5Fy2sOihbFSBj_UfIe1A5_2bMIN)

### order.jade

![enter image description here](https://lh3.googleusercontent.com/g6rbD0TYh7FsmesTiEItV5E8WPodQHMitFk6z6vNaPHwfIewUtWa1-TaWm2yE5x_HoBoymbHwdgX)


![enter image description here](https://lh3.googleusercontent.com/8RlipmSMnox7mHWzyWQlEmSp_6crx-9tjLe6v7q8fFLwL-f7560QyjWR2tRlmVsH3IqjpJ2hRS29)

Cuando se realice el pedido será impreso:

![enter image description here](https://lh3.googleusercontent.com/_KBKRw_xd5pofTcR9XYfgH_8dt3vTtkkLTZooonT3pmFoFsvVoJHNUUxQU2HP6Fp7jXQE8FIIYZe)


## Nodemailer - Envío de correo
Nodemailer nos ofrecerá los métodos necesarios para poder habilitar el envío de correo automático, en este caso elegimos **Gmail** que viene implementada por defecto.

![enter image description here](https://lh3.googleusercontent.com/ejC9-L0iry4Z_V_4xVTa0SjJ4B1-tv5YhiBPSFi3nDunJzGVpmLJuW7n5eHvLFaWtOtMt0rcs7kw)

Configuramos el correo automático

![enter image description here](https://lh3.googleusercontent.com/-Nn3h9IA3PaMk87e1pw_vutH8GiVmiDG4qitXrO4G8nVNv_1p4J_QxBVCgN255en-LbnUOdz-dm2)

Con el siguiente código se enviará un correo automáticamente al correo de aquellos clientes que hayan realizado un pedido y dicho pedido esté listo **(ready)**

![enter image description here](https://lh3.googleusercontent.com/GxIVdta7TG9UM5AJ6c9LVrYhJGvUkyDUrur57POetP7xkgRd-PnvyMXKkj0xPkQRK2laGXkQ32uj)

Una vez el administrador modifica el estado del pedido a **ready** nodemailer enviará automáticamente el correo al cliente.

![enter image description here](https://lh3.googleusercontent.com/VPmNt3vWf6bRz_m_kCSkzlgzDjvQgSrcaVmvAhqZhox7_60vNe8wKiQuC6E6lDtMMPTn9JkjUic1)

## Problemas durante el curso

### Problema con la conexión a la BD
Este problema lo detectamos la primera vez que forzamos la conexión de Node con Mongo haciendo un login con un usuario, cuando establecíamos el middleware de la librería passport para la autenticación de usuarios.

![enter image description here](https://lh3.googleusercontent.com/bUDMAfaYZyCb46ZqiblCxAitRB5i4-EgkJBQdP0CoMQgYaUEVZoqdiErQHq0UizBFPLJMbZPY_of)




El fallo estaba en el archivo de configuración de Mongo donde se establece la ruta donde se almacenan las bases de datos.

![enter image description here](https://lh3.googleusercontent.com/QBMmEj5WqGuTaLMPa6TJ1kS4ZMvmKtVpkAszAiLHsX6mklvmtJV518DqINWuERM3MPJwfWjSnP7g)


### Problema con la variable Booleana

Para solucionar este problema cambiamos el tipo de dato.

![enter image description here](https://lh3.googleusercontent.com/NML32NGkuSR_im0MjFAnjiGU3keMEB7xJLyE7RXryn03Gmum-H27TV2RC9TCBB5aID7AKsfEHmJv)


#### Referencia:https://stackoverflow.com/questions/52409199/cast-to-boolean-failed-for-value-on-path-sell

Esto supuso tener que modificar ciertas partes de los ficheros para que todo funcionase como debería

![enter image description here](https://lh3.googleusercontent.com/njtlHNMcOXjhcY1odml5o4_JiBSFFGbuAc-nr3kDcFPwFrQESvb6sYKB8pbrGJYtv8OOh0uHqNIE)

![enter image description here](https://lh3.googleusercontent.com/MfNYF0webPTRdcj75H_n9bAxCPiSKhgLdAE8gEMzoMdjFx-_XqvV2O93wfyLrasfz1zEBnLB1VNC)




