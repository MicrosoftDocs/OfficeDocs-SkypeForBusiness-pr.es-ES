---
title: 'Lync Server 2013: configurar un tronco con omisión de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16c12a5d8cff03f8d5755b5a2b54a6ff4dcf8399
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a>Configure a trunk with media bypass in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-07_

Siga estos pasos para configurar un tronco con la omisión de medios habilitada. Para configurar un tronco con la omisión de medios deshabilitada, vea [configurar un tronco sin omitir medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md). La omisión de elementos multimedia es útil cuando desea minimizar el número de servidores de mediación implementados. Normalmente, un grupo de servidores de mediación se implementará en un sitio central y controlará las puertas de enlace en los sitios de sucursales. Habilitar la omisión de medios permite que las llamadas de la red telefónica conmutada (RTC) desde clientes en sitios de sucursal se dirijan directamente a través de las puertas de enlace a esos sitios. Las directivas de llamadas salientes de Lync Server 2013 y de Enterprise Voice deben configurarse correctamente para que las llamadas RTC de clientes de un sitio de sucursal se enruten a la puerta de enlace adecuada.

Se recomienda habilitar la omisión de medios. Ahora bien, antes de hacerlo en un tronco SIP, asegúrese de que su proveedor de troncos SIP cualificado es compatible con la omisión de medios y puede aceptar los requisitos para habilitar correctamente el escenario. Concretamente, el proveedor debe disponer de las direcciones IP de los servidores en la red interna de la organización. Si el proveedor no admite este escenario, la omisión de elementos multimedia no se realizará correctamente. Para obtener más información, consulte [planificación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la documentación de planeación.

<div>


> [!NOTE]  
> La omisión de medios no funcionará con todas las puertas de enlace de red de telefonía pública conmutada (RTC), IP-PBX ni el controlador de borde de sesión (SBC). Microsoft ha probado una serie de puertas de enlace RTC y SBC con asociados certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. La omisión de contenido multimedia solo se admite con productos y versiones que se enumeran en el programa de interoperabilidad <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>abierta de comunicaciones unificadas: Lync Server en.



</div>

Una configuración de tronco tal como se describe más abajo agrupa un conjunto de parámetros que se aplican a los troncos a los que se ha asignado esta configuración de tronco. Una configuración de tronco concreta puede tener ámbito global (todos los troncos que no tengan una configuración de sitio o grupo de servidores más concreta), de sitio o de grupo de servidores. La configuración de tronco de nivel de grupo de servidores se utiliza para limitar el ámbito de una configuración de tronco concreta a un único tronco.

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a>Para configurar un tronco con omisión de medios

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración de tronco**.

4.  En la página **Configuración de tronco**, use uno de los métodos siguientes para configurar un tronco:
    
      - Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración de tronco**.
    
      - Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:
        
          - **Tronco del sitio:** Elija el sitio para esta configuración de tronco en **Seleccione un sitio**y, a continuación, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, el sitio no aparece en **Seleccionar un sitio**. Esta configuración de tronco se aplicará a todos los troncos del sitio.
        
          - **Tronco de la piscina:** Elija el nombre del tronco al que se aplica esta configuración troncal. Este tronco puede ser el tronco raíz o cualquier otro tipo de troncos definidos en el generador de topologías. En **Seleccionar un servicio**, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración para un tronco específico, dicho tronco no aparecerá en **Seleccionar un servicio**.
    
    <div>
    

    > [!NOTE]  
    > Una vez seleccionado el ámbito de la configuración del tronco, no se podrá cambiar.<BR>El campo <STRONG>Nombre</STRONG> está rellenado previamente con el nombre del sitio o servicio asociado a la configuración del tronco y no se puede cambiar.

    
    </div>

5.  Especifique un valor en **Número máximo de diálogos iniciales admitidos**. Es el número máximo de respuestas bifurcadas que una puerta de enlace de red telefónica conmutada (RTC), un sistema PBX IP o el controlador de borde de sesión (SBC) del proveedor de servicios puede recibir para una invitación (INVITE) enviada al servidor de mediación. El valor predeterminado es 20.
    
    <div>
    

    > [!NOTE]  
    > Antes de cambiar este valor, póngase en contacto con su proveedor de servicios o fabricante de equipos para obtener información detallada sobre las capacidades de su sistema.

    
    </div>

6.  Seleccione una de las opciones de  **Nivel admitido de cifrado** siguientes:
    
      - **Requerido:** El protocolo de transporte seguro (SRTP) debe usarse para ayudar a proteger el tráfico entre el servidor de mediación y la puerta de enlace o la central de conmutación (PBX).
    
      - **Opcional:** El cifrado SRTP se usará si el proveedor de servicios o el fabricante de equipos lo admiten.
    
      - **No es compatible:** El cifrado de SRTP no es compatible con el proveedor de servicios o el fabricante del equipo y, por lo tanto, no se usará.

7.  Active la casilla **Habilitar omisión de medios** si desea que los medios omitan el servidor de mediación para que sea la entidad del mismo nivel que el tronco la que realice el procesamiento.
    
    <div>
    

    > [!IMPORTANT]  
    > Para que la omisión de medios funcione correctamente, es preciso que la puerta de enlace de RTC, el sistema PBX IP o el controlador de borde de sesión del proveedor de servicios sean compatibles con ciertas capacidades. Para obtener más información, consulte <A href="lync-server-2013-planning-for-media-bypass.md">planificación de la omisión de medios en Lync Server 2013</A> en la documentación de planeación.

    
    </div>

8.  Active la casilla **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace RTC donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios conocido, desactive esta casilla.

9.  Si el tronco del mismo nivel admite la recepción de solicitudes SIP de referencia del servidor de mediación, seleccione la casilla de verificación **Habilitar envío consulte la puerta de enlace** .
    
    <div>
    

    > [!NOTE]  
    > Si deshabilita esta opción mientras la opción <STRONG>Habilitar omisión de medios</STRONG> está seleccionada, se requerirá una configuración adicional. Si la entidad del mismo nivel del tronco no es compatible con la recepción de solicitudes SIP REFER del servidor de mediación y se ha habilitado el desvío de medios, es preciso que ejecute el cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> para deshabilitar el RTCP para las llamadas activas y en espera con el fin de admitir las condiciones adecuadas para la omisión de medios. Para obtener más información, consulte la documentación del <A href="lync-server-2013-lync-server-management-shell.md">Shell de administración de Lync Server 2013</A> .<BR>También puede seleccionar <STRONG>Habilitar referencia mediante el control de llamadas a terceros</STRONG> si desea que los medios omitan las llamadas transferidas y la puerta de enlace no admita solicitudes SIP REFER.

    
    </div>

10. (Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure registros de uso de la RTC a esta configuración de tronco. Los usos de RTC asociados a esta configuración de tronco se aplicarán para todas las llamadas entrantes a través del tronco que no se originen desde un punto de conexión de Lync. Para administrar registros de uso de la RTC asociados a una configuración de tronco, use uno de los métodos siguientes:
    
      - Para seleccionar uno o varios registros de una lista de todos los registros de uso de RTC disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.
    
      - Para quitar un registro de uso de RTC de esta configuración de tronco, seleccione el registro y haga clic en **Quitar**.
    
      - Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco, haga lo siguiente:
        
        1.  Haga clic en **Nuevo**.
        
        2.  En el campo **Nombre**, escriba un nombre descriptivo único para el registro.
            
            <div>
            

            > [!NOTE]  
            > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.

            
            </div>
        
        3.  Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**.
            
              - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            
              - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, vea [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. Para obtener más información, vea [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Haga clic en **Aceptar**.
    
      - Para editar un registro de uso de RTC ya asociado a esta configuración de tronco:
        
        1.  Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.
        
        2.  Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**.
            
              - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            
              - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, vea [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. Para obtener más información, vea [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Haga clic en **Aceptar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Es importante asociar los registros de uso de RTC según el servidor de mediación del mismo nivel que esté asociado al tronco que se configure. Si el servidor de mediación del mismo nivel es una puerta de enlace RTC o un controlador de borde de sesión (SBC), se recomienda enfáticamente que la configuración de troncal no esté asociada a un registro de uso de RTC que se enrute a un destino RTC o a cualquier otro sistema indirecto conectado a través de Lync. Servidores.

    
    </div>

11. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, seleccione el registro de uso de RTC y haga clic en las flechas arriba o abajo.
    
    <div>
    

    > [!IMPORTANT]  
    > El orden en el que aparecen en la lista de configuración del tronco los registros de uso de RTC es importante. Lync Server recorre la lista de arriba a abajo.

    
    </div>

12. Debe seleccionarse **Habilitar cierre RTP** si se desea habilitar la omisión de medios para clientes situados detrás de una traducción de direcciones de red (NAT) o firewall y un SBC que admita cierre.

13. **Habilitar el historial de llamadas hacia adelante** debe seleccionarse para habilitar el envío de información del historial de llamadas a la puerta de enlace del servidor de mediación.

14. **Habilitar Forward-Asserted: los datos de identidad** deben seleccionarse para habilitar la identidad de firma de p-asserted-Identity (PAI) la información del originador de llamadas se desviará entre el lado del servidor de mediación y la puerta de enlace (y viceversa) cuando estén presentes.

15. Debe seleccionar la opción **Habilitar temporizador de conmutación por error del enrutamiento de salida** para que la conmutación por error sea más rápida. La puerta de enlace asociada con este tronco puede notificar en un plazo de 10 segundos que se está procesando una llamada saliente. El redireccionamiento a otro tronco se producirá si el servidor de mediación no recibe esta notificación. En las redes en las que la latencia pueda retrasar el tiempo de respuesta o si la puerta de enlace se demora más de 10 segundos en responder, deberá deshabilitarse la conmutación por error rápida.

16. (Opcional) Asocie y configure **Reglas de traducción de números de llamada** para el tronco. Estas reglas de conversión se aplican al número desde donde se realizó la llamada (para las llamadas salientes).
    
      - Para elegir una o más reglas de una lista de todas las reglas de traducción disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    
      - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nuevo**. Para obtener más información sobre cómo definir una nueva regla, vea [definir reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.
    
      - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. Para obtener información detallada, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.
    
      - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. Para obtener más información, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.
    
    <div>
    

    > [!WARNING]  
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto.

    
    </div>

17. (Opcional) Asocie y configure **Reglas de traducción de números llamados** para el tronco. Estas reglas de conversión se aplican al número llamado en una llamada saliente.
    
      - Para elegir una o más reglas de una lista de todas las reglas de traducción disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    
      - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nuevo**. Para obtener más información sobre cómo definir una nueva regla, vea [definir reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.
    
      - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. Para obtener información detallada, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.
    
      - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. Para obtener más información, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.
    
    <div>
    

    > [!WARNING]  
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas pudieran entrar en conflicto.

    
    </div>

18. Asegúrese de que las reglas de conversión del tronco se dispongan en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 recorre la lista de reglas de traducción de la parte superior abajo y usa la primera regla que coincida con el número marcado. Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida solamente con números de 11 dígitos que comiencen por +1425, asegúrese de que la regla que coincida con cualquier número de 11 dígitos se haya colocado <EM>por debajo</EM> de la regla más restrictiva.

    
    </div>

19. Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.

20. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Al crear o modificar la configuración de un tronco, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

Una vez que haya configurado el tronco, continúe con la configuración de la omisión de medios seleccionando las opciones de omisión de multimedia global, como se describe en [Opciones de omisión de multimedia en Lync Server 2013](lync-server-2013-global-media-bypass-options.md) en la documentación de implementación.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[Configurar la omisión de medios en Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Opciones de omisión de multimedia global en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

