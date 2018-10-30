---
title: "Lync Server 2013 : Conf. d’une jonction sans déviation du trafic multimédia"
TOCTitle: Configurar un tronco sin omisión de medios
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48274881
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar un tronco sin omisión de medios en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-24_

Si desea configurar un enlace troncal con el desvío de medios deshabilitado, siga estos pasos. Si desea configurar un enlace troncal con el desvío de medios habilitado, consulte [Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

Tal como se describe a continuación, una configuración de tronco agrupa un conjunto de parámetros que se aplican a los troncos asignados a esta configuración de tronco. Una configuración de tronco puede tener ámbito global (se aplica a todos los troncos que no tienen sitios o configuración de grupo más específicos), ámbito de sitio o de grupo. La configuración del tronco de nivel de grupo se utiliza para adaptar una configuración de tronco específica a un único tronco.

## Para configurar un enlace troncal sin desvío de medios

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.

4.  En la página **Configuración del tronco**, utilice uno de los métodos siguientes para configurar un tronco:
    
      - Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración del tronco**.
    
      - Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:
        
          - **Tronco del sitio :** elija el sitio para la configuración de este tronco en **Seleccionar un sitio** y, a continuación, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, el sitio no aparece en **Seleccionar un sitio**. Esta configuración de tronco se aplicará a todos los troncos del sitio.
        
          - **Tronco de grupo de servidores :** elija el nombre del tronco al que se aplica esta configuración de tronco en **Seleccionar un servicio** y haga clic en **aceptar**. Este tronco puede ser el tronco raíz o cualquiera de los troncos adicionales definidos en el Generador de topologías. Tenga en cuenta que si ya se ha creado una configuración de tronco para un tronco específico, el tronco no se mostrará en **Seleccionar un servicio**.
    

    > [!NOTE]
    > Una vez seleccionado el ámbito de la configuración del tronco, no se podrá cambiar.<BR>El campo <STRONG>Nombre</STRONG> está rellenado previamente con el nombre del sitio o servicio asociado a la configuración del tronco y no se puede cambiar.



5.  Seleccione una de las opciones de **Nivel admitido de cifrado** siguientes:
    
      - **Obligatorio :** es preciso utilizar un protocolo de transporte seguro en tiempo real (SRTP) para contribuir a proteger el tráfico entre el servidor de mediación y la puerta de enlace o central de conmutación (PBX).
    
      - **Opcional :** se utilizará el cifrado del SRTP si lo admiten el proveedor de servicios o el fabricante de los equipos.
    
      - **No admitido :** el proveedor de servicios o el fabricante de los equipos no admite el cifrado de SRTP y, por tanto, no se podrá utilizar.

6.  Asegúrese de que esté desactivada la casilla **Habilitar desvío de medios**.

7.  Active la casilla de verificación **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace de red telefónica conmutada \[RTC\] donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios conocido, desactive esta casilla.

8.  Si la entidad del mismo nivel que el tronco admite la recepción de solicitudes SIP REFER del Servidor de mediación, active la casilla **Habilitar envío de referencia a la puerta de enlace**.

9.  (Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure registros de uso de RTC a esta configuración de tronco. Los usos de RTC asociados a esta configuración de tronco se aplicarán a todas las llamadas entrantes que pasen por el tronco y no tengan su origen en un extremo de Lync. Para administrar registros de uso de RTC asociados a una configuración de tronco, utilice uno de los métodos siguientes:
    
      - Para seleccionar uno o más registros en una lista de todos los registros de uso de RTC disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.
    
      - Para quitar un registro de uso de RTC de esta configuración de tronco, seleccione el registro y haga clic en **Quitar**.
    
      - Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco, haga lo siguiente:
        
        1.  Haga clic en **Nuevo**.
        
        2.  En el campo **Nombre**, escriba un nombre descriptivo único para el registro.
            

            > [!NOTE]
            > El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.

        
        3.  Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**.
            
              - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            
              - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. Para obtener más información, consulte [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Haga clic en **Aceptar**.
    
      - Para editar un registro de uso de RTC ya asociado a esta configuración de tronco:
        
        1.  Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.
        
        2.  Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**.
            
              - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            
              - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. Para obtener más información, consulte [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Haga clic en **Aceptar**.
    
    > [!IMPORTANT]  
    > Es importante asociar registros de uso de RTC según el Servidor de mediación del mismo nivel que se asocie al tronco en proceso de configuración. Si el Servidor de mediación del mismo nivel es una puerta de enlace de RTC o un controlador de borde de sesión (SBC), se recomienda encarecidamente que la configuración de tronco no esté asociada a un registro de uso de RTC que se enrute a un destino de RTC o a cualquier otro sistema de bajada conectado a través de Lync Server.
    


10. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, seleccione el registro de uso de RTC y haga clic en las flechas arriba o abajo.
    
    > [!IMPORTANT]  
    > Es importante el orden en el que aparecen en la lista de la configuración de tronco los registros de uso de RTC. Lync Server recorre la lista de arriba abajo.
    


11. **Habilitar cierre de RTP** debe seleccionarse para habilitar el desvío de medios para los clientes que se encuentren detrás de un firewall o NAT y para los SBC que admitan el cierre.

12. Debe seleccionarse **Habilitar reenvío de historial de llamadas** para habilitar el envío de información de historial de llamadas a la puerta de enlace del mismo nivel del Servidor de mediación.

13. **Habilitar el reenvío de datos P-Asserted-Identity** debe seleccionarse para habilitar el reenvío de información de PAI de autor de la llamada entre el Servidor de mediación y la puerta de enlace (y viceversa).

14. Debe seleccionarse **Habilitar temporizador de la conmutación por error de enrutamiento saliente** para que la conmutación por error sea más rápida. La puerta de enlace asociada con este tronco puede notificar en un plazo de 10 segundos que se está procesando una llamada saliente. Si Servidor de mediación no se recibe esta notificación, se producirá el reenrutamiento a otro tronco. En las redes en las que la latencia pueda retrasar el tiempo de respuesta o si la puerta de enlace se demora más de 10 segundos en responder, deberá deshabilitarse la conmutación por error rápida.

15. (Opcional) Asocie y configure las **reglas de conversión de números desde donde se realizó la llamada** para el tronco. Estas reglas de conversión se aplican al número desde donde se realizó la llamada (para las llamadas salientes).
    
      - Para elegir una o más reglas en una lista de reglas de conversión disponible en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    
      - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener información sobre cómo definir una regla nueva, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación referente a la implementación.
    
      - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en **Mostrar detalles**. Para obtener más información, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.
    
      - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en **Pegar**. Para obtener información detallada, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg399038.security(OCS.15).gif" title="security" alt="security" />Seguridad Nota:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas pudieran entrar en conflicto.</td>
    </tr>
    </tbody>
    </table>


16. (Opcional) Asocie y configure **reglas de conversión de números llamados** para el tronco. Estas reglas de conversión se aplican al número llamado en una llamada saliente.
    
      - Para elegir una o más reglas en una lista de reglas de conversión disponible en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    
      - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener información sobre cómo definir una regla nueva, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación referente a la implementación.
    
      - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en **Mostrar detalles**. Para obtener más información, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.
    
      - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en **Pegar**. Para obtener información detallada, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.
    
    > [!CAUTION]  
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas pudieran entrar en conflicto.
    


17. Asegúrese de que las reglas de conversión del tronco se dispongan en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.
    
    > [!IMPORTANT]  
    > Lync Server recorre la lista de reglas de conversión de arriba abajo y utiliza la primera regla que coincide con el número marcado. Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida solamente con números de 11 dígitos que comiencen por +1425, asegúrese de que la regla que coincida con cualquier número de 11 dígitos se haya colocado <em>por debajo</em> de la regla más restrictiva.
    


18. Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.

19. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    

    > [!NOTE]
    > Siempre que cree o modifique una configuración de tronco, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación sobre operaciones.



## Vea también

#### Tareas

[Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  

#### Otros recursos

[Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md)

