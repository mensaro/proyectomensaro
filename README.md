#   Proyectomensaro

<h1>ZABBIX<h1>
  <h4>Instalamos Zabbix<h4>
  
![installzabiix](https://user-images.githubusercontent.com/104897417/169695972-7b14894a-b8d1-4076-a1cb-3bc172710b99.png)
-Instalamos el paquete descargado antes:

sudo dpkg -i zabbix-release_4.2-1+bionic_all.deb

-Instalamos otros paquetes necesarios para el servidor Zabbix:

sudo apt install -y zabbix-server-mysql zabbix-frontend-php zabbix-agent

 -Conectamos al servidor de bases de datos:
![CONECTAR_UROOT](https://user-images.githubusercontent.com/104897417/169697729-9a102a11-6dec-4875-873e-529d8d528441.png)

-Creamos la base de datos:
 ![Creamos la base de datos](https://user-images.githubusercontent.com/104897417/169697928-41e38357-ec06-4c11-96b5-3122a1754024.png)

    
-Creamos al usuario zabbix con contraseña password y le damos todos los privilegios sobre la base de datos zabbix:
 ![Creamos al usuario zabbix](https://user-images.githubusercontent.com/104897417/169697952-bda35e4c-1231-4292-9921-1fa47154b58f.png)

-Importamos el esquema inicial y los datos, utilizando la contraseña antes creada:
 ![Importamos el esquema inicial](https://user-images.githubusercontent.com/104897417/169698083-78cb3930-6059-4f34-855d-fd08764ce1af.png)
 
-Editamos el fichero /etc/zabbix/zabbix_server.conf y modificamos las siguientes propiedades:
 ![Editamos el fichero zabbix](https://user-images.githubusercontent.com/104897417/169699113-ba43d70c-0d02-4a29-bc13-c6b276fb97fc.png)

-Editamos el fichero /etc/zabbix/apache.conf para especificar nuestra zona horaria:
 ![zona horaria](https://user-images.githubusercontent.com/104897417/169699208-dc6c15e4-b1e8-4d92-98c6-295b940fe593.png)

Reiniciamos el servidor y el agente Zabbix, y el servidor web Apache:
sudo systemctl restart zabbix-server zabbix-agent apache2
    
Configuramos los servicios Zabbix para que se inicie automáticamente en el arranque:
sudo systemctl enable zabbix-server zabbix-agent apache2
    
Ya estaría completado el proceso de instalación, ahora podemos acceder a la interfaz de Zabbix para administrarlo accediendo a la siguiente dirección http://localhost/zabbix en el navegador
La configuración va a comprobar los requisitos:
![requisito](https://user-images.githubusercontent.com/104897417/169699574-dd26b1be-f172-41cc-881c-c49230715ab1.png)
    
Ponemos el nombre de la base de datos, el usuario y la contraseña:
![inicio_sesión](https://user-images.githubusercontent.com/104897417/169700031-9c89c0d4-5cac-4302-b83c-977e6b7e1fbf.png)

Finalmente se nos ha instalado correctamente:
![zabbix_instalado](https://user-images.githubusercontent.com/104897417/169700280-fe3d23b3-e52c-4111-bb50-6cce1b75e9d8.png)
    
 -Instalación del agente
 
    Cuando lo descarguemos de a página web, en la instalación solo tenemos que poner la ip del servidor
  ![zabbix_agent](https://user-images.githubusercontent.com/104897417/170215308-0e9db478-f6aa-44d9-a2fa-d148ae13a504.png)
    
   Ahora para que el servidor pueda hacer ping al cliente debemos quitar el firewall al cliente
    ![quitamos el firewall](https://user-images.githubusercontent.com/104897417/170217028-209dbcca-cbf1-439b-8645-0e5ba6f52979.png)

   Monitorizar un equipo 
    
Entramos en la interfaz web de administración de Zabbix, vamos al apartado "Configuration" y, dentro de éste, entramos en el apartado "Host".

 Pulsamos en "create host" y empezamos a configurar el host. Ponemos un nombre en este caso "windows-pc" y en el apartado grupos añadimos todos los      grupos y finalmente lde damos a add en el apartado de aggent interfaces y ponemos la ip del cliente
    
   ![create_host](https://user-images.githubusercontent.com/104897417/170222843-0446080e-5423-451e-a2a9-732651568c70.png)
    
 Entramos en el host que acabamos de crear y nos vamos a la pestaña de "Templates", buscamos el template "Windows OS", le damos a "add" y después a "update".

 ![template](https://user-images.githubusercontent.com/104897417/170223697-5f8f11c5-361c-47e7-87e8-1bbefc6bfa71.png)
    
    
    
Nos vamos a "Monitoring", y dentro de este pulsamos en Graphs, en "Host" seleccionamos windows-pc y En "Graph" tenemos dos opciones disponibles una para monitorizar la CPU (CPU Load) y otra para monitorizar la memoria (Memory usage)
![graphs](https://user-images.githubusercontent.com/104897417/170230841-b53f4397-71cd-4a76-b7a7-15e1efaacbed.png)

 Memoria
 ![memoria](https://user-images.githubusercontent.com/104897417/170237606-fab2d47e-272f-40f8-92b1-653b10c1cd25.png)
    
 CPU
 ![CPU](https://user-images.githubusercontent.com/104897417/170238234-5b2ecd3e-0896-450f-9d2a-af8e29d71966.png)

 Disco
   
 ![DISCO](https://user-images.githubusercontent.com/104897417/170238087-85f6a4af-b26f-485f-bd13-ac48969afdb0.png)
   
    



 
