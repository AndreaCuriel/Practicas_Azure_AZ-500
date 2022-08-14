## aleterta en Monitor
- Crear - Regla de alerta (Imagen 1)
- Nos pedira seleccionar un recuerso 
- filtramos nuestro recuerso, para seleccionar la MV que ya tenemos. (imagen2) - clic en listo (imagen 3)
- Continuamos con agregar la condición de la regla, seleccionando que queremos que sea una metrica y nos muestre el porcentaje de CPU (imagen 4)
- Al selecionar la metrica que deseamos, nos mostrara la configuracion de la lógica de la senal (imagen5)
- En esta ventana se podra observar una grafica donde exponen el porcentaje de uso de CPU y en la parte de abajo podemos escoger los parametros que indicaran que la alerta se realice.
- Configuraremos que si sobrepasa el 30% mande una alerta (imagen6)
- clic en listo y nos regresa a la ventana principal de cración de la regla de alertas, mostrando la condicón configurada. (7)
- Siguiente paso es general la acción cuando se active la alerta, para ello seleccionamos crear un grupo de acciones. (8)
- Seleccionamos el grupo de recurso donde deseamos que se guarde, en este caso seleecione el mismo grupo donde cree la MV. En nombre del grupo de acciones, se nombro "Todas las operaciones administrativas"y en Nombre para mostrar es "allops". (9)
- Terminando el llenado de datos b;asicos, seleccionamos el menu Notificación, para configurar como seremos notificados. El cual será mediante correo electronico. Tambien se peude notificar mediante sms y otras opciones (10)
- despues de seleecionar el medio, es necesario agregar un Nombre a la notificacion ("Mail notification") (11)
- Clic en "revisar y crear" y finalizamos con clic en "Crear".
- Nos mostrara en la ventana principal de crear una regla de alertas la acción que configuramos. (12)
- Siguiente paso es configurar los detalles, donde podemos seleccionar que tipo de gravedad nos indicara dicha alerta.(13)
- Lo dejaremos como informativo, agregaremos el nombre de la alerta y descripción. (14)
- ir a la pestana de  revisar y crear; y clic en crear. (15)
- Se tardara un poco en mandar la primera alerta. (16)


## Log Analytics

- Entramos a Áreas de trabajo de log analytics.(17)
- Damos clic en crear (18)
- En datos básicos, seleccionamos el mismo grupo de recurso de nuesta VM, le damos un nombre y seleccionamos la región que queramos. (19)
- Revisar y crear, esperar unos segundo y despues dar clic en Ir al recurso.
- Seleccionar Configuración de agentes, donde seleccionaremos nuestro agente. (20)
- Agregaremos un agente de eventos de Windows, ya que la VM tiene windows, el agente sera DNS Server cuando exista un Error, Advertencia o Información lo va registrar.(21)
- clic en aplicar
- Tambien se pueden hacer nuestros propios registros en "Registros personalizados" opción en la barra izquierda.
- Nos iremos a información general para setear el log Analytics que hemos creado. Seguri los pasos de Conectar un origen de datos. (22)
- Clic en Maquinas Virtuales de Azure (VM) 
- Seleccionamos la MV (23)
- Clic en conectar (24), verificando que MV este iniciada.
- Tardara un poco en conectarse.
- Podemos ver los logs en la opcion Resumen del área de trabajo en nuestro recurso de log Analytics ("logA1) (25)
- En la misma barra de opciones, hay una opción de maquinas virtuales, ahi nos mostrara cuáles Maquinas Vituales estan conectadas.
- Seleccionaremos registros en la misma barra del lado izquierdo para ver los eventos.
- Escogemos login y seleeccionamos "Failed login Count". Clic en ejecutar (26)
- Nos muestra un lenguaje llamado kustum que sirve para consultas. si no se logeo, entonces suma un contador dependiendo el recuerso. para saber los intentos de no logeo. (27)
- Entraremos a nuestra maquian virtual mediante RDP.(28)
- Regresamos a nuestro registro que indicamos para detectar intentos fallidos de acceso en el log Analytics y le damos en ejecutar (29)
- 
-  
