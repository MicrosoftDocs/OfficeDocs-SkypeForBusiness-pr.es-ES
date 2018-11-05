---
title: "Crear una directiva de voz y configurar registros de uso de RTC en Lync Server 2013"
TOCTitle: "Créer strat. et voix et conf. les enr. d’ut. PSTN dans Lync Server 2013"
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48276993
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear una directiva de voz y configurar registros de uso de RTC en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Siga estos pasos para crear una nueva directiva de voz. Si desea editar una directiva de voz, vea [Modificar una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) para ver el procedimiento.


> [!NOTE]
> Cada directiva de voz debe tener al menos un registro de uso de RTC asociado. Para ver un listado de todos los registros de uso de RTC disponibles en su implementación de Telefonía IP empresarial y sus propiedades, vea <A href="lync-server-2013-view-pstn-usage-records.md">Ver registros de uso de la RTC en Lync Server 2013</A>.



## Para crear una directiva de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y luego en **Directiva de voz**.

4.  En la página **Directiva de voz**, haga clic en **Nueva** y seleccione el ámbito de la nueva directiva:
    
      - La **directiva de sitio** se aplica a todo un sitio, excepto a los usuarios o grupos que estén asignados a una directiva de usuario. Si selecciona Sitio al definir el ámbito de la directiva, elija un sitio en el cuadro de diálogo **Seleccionar un sitio**. Si ya se creó una directiva de voz para un sitio, el sitio no aparecerá en el cuadro de diálogo **Seleccionar un sitio**.
    
      - La **directiva de usuario** se puede aplicar a usuarios o grupos concretos.

5.  Si el ámbito de una directiva de voz es Usuario, escriba un nombre descriptivo para la directiva en el campo **Nombre**.
    

    > [!NOTE]
    > Si el ámbito de la directiva de voz es Sitio, el campo <STRONG>Nombre</STRONG> de la <STRONG>Nueva directiva de voz</STRONG> se rellena automáticamente con el nombre del sitio y no se puede cambiar.



6.  (Opcional) Añada información descriptiva sobre la directiva de voz.

7.  Active o desactive las siguientes casillas para habilitar o deshabilitar cada una de las **Características de llamada** de esta directiva de voz:
    
      - **Voice mail escape** evita que las llamadas se redirijan inmediatamente al sistema de correo de voz del teléfono móvil del usuario cuando está configurada la opción de llamadas simultáneas y el teléfono está desactivado, se ha quedado sin batería o está fuera de alcance.
        

        > [!NOTE]
        > Esta característica solo se puede configurar con el Shell de administración de Lync Server

    
      - **Desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente. En Lync Server 2013 proporciona una gama de opciones de configuración mucho más amplia para el desvío de llamadas. Por ejemplo, si una organización no desea que las llamadas entrantes se desvíen externamente al RTC, un administrador puede aplicar una directiva de voz especial para implementar esta restricción. Opción habilitada habitualmente.
    
      - La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre. En Lync Server 2013, un delegado puede configurar la opción de llamadas simultáneas que permite que las llamadas entrantes dirigidas al administrador vayan también a los destinos de llamadas simultáneas del delegado. De esta forma, el delegado dispone de mayor flexibilidad a la hora de responder a las llamadas dirigidas administrador. Opción habilitada habitualmente.
    
      - La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Opción habilitada habitualmente.
    
      - El **estacionamiento de llamadas** permite a los usuarios poner llamadas en espera y después recibir la llamada de otro teléfono o cliente. Opción deshabilitada habitualmente.
    
      - La función de **llamadas simultáneas** permite que las llamadas entrantes suenen en más teléfonos (por ejemplo, un móvil) u otros dispositivos de extremo. Lync Server 2013 proporciona una gama de opciones de configuración mucho más amplia para las llamadas simultáneas. Opción habilitada habitualmente.
    
      - La **llamada de equipo** permite a los usuarios de un equipo determinado responder llamadas por otros miembros del equipo. Opción habilitada habitualmente.
    
      - **Volver a enrutar en RTC** permite que las llamadas realizadas por usuarios que tienen asignada esta directiva a otros usuarios de la empresa se puedan volver a redirigir en la red telefónica conmutada (RTC) si la red WAN está saturada o no disponible. Opción habilitada habitualmente.
    
      - El **reemplazo de directiva de ancho de banda** permite a los administradores reemplazar las decisiones de la directiva de control de admisión de llamadas para un usuario concreto. Opción deshabilitada habitualmente.
        

        > [!NOTE]
        > La directiva se reemplazará solo para las llamadas entrantes que reciba el usuario, y no para las llamadas salientes que realice el usuario. Una vez establecida la sesión, se justificará detalladamente el consumo de ancho de banda. Esta configuración se debe usar con moderación, y recomendamos evitarla para tomar las decisiones correctas en el control de admisión de llamadas.

    
      - **Seguimiento de llamadas malintencionadas** permite a los usuarios informar sobre llamadas malintencionadas (como amenazas de bomba) usando la interfaz de usuario del cliente, y hace que la llamada quede señalada en los registros de detalles de llamadas. Opción deshabilitada habitualmente.

