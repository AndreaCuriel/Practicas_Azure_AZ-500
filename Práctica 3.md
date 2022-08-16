## Microsoft Defender for Cloud 

- En portal azure, en el buscador escribicmos defender y seleccionamos la opción Microsoft defender for Cloud. (1)
- Agregar una 'directiva' para que se conecte con Microsoft Defender for Cloud
- Escribimos en el buscador, Directiva y la seleccionamos. (2) Estas se encuentran en Azure Police. (3)
- Primer paso es definir una directiva, para ello selecionamos 'Definiciones' en la barra de la izquierda y despues en '+ Definición de directiva' para crear neustra propia Directiva (regla). (4)
- Agregamos la suscripción que Azure que corresponde y el nombre con el que queremos nombrarla. (5)
- Podemos modificar la directiva mediante json (6) , es el código que se muestra en Definicion de directiva (todo azure de maneja mediante json) (6)
- Concluimos en dar clic en guardar.
- Asignaciones de las Directivas, seleccionamos 'Asignación'en la barra izquierda. (7)
- Selecionamos asignar directiva.
- Selecionamos un grupo de recursos que excluir y le damos guardar. (8)
- Definiremos la directiva, en este caso, seleccionaremos Ubicaciones permitidas. (9 y 10)
- Continuaremos con la opción de Parametros, donde seleccionaremos las ubicaciones que seran permitidas. (11)
- La directiva interpretara que todos los recuros que esten en la suscripcion únicamente podran ser generados en la ubicacion US, con la excepción del recurso que seleccionamos en excepciones.
- Nos movemos a Mensajes de no cumplimiento, donde escribiremos el texto que aparecera al no cumplirse la directiva. (12)
- Finalizamos con revizar y crear. La directiva tardara entre 5 a 10min para ser aplicada.

Defender y Sentinel trabajan de forma conjunta para proteger la nube.

- Crear una maquina Virtual llamada 'VM1' con windows 10 con puerto de entrada RDP.
- Buscar Microsoft Sentinel (13) 
- Selecionar en Crear. (14)
- 
