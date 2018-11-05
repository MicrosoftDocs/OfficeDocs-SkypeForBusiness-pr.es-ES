---
title: "Lync Server 2013 : Conf. d’une jonction avec la déviation du trafic mult."
TOCTitle: Configurar un tronco con omisión de medios
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48276113
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar un tronco con omisión de medios en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Siga los procedimientos descritos a continuación para configurar un tronco con la desviación de medios activada. Para configurar un tronco con la desviación de medios desactivada, consulte [Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md). La desviación de medios resulta útil cuando se quiere minimizar el número de servidores de mediación implementados. Por lo general, se implementará un grupo de servidores de mediación en un sitio central y controlará las puertas de enlace en los sitios de sucursales. Si se activa la derivación de medios, la red telefónica conmutada (RTC) puede llamar desde los clientes en los sitios de sucursales para pasar directamente por las puertas de enlace de esos sitios. Las rutas de llamadas salientes de Lync Server 2013 y las directivas de Telefonía IP empresarial se han de configurar correctamente para que las llamadas de RTC desde clientes en un sitio de sucursal se enruten a la puerta de enlace correcta.

Se recomienda encarecidamente que habilite el desvío de medios. Ahora bien, antes de hacerlo en un tronco SIP, asegúrese de que su proveedor de troncos SIP cualificado es compatible con el desvío de medios y puede aceptar los requisitos para habilitar correctamente el escenario. Concretamente, el proveedor debe disponer de las direcciones IP de los servidores en la red interna de la organización. Si el proveedor no es compatible con este escenario, el desvío de medios no se efectuará correctamente. Para obtener más información, consulte [Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la documentación sobre planeamiento.


> [!NOTE]
> El desvío de medios no interactuará con todas las puertas de enlace de red telefónica conmutada (RTC), los sistemas IP-PBX y los controladores de borde de sesión (SBC). Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. El desvío de medios solo se admite con los productos y las versiones recogidos en Ingeniería completa para Microsoft Lync, en <A href="http://go.microsoft.com/fwlink/?linkid=214406%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=214406&amp;clcid=0xC0A</A>.



Una configuración de tronco tal como se describe más abajo agrupa un conjunto de parámetros que se aplican a los troncos a los que se ha asignado esta configuración de tronco. Una configuración de tronco concreta puede tener ámbito global (todos los troncos que no tengan una configuración de sitio o grupo de servidores más concreta), de sitio o de grupo de servidores. La configuración de tronco de nivel de grupo de servidores se utiliza para limitar el ámbito de una configuración de tronco concreta a un único tronco.

## Para configurar un tronco con desvío de medios

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco** .

4.  En la página **Configuración del tronco** , utilice uno de los métodos siguientes para configurar un tronco:
    
      - Haga doble clic en un tronco existente (por ejemplo, el tronco **Global** ) para que aparezca el cuadro de diálogo **Editar configuración del tronco** .
    
      - Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:
        
          - **Tronco del sitio :** elija el sitio para esta configuración de tronco en **Seleccionar un sitio** y, a continuación, haga clic en **Aceptar** . Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, este no aparecerá en **Seleccionar un sitio** . Esa configuración de tronco se aplicará a todos los troncos del sitio.
        
          - **Tronco del grupo :** elija el nombre del tronco al que se aplica esta configuración de tronco. Dicho tronco puede ser el tronco raíz o cualquier otro tronco definido en Generador de topologías. En **Seleccionar un servicio** , haga clic en **Aceptar** . Tenga en cuenta que si ya se ha creado una configuración para un tronco específico, dicho tronco no aparecerá en **Seleccionar un servicio** .
    

    > [!NOTE]
    > Una vez seleccionado el ámbito de la configuración del tronco, no se podrá cambiar.<BR>El campo <STRONG>Nombre</STRONG> está rellenado previamente con el nombre del sitio o servicio asociado a la configuración del tronco y no se puede cambiar.



5.  Especifique un valor en **Máximo de diálogos previos compatibles** . Es el número máximo de respuestas bifurcadas que una puerta de enlace de red telefónica conmutada (RTC), un sistema PBX IP o el controlador de borde de sesión (SBC) del proveedor de servicios puede recibir para una invitación (INVITE) enviada al servidor de mediación. El valor predeterminado es 20.
    

    > [!NOTE]
    > Antes de cambiar este valor, póngase en contacto con su proveedor de servicios o fabricante de equipos para obtener información detallada sobre las capacidades de su sistema.



6.  Seleccione una de las opciones de **Nivel admitido de cifrado** siguientes:
    
      - **Obligatorio :** es preciso utilizar un protocolo de transporte seguro en tiempo real (SRTP) para contribuir a proteger el tráfico entre el servidor de mediación y la puerta de enlace o central de conmutación (PBX).
    
      - **Opcional :** se utilizará el cifrado del SRTP si lo admiten el proveedor de servicios o el fabricante de los equipos.
    
      - **No admitido :** el proveedor de servicios o el fabricante de los equipos no admite el cifrado de SRTP y, por tanto, no se podrá utilizar.

7.  Active la casilla **Habilitar desvío de medios** si desea que los medios omitan el servidor de mediación para que sea la entidad del mismo nivel que el tronco la que realice el procesamiento.
    
    > [!IMPORTANT]  
    > Para que el desvío de medios funcione correctamente, es preciso que la puerta de enlace de RTC, el sistema PBX IP o el controlador de borde de sesión del proveedor de servicios sean compatibles con ciertas capacidades. Para obtener más información, consulte <a href="lync-server-2013-planning-for-media-bypass.md">Planificar la omisión de medios en Lync Server 2013</a> en la documentación referente al planeamiento.
    


8.  Active la casilla **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace RTC donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios conocido, desactive esta casilla.

9.  Si la entidad del mismo nivel que el tronco admite la recepción de solicitudes SIP REFER del Servidor de mediación, active la casilla **Habilitar envío de referencia a la puerta de enlace** .
    

    > [!NOTE]
    > Si deshabilita esta opción mientras la opción <STRONG>Habilitar desvío de medios</STRONG> está seleccionada, se requerirá una configuración adicional. Si la entidad del mismo nivel del tronco no es compatible con la recepción de solicitudes SIP REFER del servidor de mediación y se ha habilitado el desvío de medios, es preciso que ejecute el cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> para deshabilitar el RTCP para las llamadas activas y en espera con el fin de admitir las condiciones adecuadas para el desvío de medios. Para obtener más información, consulte la documentación <A href="lync-server-2013-lync-server-management-shell.md">Shell de administración de Lync Server</A>.<BR>También puede seleccionar <STRONG>Habilitar referencia usando control de llamadas de terceros</STRONG> si desea que los medios omitan las llamadas transferidas y la puerta de enlace no admita solicitudes SIP REFER.



10. (Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure registros de uso de RTC a esta configuración de tronco. Los usos de RTC asociados a esta configuración de tronco se aplicarán a todas las llamadas entrantes que pasen por el tronco y no tengan su origen en un extremo de Lync. Para administrar registros de uso de RTC asociados a una configuración de tronco, utilice uno de los métodos siguientes:
    
      - Para seleccionar uno o más registros en una lista de todos los registros de uso de RTC disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar** . Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar** .
    
      - Para quitar un registro de uso de RTC de esta configuración de tronco, seleccione el registro y haga clic en **Quitar** .
    
      - Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco, haga lo siguiente:
        
        1.  Haga clic en **Nuevo** .
        
        2.  En el campo **Nombre** , escriba un nombre descriptivo único para el registro.
            

            > [!NOTE]
            > El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG> .

        
        3.  Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar** . Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar** .
            
              - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar** .
            
              - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo** . Para obtener más información, consulte [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles** . Para obtener más información, consulte [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Haga clic en **Aceptar** .
    
      - Para editar un registro de uso de RTC ya asociado a esta configuración de tronco:
        
        1.  Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles** .
        
        2.  Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar** . Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar** .
            
              - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar** .
            
              - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo** . Para obtener más información, consulte [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles** . Para obtener más información, consulte [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Haga clic en **Aceptar** .
    
    > [!IMPORTANT]  
    > Es importante asociar registros de uso de RTC según el Servidor de mediación del mismo nivel que se asocie al tronco en proceso de configuración. Si el Servidor de mediación del mismo nivel es una puerta de enlace de RTC o un controlador de borde de sesión (SBC), se recomienda encarecidamente que la configuración de tronco no esté asociada a un registro de uso de RTC que se enrute a un destino de RTC o a cualquier otro sistema de bajada conectado a través de Lync Server.
    


11. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, seleccione el registro de uso de RTC y haga clic en las flechas arriba o abajo.
    
    > [!IMPORTANT]  
    > Es importante el orden en el que aparecen en la lista de la configuración de tronco los registros de uso de RTC. Lync Server recorre la lista de arriba abajo.
    


12. Debe seleccionarse **Habilitar cierre de RTP** si se desea habilitar el desvío de medios para clientes situados detrás de una traducción de direcciones de red (NAT) o firewall y un SBC que admita cierre.

13. Debe seleccionarse **Habilitar reenvío de historial de llamadas** para habilitar el envío de información de historial de llamadas a la puerta de enlace del mismo nivel del Servidor de mediación.

14. Debe seleccionarse **Habilitar reenvío de datos de P-Asserted-Identity** para que la información de originadores de llamadas de P-Asserted-Identity (PAI) pueda reenviarse entre el lado de Servidor de mediación y el lado de la puerta de enlace (y viceversa) si está presente.

15. Debe seleccionarse **Habilitar temporizador de la conmutación por error de enrutamiento saliente** para que la conmutación por error sea más rápida. La puerta de enlace asociada con este tronco puede notificar en un plazo de 10 segundos que se está procesando una llamada saliente. Si Servidor de mediación no se recibe esta notificación, se producirá el reenrutamiento a otro tronco. En las redes en las que la latencia pueda retrasar el tiempo de respuesta o si la puerta de enlace se demora más de 10 segundos en responder, deberá deshabilitarse la conmutación por error rápida.

16. (Opcional) Asocie y configure las **reglas de conversión de números desde donde se realizó la llamada** para el tronco. Estas reglas de conversión se aplican al número desde donde se realizó la llamada (para las llamadas salientes).
    
      - Para elegir una o más reglas en una lista de reglas de conversión disponible en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar** . En **Seleccionar reglas de conversión** , haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar** .
    
      - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva** . Para obtener información sobre cómo definir una regla nueva, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación referente a la implementación.
    
      - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en **Mostrar detalles** . Para obtener más información, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.
    
      - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en **Pegar** . Para obtener información detallada, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar** .
    
    > [!WARNING]  
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas pudieran entrar en conflicto.
    


17. (Opcional) Asocie y configure **reglas de conversión de números llamados** para el tronco. Estas reglas de conversión se aplican al número llamado en una llamada saliente.
    
      - Para elegir una o más reglas en una lista de reglas de conversión disponible en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar** . En **Seleccionar reglas de conversión** , haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar** .
    
      - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva** . Para obtener información sobre cómo definir una regla nueva, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación referente a la implementación.
    
      - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en **Mostrar detalles** . Para obtener más información, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.
    
      - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en **Pegar** . Para obtener información detallada, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar** .
    
    > [!WARNING]  
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas pudieran entrar en conflicto.
    


18. Asegúrese de que las reglas de conversión del tronco se dispongan en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.
    
    > [!IMPORTANT]  
    > Lync Server 2013 recorre la lista de reglas de conversión de arriba abajo y utiliza la primera regla que coincide con el número marcado. Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida solamente con números de 11 dígitos que comiencen por +1425, asegúrese de que la regla que coincida con cualquier número de 11 dígitos se haya colocado <em>por debajo</em> de la regla más restrictiva.
    


19. Cuando haya terminado de configurar el tronco, haga clic en **Aceptar** .

20. En la página **Configuración del tronco** , haga clic en **Confirmar** y, a continuación, en **Confirmar todo** .
    

    > [!NOTE]
    > Siempre que cree o modifique una configuración de tronco, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación sobre operaciones.



Una vez que haya configurado el tronco, siga configurando el desvío de medios; para ello, elija entre las opciones globales de desvío de medios, tal como se describe en [Opciones globales de desvío de medios en Lync Server 2013](lync-server-2013-global-media-bypass-options.md) en la documentación referente a la implementación.

## Vea también

#### Tareas

[Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  

#### Conceptos

[Configurar la omisión de medios en Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Opciones globales de desvío de medios en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  

#### Otros recursos

[Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md)

