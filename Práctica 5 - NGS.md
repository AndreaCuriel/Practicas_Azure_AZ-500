#Crear un grupo de seguridad de red (NGS)

## Craer una Maquina virtyal
- Selecionar crear una nueva maquina virtual 
- Crear un grupo de recursos 'secure-network'. nombre 'myVM1', selecionamos la región y seleccionamos Windows Server 2019 Datacenter - Gen2, Agregamos un nombre de usuario y password y piuerto de entrada RDP.
- Ir al apartado de redes, en grupos de seguridad de NIC, seleccionamos 'Ninguno' y en el apartado de administración, deshabilitaremos los diagnosticos de arranque.
- Revisar y Crear la maquina virtual.

## Crear grupo de seguridad de red.
- En el buscador, escribir Grupo de seguridad de red y selecionar.
- Seleccionar crear un grupo de seguridad de red.
- En datos básicos, seleccionamos el mismo grupo de recursos que la MV anterior y nombremos el grupo de seguridad de red como 'mySecurityGroup' y elegimos la misma región.
- Clic en revisar y crear.
- Entramos al recurso cuando se haya terminado de crear.
- Seleccionamos de la barra izquierda la opcion de Interfeces de red.
- Selecionamos en Asociar, donde seleccionameremos la interfaz de red de la maquina virtual que se creo, puedes identificarle yendo al grupo de recursos y en el listado esta la interfaz de red correspondiente a la MV.
- Cada Maquina Virtual solo puede tener un grupo de seguridad de red.
- Ya que esta la interfaz de red asociada, regresamos al recurso de la mAquina Virtual.
- Vamos a conectar, con la opcion RDP, vamos a ver que tenemos una red publica, pero al intentar conectarnos, no se podra, ya que no hemos agregado ninguna regla en nuestro grupo de seguridad de red.
- Regresamos al grupo de seguridad de red que creamos y en la barra izquierda seleccionamos 'Reglas de seguridad de entrada'.
- Clic en Agregar, para ingresar las reglas.
- En origin puede ser por Any,  Ip, service tag (tipo de servicio, puedes elegir por region un recurso especifico de azure por entrada, internet, vpn, etc) y Application security group (ASG).
- Seleccionaremos 'Any', en puertos ' * ' y en destino (a donde va direccionar) 'Any' y en servicio çustom', puerto 3389 y seleccionamos Protocolo 'TCP', priorifaf '300', acción 'Permitir', Nombre 'PermitirRDP' y le damos clic en guardar.
- Esperar a que se implemente para poder regresar a la maquina virtual y conectarnos por RDP. Logrando conectarnos.
- Regresamos al Grupo de seguridad de red creado para configurar reglas de seguridad de salida.
- En la barra de la izquierda seleccionamos Reglas de seguridad de salida. Servira para indicar que quiero que pueda salir de los recursos que tenemos, en este caso la Maquina virtual.
- Seleccionamos 'Agregar' para hacer la regla de seguridad de salida.
- Vamos a seleccionar en Origen 'Any', en intervalo de puertos de origen ' * ', en Destigo 'Service tag', etiqueta de servicio de destino 'Internet', Servicio 'Custum', Intervalo de puertos de destino ' * '(ningun puerto va poder sacar ningun servicio de internet), protocolo 'TCP', seleccionamos en acción 'Denegar' y en nombre 'NoInternetHastaQueTerminesLaTarea', seleecionamos agregar para guardar los cambios
- Regresamos a la maquina para conectarnos, intentamos entrar al navegador y no nos va intentar usar internet.


