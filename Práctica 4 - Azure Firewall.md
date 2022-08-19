## Configuración de Azure Firewall.

### Primer paso, crear una red virtual. (1,2)
- Seleccionamos direccones IP 
- Asegurarse que la dirección sea 10.0.0.0/16 (3)
- En nombre de la subnet, cambiaremos el nombre por 'AzureFirewallSubnet' y en intervalo de direcciobes de subnet será 10.0.1.0/24 (4)
- Agregar otra subnet llamada 'Workload-SN' y en intervalo de direcciones de subnet será 10.0.2.0/24. (5) 
- El firewall vivira en la subnet 'AzureFirewallSubnet' y la carga de trabajo será en 'Workload-SN' donde se tendran nuestro recursos como las maquinas virtuales. (6)
- Seleccionamos revisar y crear.

### Senfo paso, crear una maquina virtual.
- La maquina virtul se creara en la mismo recurso que la red virtual y en la misma región. Eligiremos en imagen Windows Server 2016 Datacenter. (7)
- Ingresar un usuario y contraseña. En reglas de puerta de entrada, seleccionaremos 'Ninguno'. (8)
- Aceptamos las licencias.
- Seleccionamremos el apartad de redes, revisar que en rede virtual este la que acabos de crear 'TEST-FIREWALL', en subred 'Workload-SN'  y en Ip publica seleccionamos 'Ninguno'. (9)
- Selecionamos el apartado de administración y deshabilitamos el diagnostico de arranque, para disminuir el tiempo de la creación de la maquina virtual (10)
- Seleccionamos revisar y crear.

### Tercer paso, crear Firewall.
- Buscar firewall en portal.azure.com 
- Seleccionar crear.
- Agregar el mismo grupo de recursos, misma región y de nombre, se llamara 'Firewall' (11)
- Seleccionaramos el firewall estandar con las reglas de firewall (clásicas) para administrar firewalll, en red virtual elegir 'usar existente' y seleccionar 'TEST-FIREWALL' (La red que se creo en el paso uno). (12)
- Agregaremos una nueva IP 'fw-Ip'. (13)
- Seleccionar revisar y crear.
- Finalizando el recurso, ingresar y seleccionar la IP privada saber su valor. (14)

### Cuarto paso, Enrutamiento para mandar la información hacia el Firewall, usando Tablas de rutas
- Buscamos Tablas de rutas en el buscador de portal.azure.com. (15)
- Seleccionamos en crear.
- Seleccionamos la mismo grupo de recursos y región. De nombre será firewall-route. (16)
- Clic en revisar y crear.
- La tabla de rutas crea el camino para las conexiones entrantes y salientes del firewall.
- Vamos al recurso y seleccionamos en la barra de la izquierda 'Subredes' y damos clic en Asociar. (17)
- Selecionamos la red que creamos y la subred de carga de trabajo 'Workload-SN' y guardamos .(18) 
- Selecionarmos en la barra izquierda la opción Rutas y agregar. (19)
- Le colocamos el nombre de 'firewall-dg', en destino del profigo de dirección seleccionamos 'Direcciones IP', en intervalo de direcciones de destino y CIDR escribimos 0.0.0.0/0, en tipo del próximo salto 'Dispositivo virtual' y en Dirección del próximo salto escribimos la ip privada de nuestro firewall ya creado. (20)

### Quinto paso, Agregar las reglas del Firewall.
- Ir al recurso ya creado de firewall y seleccionar en la barra izquierda 'Reglas' y selecionamos Recopilación de reglas de aplicación. (21)
- Selecionamos agregar una colección de reglas de aplicación.
- En nombre 'App-Rule1', en prioridad le pondremos 200, menos el numero mayor la prioridad. en acción permitir. En FQDN de destino pondremos como idica en la imagen (en source es la ip de la subnet Workloan-SN) (22) Lo que hara sera permitir el paso a www.google.com
- seleccionamos agregar para finalizar la reglas.
- Ahora agregaremos las reglas de red, seleccionando Agregar una colección de reglas de red.
- Donde permitiremos las redes de DNS, para ello en source agregamos la IP de Workloan-SN, en direcciones de destino las que corresponden al DNS (205.171.3.65, 205.171.2.65) y en puerto de destino 53 y terminamos seleccionando en agregar. (24)
- Finalizando agregaremos la refla de NAT, seleccionando Agregar una colección de reglas NAT.
- Será para le protocolo RDP, prioridad 200. En la regla pondremos como nombre 'rd-nat', protocolo 'TCP', en source un * indicando que todas las ip de origen las vas soportar y en ip de destino vamos a colocar la ip publica de nuestro firewall 'fw-Ip' y en puerto de destino es 3389, en dirección traducida es la ip privada de la maquina virtual (en el recuerso 'srv-Work-nsg' selecionamos opción interfeces de red y ahi mostrara la ip necesaria) y en puerto traducido el mismo 3389. Agregamos (25)

### Sexto paso. Vamos a la interfaz de red 
- Nos vamos a nuestro grupo de recursos y seleccionamos la interfaz de red. (26)
- Seleccionamos Servidores DNS, personalizar y pegamos las dos IP de DNS que agregamos en la regla de red y seleccionamos guardar (27)


### Septimo paso. Probar el Firewall, conectandonos a la maquina virtul.
- Ir a conectarse por RDP a la maquina virtual (28)
- No nos va permitir entrar, porque no es publico, porque no estamos dentro de las ip de DNS. Tenemos que agregar en las reglas de red la ip nuestra IP DNS y tambien agregarla en interfaz de red.
