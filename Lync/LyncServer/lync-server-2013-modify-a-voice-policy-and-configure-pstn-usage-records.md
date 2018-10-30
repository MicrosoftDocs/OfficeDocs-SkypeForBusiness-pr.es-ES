---
title: "Modificar directiva de voz y configurar registros de uso de RTC en Lync Server 2013"
TOCTitle: "Mod. une strat. de voix et conf. des enr. d’util. PSTN dans Lync Server 2013"
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48275616
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificar una directiva de voz y configurar registros de uso de RTC en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Siga los pasos siguientes si desea modificar una directiva de voz. Si desea crear una nueva directiva de voz, consulte [Crear una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) para obtener el procedimiento que debe seguir.


> [!NOTE]
> Si se asigna a un usuario una directiva de voz sin registros de uso de la Red telefónica conmutada (RTC) asociados, el usuario no podrá realizar llamadas salientes. Para ver un listado de todos los registros de uso de la RTC disponibles en su implementación de Telefonía IP empresarial y ver sus propiedades, consulte <A href="lync-server-2013-view-pstn-usage-records.md">Ver registros de uso de la RTC en Lync Server 2013</A>.



## Para modificar una directiva de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, después, en **Directiva de voz**.

4.  En la página **Directiva de voz**, haga doble clic en el nombre de una directiva de voz.
    

    > [!NOTE]
    > El ámbito y el nombre se establecieron cuando se creó la directiva de voz. No pueden modificarse.



5.  (Opcional) En **Editar directiva de voz**, especifique otra información descriptiva sobre la directiva de voz.

6.  Active o desactive las casillas siguientes para habilitar o deshabilitar cada una de las **Características de llamadas**:
    
      - **Desvío de correo de voz** impide que las llamadas se enruten inmediatamente al sistema de correo de voz del teléfono móvil del usuario cuando se ha configurado las llamadas simultáneas y el teléfono está apagado, no tiene batería o está fuera de cobertura.
        

        > [!NOTE]
        > Esta característica solo se puede configurar desde el Shell de administración de Lync Server

    
      - **Desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos cliente. Lync Server 2013 ofrece un amplio abanico de opciones para configurar el desvío de llamadas. Por ejemplo, si una organización no desea que las llamadas entrantes se desvíen externamente a la Red telefónica conmutada (RTC), un administrador puede aplicar una directiva de voz especial para implementar esta restricción. Habilitada de forma predeterminada.
    
      - **Delegación** permite que los usuarios designen a otros usuarios para que envíen y reciban llamadas en su nombre. En Lync Server 2013, un delegado puede configurar las llamadas simultáneas de modo que cuando se realicen llamadas entrantes a su superior suenen los teléfonos de todos los destinatarios definidos en las llamadas simultáneas del delegado. Así pues, el delegado dispone de una mayor flexibilidad para responder a las llamadas dirigidas a su superior. Habilitada de forma predeterminada.
    
      - **Transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Habilitada de forma predeterminada.
    
      - **Estacionamiento de llamadas** permite que los usuarios pongan las llamadas en espera para que se puedan atender desde otro teléfono u otro cliente. Deshabilitada de forma predeterminada.
    
      - **Llamadas simultáneas** permite que las llamadas entrantes suenen en otros teléfonos (por ejemplo, un teléfono móvil) o en otros dispositivos de extremo. Lync Server 2013 ofrece un amplio abanico de opciones para configurar las llamadas simultáneas. Habilitada de forma predeterminada.
    
      - **Llamada de equipo** permite a los usuarios de un equipo definido responder a las llamadas en lugar de otros miembros del equipo. Habilitada de forma predeterminada.
    
      - **Volver a enrutar en RTC** permite que las llamadas realizadas por usuarios que tienen asignada esta directiva a otros usuarios de la empresa se puedan volver a enrutar en la Red telefónica conmutada (RTC) si la red WAN está saturada o no disponible. Habilitada de forma predeterminada.
    
      - **Invalidar directiva de ancho de banda** permite a los administradores invalidar las decisiones de la directiva de control de admisión de llamadas para un usuario determinado. Deshabilitada de forma predeterminada.
        

        > [!NOTE]
        > La directiva se invalidará solo para llamadas entrantes dirigidas a dicho usuario, pero no para las llamadas salientes que realice el usuario. Una vez establecida la sesión, el consumo de ancho de banda se registrará de forma detallada. Este parámetro debe usarse con moderación.

    
      - **Seguimiento de llamadas malintencionadas** permite a los usuarios informar sobre llamadas malintencionadas (como amenazas de bomba) usando la interfaz de usuario del cliente, con lo cual la llamada queda señalada en los registros de detalles de llamadas. Deshabilitada de forma predeterminada.

