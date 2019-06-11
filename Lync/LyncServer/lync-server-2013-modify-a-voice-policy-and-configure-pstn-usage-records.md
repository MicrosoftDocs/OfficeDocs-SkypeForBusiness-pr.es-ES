---
title: 'Lync Server 2013: modificar una directiva de voz y configurar los registros de uso de RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb7c4cdc47c0624b3d94d0dc52c527310f803d83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Siga estos pasos si desea modificar una directiva de voz. Si desea crear una nueva Directiva de voz, vea [crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) para el procedimiento.

<div>


> [!NOTE]  
> Si un usuario se asigna a una directiva de voz no tiene ningún registro de uso de red telefónica pública conmutada (RTC) asociado, el usuario no puede realizar llamadas salientes. Para obtener una lista de todos los registros de uso de RTC disponibles en su implementación de telefonía IP empresarial y ver sus propiedades, consulte <A href="lync-server-2013-view-pstn-usage-records.md">ver los registros de uso de RTC en Lync Server 2013</A>.



</div>

<div>

## <a name="to-modify-a-voice-policy"></a>Para modificar una directiva de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, después, en **Directiva de voz**.

4.  En la página **Directiva de voz**, haga doble clic en el nombre de una directiva de voz.
    
    <div>
    

    > [!NOTE]  
    > El ámbito y el nombre se establecieron cuando se creó la directiva de voz. No pueden modificarse.

    
    </div>

5.  (Opcional) En **Editar directiva de voz**, especifique otra información descriptiva sobre la directiva de voz.

6.  Active o desactive las casillas siguientes para habilitar o deshabilitar cada una de las **Características de llamadas**:
    
      - **Voice mail escape** evita que las llamadas se redirijan inmediatamente al sistema de correo de voz del teléfono móvil del usuario cuando está configurada la opción de llamadas simultáneas y el teléfono está desactivado, se ha quedado sin batería o está fuera de alcance.
        
        <div>
        

        > [!NOTE]  
        > Esta característica solo se puede configurar a través del shell de administración de Lync Server.

        
        </div>
    
      - El **desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente. Lync Server 2013 proporciona un intervalo significativamente más amplio de opciones de configuración para el desvío de llamadas. Por ejemplo, si una organización no desea que las llamadas entrantes se desvíen externamente a la RTC, un administrador puede aplicar una directiva de voz especial para implementar esta restricción. Está habilitado de forma predeterminada.
    
      - La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre. En Lync Server 2013, un delegado puede configurar la llamada simultánea que permite que las llamadas entrantes a su jefe suenen a todos los destinos de timbre simultáneo del delegado. De esta forma, el delegado dispone de mayor flexibilidad a la hora de responder a las llamadas dirigidas administrador. Esta opción está habilitada de forma predeterminada.
    
      - La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Está opción está habilitada de forma predeterminada.
    
      - El **estacionamiento de llamadas** permite que los usuarios pongan las llamadas en espera para que se puedan atender desde otro teléfono u otro cliente. Esta opción está deshabilitada de forma predeterminada.
    
      - La **función de llamadas simultáneas** permite que las llamadas entrantes suenen en más teléfonos (por ejemplo, un móvil) u otros dispositivos de extremo. Lync Server 2013 proporciona un intervalo significativamente más amplio de opciones de configuración para llamadas simultáneas. Está habilitada de forma predeterminada.
    
      - La **llamada de equipo** permite a los usuarios de un equipo determinado responder llamadas por otros miembros del equipo. Está habilitada de forma predeterminada.
    
      - La reenrutación de **RTC** permite que las llamadas realizadas por los usuarios que tienen asignada esta directiva a otros usuarios de la empresa se vuelvan a enrutar en la red de telefonía pública conmutada (RTC) si la WAN está congestionada o no disponible. Está habilitado de forma predeterminada.
    
      - La anulación de la **Directiva de ancho de banda** permite a los administradores anular las decisiones de directiva de control de admisión de llamadas (CAC) para un usuario en particular. Está deshabilitado de forma predeterminada.
        
        <div>
        

        > [!NOTE]  
        > La directiva se invalidará solo para llamadas entrantes dirigidas a dicho usuario, pero no para las llamadas salientes que realice el usuario. Una vez establecida la sesión, el consumo de ancho de banda se registrará de forma detallada. Este parámetro debe usarse con moderación.

        
        </div>
    
      - El **seguimiento de llamadas** malintencionadas permite a los usuarios denunciar llamadas malintencionadas (como amenazas de bomba) mediante la interfaz de usuario del cliente, que a su vez marca las llamadas en los registros de detalles de llamadas (CDRs). Está deshabilitada de forma predeterminada.

