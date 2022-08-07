Metricas 
1- Etramos a Monitor
2- Seleccionamos Metricas
donde primero es necesario indicar el ámbito(donde aplicaremos el monitoreo o una directiva)
3- Selecionar las metricas

Alertas 
Un aviso por correo o msn que algo esta fallando o algo esta fuera de los limites de Azure.
(imagen 5 y 6)
Seleccionamos el ámbito
(img 7)
Indicamos la condición. Seleccionamos cuando se active una regla nos mande una alerta.
Para ello nos solicita la configuración (período del grafico, el estado donde lo queremos, que el evento sea activiado por cualquier usaurio o especificar).
(imagen 11)
Configuramos las acciones que requerimos. Clic en acciones y en seleccionamos en crear un grupo de acciones.
(imagen 12)
Agregamos los datos básicos
(imagen 13)
Nos dirigimos a Notificaciones y agregamos que la alerta llegue mediante correo electonico.
(imagen 14)
Agregamos un nombre de la notificación
(imagen 15)
Seleccionamos en el menu acciones, en donde podemos indicarles por ejemplo que nos mande una logic app (un flujo de trabajo).
(imagen 16)
Lo dejaremos en blanco y daremos en revisar y crear.
(imagen 17)


Monitor permite conectar log Analytics 
En una nueva ventana, buscamos log Analytics, lo que permite mandarle varios registros al Azure Monitor.
Creamos un recursos de log Analytics 
(imagen 19, 20)
Terminando de crear el recuerso, lo seleccionamos.
(imagen 21)
Seleccionamos Configuración de agentes en la barra de la izquierda, para conectar una aplicación y ver todos los errores de dicha aplicación.
(imagen 22)



Monitor también se conecta con Microsoft Defender for Cloud.
Es un centro de seguridad que contiene un antivirus. SIEM, administra los eventos que pasan, para crear un flujo de trabajo.
(imagen 23)
Nos da 3 cosas.
Seguridad general. cuanto recueross tenemos y que ataques
cumplimiento directivo, gobernanza. Donde se peuden crear directivas (reglas).
Protecciones de carga de trabajo. Diferentes suscripcopnes o grupos las fallas de seguridad cuando los usuarios usan los servicios.
El servicio Just-in-time es de paga, y permite limitar tiempo para una actividad especifica.






