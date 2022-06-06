## Monitorizar un sitio web con Zabbix

Añadir un escenario. Vamos a Configuración → Hosts , elegimos un host y hacemos clic en Web. Luego hacemos clic en "Crear Escenario Web".

![web](https://user-images.githubusercontent.com/104897417/170241752-d962b8b0-c3fb-4f84-9745-e675654ca594.png)

2º Definir los pasos para el escenario.

![first](https://user-images.githubusercontent.com/104897417/170443586-0f27a1fd-28e7-495f-9956-d90d637521ba.png)

Continuamos iniciando sesión en la interfaz de Zabbix, y lo hacemos reutilizando las macros (variables) que definimos en el nivel de escenario: {usuario} y {contraseña}

 ![login_](https://user-images.githubusercontent.com/104897417/170444416-3c99ad52-19d1-4083-bb18-63df2f3341db.png)

5º Al iniciar sesión, debemos verificar el hecho. Para hacerlo, verificamos una cadena que solo sea visible cuando inicie sesión, por ejemplo, Administración.

![login_check](https://user-images.githubusercontent.com/104897417/170444518-a711e4b7-8453-414c-8786-fb0ffe87cc64.png)

Ahora que hemos verificado que se puede acceder a la interfaz y que podemos iniciar sesión y recuperar el contenido registrado, también debemos cerrar sesión; de lo contrario, la base de datos de Zabbix se contaminará con muchos registros de sesiones abiertas

![logout](https://user-images.githubusercontent.com/104897417/170444794-3040aeb4-1301-46ff-9ed7-06914a5d0582.png)

También podemos verificar que hemos cerrado sesión buscando la cadena de nombre de usuario.

 ![logout](https://user-images.githubusercontent.com/104897417/170444762-2885772a-3e38-4bcc-bf3d-75a347929c88.png))

 Filnamente vamos a monitorizar y después a web. Vemos que ha funcioinado

 ![logoutch](https://user-images.githubusercontent.com/104897417/170444931-4603038d-9b0e-4be3-b135-6d72baca6d51.png)

