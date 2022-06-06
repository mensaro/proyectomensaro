# Proyectomensaro

# Instalamos Zabbix

![installzabiix](https://user-images.githubusercontent.com/104897417/169695972-7b14894a-b8d1-4076-a1cb-3bc172710b99.png)

- Instalamos el paquete descargado antes:

```bash
sudo dpkg -i zabbix-release_4.2-1+bionic_all.deb
```

- Instalamos otros paquetes necesarios para el **servidor Zabbix**:

```bash
sudo apt install -y zabbix-server-mysql zabbix-frontend-php zabbix-agent
```

- Conectamos al servidor de bases de datos:

![CONECTAR_UROOT](https://user-images.githubusercontent.com/104897417/169697729-9a102a11-6dec-4875-873e-529d8d528441.png)

- Creamos la base de datos:

![Creamos la base de datos](https://user-images.githubusercontent.com/104897417/169697928-41e38357-ec06-4c11-96b5-3122a1754024.png)

- Creamos al usuario zabbix con contraseña password y le damos todos los privilegios sobre la base de datos zabbix:

![Creamos al usuario zabbix](https://user-images.githubusercontent.com/104897417/169697952-bda35e4c-1231-4292-9921-1fa47154b58f.png)

- Importamos el esquema inicial y los datos, utilizando la contraseña antes creada:

![Importamos el esquema inicial](https://user-images.githubusercontent.com/104897417/169698083-78cb3930-6059-4f34-855d-fd08764ce1af.png)

- Editamos el fichero /etc/zabbix/zabbix_server.conf y modificamos las siguientes propiedades:

![Editamos el fichero zabbix](https://user-images.githubusercontent.com/104897417/169699113-ba43d70c-0d02-4a29-bc13-c6b276fb97fc.png)

- Editamos el fichero /etc/zabbix/apache.conf para especificar nuestra zona horaria:

![zona horaria](https://user-images.githubusercontent.com/104897417/169699208-dc6c15e4-b1e8-4d92-98c6-295b940fe593.png)

Reiniciamos el servidor y el agente Zabbix, y el servidor web Apache:

```bash
sudo systemctl restart zabbix-server zabbix-agent apache2
```

Configuramos los servicios Zabbix para que se inicie automáticamente en el arranque:
sudo systemctl enable zabbix-server zabbix-agent apache2

Ya estaría completado el proceso de instalación, ahora podemos acceder a la interfaz de Zabbix para administrarlo accediendo a la siguiente dirección http://localhost/zabbix en el navegador
La configuración va a comprobar los requisitos:
![requisito](https://user-images.githubusercontent.com/104897417/169699574-dd26b1be-f172-41cc-881c-c49230715ab1.png)

Ponemos el nombre de la base de datos, el usuario y la contraseña:
![inicio_sesión](https://user-images.githubusercontent.com/104897417/169700031-9c89c0d4-5cac-4302-b83c-977e6b7e1fbf.png)

Finalmente se nos ha instalado correctamente:
![zabbix_instalado](https://user-images.githubusercontent.com/104897417/169700280-fe3d23b3-e52c-4111-bb50-6cce1b75e9d8.png)