7.  Para asociar y configurar los registros de uso de RTC correspondientes a esta directiva de voz, realice una de las siguientes acciones:
    
      - Para elegir uno o varios registros de una lista que contiene todos los registros de uso de RTC disponibles en la implementación de la Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de voz y después haga clic en **Aceptar**.
    
      - Para quitar un registro de uso de RTC de esta directiva de voz, resalte el registro y haga clic en **Quitar**.
    
      - Para definir un nuevo registro de uso de RTC y asociarlo a esta directiva de voz:
        
        1.  Haga clic en **Nuevo**.
        
        2.  En el campo **Nombre**, escriba un nombre descriptivo único para el registro. Por ejemplo, puede que desee crear un registro de uso de RTC llamado **Redmond** para los empleados de Redmond a tiempo completo, y otro registro llamado **RedmondTemps** para los empleados temporales.
            
            <div>
            

            > [!NOTE]  
            > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.

            
            </div>
        
        3.  Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.
            
              - Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.
            
              - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, vea [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para obtener más información, vea [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Haga clic en **Aceptar**.
    
      - Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:
        
        1.  Resalte el registro de uso de RTC que desee editar y haga clic en   **Mostrar detalles**.
        
        2.  Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.
            
              - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.
            
              - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, vea [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para obtener más información, vea [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Haga clic en **Aceptar**.

8.  Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.
    
    <div>
    

    > [!NOTE]  
    > Es importante el orden en el que aparecen en la lista de la directiva de voz los registros de uso de RTC. Lync Server recorre la lista desde arriba hacia abajo. Recomendamos ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

    
    </div>

9.  Para asociar y configurar registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas en esta directiva de voz, haga una de las acciones siguientes:
    
      - Para usar los mismos registros de uso de RTC que esta directiva de voz, para el desvío de llamadas y las llamadas simultáneas, seleccione la opción **Distribuir con los usos de la RTC de llamada** en el menú desplegable.
    
      - Para permitir el desvío de llamadas y las llamadas simultáneas solo a los usuarios internos de Lync, seleccione enrutar **solo para usuarios internos de Lync** en el menú desplegable. Calls will not be forwarded to external PSTN numbers.
    
      - Para especificar unos registros de uso de RTC para el desvío de llamadas y en las llamadas simultáneas distintos de los de esta directiva de voz, seleccione la opción **Distribuir con los usos de la RTC personalizados** en el menú desplegable. Esta opción muestra un control para seleccionar unos registros de uso de RTC existentes o bien para crear otros registros de uso de RTC específicos para el desvío de llamadas y las llamadas simultáneas.
        
          - Para elegir uno o más registros de una lista de registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de desvío de llamadas y de llamadas simultáneas y después haga clic en **Aceptar**.
        
          - Para quitar un registro de uso de RTC de esta directiva de desvío de llamadas y de llamadas simultáneas, resalte el registro y haga clic en **Quitar**.
        
          - Para definir un registro de uso de RTC nuevo y asociarlo a esta directiva de desvío de llamadas y de llamadas simultáneas, haga lo siguiente:
            
            1.  Haga clic en **Nuevo**.
            
            2.  En el campo **Nombre**, escriba un nombre descriptivo único para el registro.
                
                <div>
                

                > [!NOTE]  
                > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.

                
                </div>
            
            3.  Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
                
                  - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.
                
                  - Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.
                
                  - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, vea [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para obtener más información, vea [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Haga clic en **Aceptar**.
        
          - Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:
            
            1.  Resalte el registro de uso de RTC que desee editar y haga clic en   **Mostrar detalles**.
            
            2.  Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
                
                  - Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.
                
                  - Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.
                
                  - Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, vea [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**. Para obtener más información, vea [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Haga clic en **Aceptar**.

10. (Opcional) Especifique un número para probar la directiva de voz y haga clic en **Ir**. Los resultados de la prueba se muestran en **Número convertido para probar**.
    
    <div>
    

    > [!NOTE]  
    > Puede guardar una directiva de voz que aún no pase la prueba y, a continuación, volver a configurarla más tarde. Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.

    
    </div>

11. Haga clic en **Aceptar**.

12. En la página **Directiva de voz**, haga clic en **Confirmar** y después en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Al crear o modifica runa directiva de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

13. (Opcional) Voicemail Escape detecta que se ha respondido de forma inmediata a una llamada desde el correo de voz del teléfono móvil del usuario. Con esto se permite que la llamada siga sonando en los otros extremos del usuario y que el usuario pueda responder a la llamada. Para obtener más información sobre cómo configurar una directiva de correo de voz, vea [configurar la configuración de escape de correo de voz en Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Ver los registros de uso de RTC en Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Configurar el escape del correo de voz en Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  


[Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