8.  Para asociar y configurar los registros de uso de RTC correspondientes a esta directiva de voz, realice una de las siguientes acciones:
    
      - Para elegir uno o varios registros de una lista que contiene todos los registros de uso de RTC disponibles en la implementación de la Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de voz y después haga clic en **Aceptar**.
    
      - Para quitar un registro de uso de RTC de esta directiva de voz, resalte el registro y haga clic en **Quitar**.
    
      - Para definir un nuevo registro de uso de RTC y asociarlo a esta directiva de voz:
        
        1.  Haga clic en **Nuevo**.
        
        2.  En el campo **Nombre**, escriba un nombre descriptivo único para el registro. Por ejemplo, puede que desee crear un registro de uso de RTC llamado **Redmond** para los empleados de Redmond a tiempo completo, y otro llamado **RedmondTemps** para los empleados temporales.
            

            > [!NOTE]
            > El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.

        
        3.  Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de la Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y después haga clic en **Aceptar**.
            
              - Para quitar una ruta del registro de uso de RTC, resalte la ruta y después haga clic en **Quitar**.
            
              - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para más información, vea [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para más información, vea [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Haga clic en **Aceptar**.
    
      - Para editar un registro de uso de RTC ya asociado a esta directiva de voz:
        
        1.  Resalte el registro de uso de RTC que desea editar y haga clic en **Mostrar detalles**.
        
        2.  Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.
            
              - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y después haga clic en **Quitar**.
            
              - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para más información, vea [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta que ya está asociado a este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para más información, vea [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Haga clic en **Aceptar**.

9.  Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.
    
    > [!IMPORTANT]  
    > Es importante el orden en el que aparecen en la lista de la directiva de voz los registros de uso de RTC. Lync Server recorre la lista de arriba abajo. Recomendamos ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.
    


10. Para asociar y configurar registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas en esta directiva de voz, haga una de las acciones siguientes:
    
      - Para usar los mismos registros de uso de RTC que esta directiva de voz, para el desvío de llamadas y las llamadas simultáneas, seleccione la opción **Redirigir con los usos de PSTN** en el menú desplegable.
    
      - Para permitir el desvío de llamadas y las llamadas simultáneas solo para los usuarios de Lync internos, seleccione la opción **Redirigir a usuarios de Lync internos únicamente** en el menú desplegable. Las llamadas no se desviarán a los números de RTC externos.
    
      - Para usar unos registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas que no sean los que se usan para esta directiva de voz, seleccione la opción **Redirigir con usos de PSTN personalizados** en el menú desplegable. Esta opción muestra un control para seleccionar registros de uso de RTC o crear nuevos registros de uso de RTC destinados concretamente a desviar llamadas o a realizar llamadas simultáneas.
        
          - Para elegir uno o más registros de una lista de registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de desvío de llamadas y de llamadas simultáneas y después haga clic en **Aceptar**.
        
          - Para quitar un registro de uso de RTC de esta directiva de desvío de llamadas y de llamadas simultáneas, resalte el registro y haga clic en **Quitar**.
        
          - Para definir un registro de uso de RTC nuevo y asociarlo a esta directiva de desvío de llamadas y de llamadas simultáneas, haga lo siguiente:
            
            1.  Haga clic en **Nuevo**.
            
            2.  En el campo **Nombre**, escriba un nombre descriptivo único para el registro.
                

                > [!NOTE]
                > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.

            
            3.  Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
                
                  - Para elegir uno o más registros en una lista de todos los registros de uso de RTC disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de voz y después haga clic en **Aceptar**.
                
                  - Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.
                
                  - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para más información, vea [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para más información, vea [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Haga clic en **Aceptar**.
        
          - Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:
            
            1.  Resalte el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.
            
            2.  Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
                
                  - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.
                
                  - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.
                
                  - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para más información, vea [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para más información, vea [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Haga clic en **Aceptar**.

11. (Opcional) Especifique un número para probar la directiva de voz y haga clic en **Ir**. Los resultados de la prueba se muestran en **Número convertido para probar**.
    

    > [!NOTE]
    > Puede guardar una directiva de voz que no haya pasado la prueba aún y volver a configurarla más adelante. Para más información, vea <A href="lync-server-2013-test-voice-routing.md">Probar el enrutamiento de voz en Lync Server 2013</A>.



12. Haga clic en **Aceptar**.

13. En la página **Directiva de voz**, haga clic en **Confirmar** y después en **Confirmar todo**.
    

    > [!NOTE]
    > Siempre que cree o modifique una directiva de voz, ejecute el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración. Para más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación referente a las operaciones.



14. (Opcional) Voicemail Escape detecta que el correo de voz del teléfono móvil del usuario responde inmediatamente a una llamada y desconecta esta llamada de dicho correo de voz. De esta forma, la llamada sigue sonando en los demás extremos del usuario y le da a este la oportunidad de responder a la llamada. Para más información sobre la configuración de una directiva de correo de voz, vea [Configuración de escape en correo de voz en Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

## Vea también

#### Tareas

[Modificar una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Ver registros de uso de la RTC en Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Configuración de escape en correo de voz en Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  

#### Otros recursos

[Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)