7.  Para asociar y configurar registros de uso de RTC para esta directiva de voz, siga uno de los procedimientos siguientes:
    
      - Para elegir uno o más registros en una lista de todos los registros de uso de RTC disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de voz y haga clic en **Aceptar**.
    
      - Para quitar el registro de uso de RTC de esta directiva de voz, seleccione el registro y haga clic en **Quitar**.
    
      - Para definir un nuevo registro de uso de RTC y asociarlo con esta directiva de voz, haga lo siguiente:
        
        1.  Haga clic en **Nuevo**.
        
        2.  En el campo **Nombre**, escriba un nombre descriptivo único para el registro. Por ejemplo, puede que desee crear un registro de uso de RTC llamado **Redmond** para los empleados de Redmond a tiempo completo, y otro registro llamado **RedmondTemps** para los empleados temporales.
            

            > [!NOTE]
            > El registro de uso de RTC debe ser único en la implementación de Enterprise Voice. Una vez guardado el registro, el campo <STRONG>Nombre</STRONG> no puede editarse.

        
        3.  Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar a este registro de uso de RTC y, después, haga clic en **Aceptar**.
            
              - Para quitar una ruta de un registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            
              - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para obtener más información, consulte [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Haga clic en **Aceptar**.
    
      - Para editar un registro de uso de RTC que ya se ha asociado con la directiva de voz, siga el procedimiento siguiente:
        
        1.  Resalte el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.
        
        2.  Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y, después, haga clic en **Aceptar**.
            
              - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.
            
              - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para más información, consulte [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para más información, consulte [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Haga clic en **Aceptar**.

8.  Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro de la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.
    

    > [!NOTE]
    > Es importante el orden en el que aparecen en la lista de la directiva de voz los registros de uso de RTC. Lync Server recorre la lista de arriba abajo. Se recomienda ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.



9.  Para asociar y configurar los registros de uso de RTC correspondientes al desvío de llamadas y a las llamadas simultáneas de esta directiva de voz, realice una de las siguientes acciones:
    
      - Para usar los mismos registros de uso de RTC en el desvío de llamadas y las llamadas simultáneas que esta directiva de voz, seleccione la opción **Enrutar con los usos de RTC de llamada** en el menú desplegable.
    
      - Para permitir el desvío de llamadas y las llamadas simultáneas únicamente a usuarios de Lync internos, seleccione **Enrutar solo a usuarios de Lync internos** en el menú desplegable. Las llamadas no se desviarán a números de RTC externos.
    
      - Para especificar unos registros de uso de RTC para el desvío de llamadas y en las llamadas simultáneas distintos de los de esta directiva de voz, seleccione la opción **Enrutar con los usos de RTC personalizados** en el menú desplegable. Esta opción muestra un control para seleccionar unos registros de uso de RTC existentes o bien para crear otros registros de uso de RTC específicos para el desvío de llamadas y las llamadas simultáneas.
        
          - Para elegir uno o más registros de una lista con los registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas, haga clic en **Seleccionar**. Resalte los registros que desea asociar con esta directiva de desvío de voz y llamadas simultáneas y, después, haga clic en **Aceptar**.
        
          - Para quitar un registro de uso de RTC de esta directiva de desvío de llamadas y llamadas simultáneas, resalte el registro y haga clic en **Quitar**.
        
          - Para definir un nuevo registro de uso de RTC y asociarlo a esta directiva de desvío de llamadas y llamadas simultáneas:
            
            1.  Haga clic en **Nuevo** .
            
            2.  En el campo **Nombre**, escriba un nombre descriptivo único para el registro.
                

                > [!NOTE]
                > El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.

            
            3.  Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
                
                  - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y, después, haga clic en **Aceptar**.
                
                  - Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.
                
                  - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para más información, consulte [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para más información, consulte [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Haga clic en **Aceptar**.
        
          - Para editar un registro de uso de RTC ya asociado a esta directiva de voz:
            
            1.  Resalte el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.
            
            2.  Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
                
                  - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Enterprise Voice, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**.
                
                  - Para quitar una ruta de este registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
                
                  - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para obtener más información, consulte [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Haga clic en **Aceptar**.

10. (Opcional) Especifique un número para probar la directiva de voz y haga clic en **Ir**. Los resultados de la prueba se muestran en **Número convertido para probar**.
    

    > [!NOTE]
    > Puede guardar una directiva de voz que no haya pasado la prueba aún y volver a configurarla más adelante. Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">Probar el enrutamiento de voz en Lync Server 2013</A>.



11. Haga clic en **Aceptar**.

12. En la página **Directiva de voz**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    

    > [!NOTE]
    > Siempre que cree o modifique una directiva de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración. Para más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación referente a las operaciones.



13. (Opcional) El desvío de correo de voz desconecta las llamadas al correo de voz de un teléfono móvil cuando detecta que el correo de voz del teléfono del usuario responde automáticamente a la llamada. Con esto se permite que la llamada siga sonando en los otros extremos del usuario y que el usuario pueda responder a la llamada. Para ver más detalles sobre cómo configurar una directiva de correo de voz, consulte [Configuración de escape en correo de voz en Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

## Vea también

#### Tareas

[Crear una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Ver registros de uso de la RTC en Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Configuración de escape en correo de voz en Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  

#### Otros recursos

[Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)

