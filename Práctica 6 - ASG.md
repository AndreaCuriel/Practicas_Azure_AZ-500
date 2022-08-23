# Grupo de Seguridad de Aplicación (AGS)

- Buscar Grupo de seguridad de aplicación en portal.azure.com
- Seleccionar crear.
- En Datos Básicos, selecionamos el grupo  'secure-networj' donde tenemos una MV y NGS de la practica 5, nombre ASG, misma región de los dos recursos mencionados y dar en revisar y crear.
- Vamos al recurso de la Maquina Virtual 'myVM1' y seleccionamos 'Redes' en la barra de la izquierda.
- Seleccionamos Grupo de seguridad de aplicación y depsues en Configurar grupos de seguridad de aplicación y seleccionamos el que acabamos de crear y guardar.
- Agregando la MV al ASG, podemos agregarle una directiva desde el grupo.
- Vamos al buscador y escribimos 'Directiva'.
- Selecionar 'Asignaciones' en la barra de la izquierda y selecionamos asignar directiva.
- En aspectos básicos, ambito selecionamos el grupo de recurso 'secure-network' y en exclusiones seleccionamos nuestro ASG 'ASG123'. A si puedo expluir los recursos que esten dentro de ese grupo o agregarlas a la directiva.
- Dentro del recursos de la MV, en redes, ahora puedes ver los cambios en Reglas de puerto de entrada.
- Teniendo ya este grupo de seguridad de aplicación en la maquina Virtual. Si agrego otra maquina vietual con el mismo grupo de seguridad, todo lo que se modifique en la 'myVM1' se va replicar en las demas maquinas virtuales.
