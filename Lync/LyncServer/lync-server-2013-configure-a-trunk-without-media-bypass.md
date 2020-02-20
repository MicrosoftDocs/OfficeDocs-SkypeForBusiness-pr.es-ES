---
title: 'Lync Server 2013: configurar un tronco sin desvío de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e3b8f0c14ca916c7a4920a4399df441fb61bc48
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a>Configurar un tronco sin omisión de medios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

Si desea configurar un enlace troncal con el desvío de medios deshabilitado, siga estos pasos. Si desea configurar un tronco con la omisión de medios habilitada, consulte [configurar un tronco con la omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

Tal como se describe a continuación, una configuración de tronco agrupa un conjunto de parámetros que se aplican a los troncos asignados a esta configuración de tronco. Una configuración de tronco puede tener ámbito global (se aplica a todos los troncos que no tienen sitios o configuración de grupo más específicos), ámbito de sitio o de grupo. La configuración del tronco de nivel de grupo se utiliza para adaptar una configuración de tronco específica a un único tronco.

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a>Para configurar un enlace troncal sin desvío de medios

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.

4.  En la página **Configuración del tronco**, utilice uno de los métodos siguientes para configurar un tronco:
    
      - Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración del tronco**.
    
      - Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:
        
          - **Tronco del sitio:** Elija el sitio para esta configuración de tronco en **seleccionar un sitio** y, a continuación, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, el sitio no aparece en **Seleccionar un sitio**. Esta configuración de tronco se aplicará a todos los troncos del sitio.
        
          - **Tronco de Grupo:** Elija el nombre del tronco al que se aplica esta configuración de tronco en **Seleccione un servicio** y haga clic en **Aceptar**. Este tronco puede ser el tronco raíz o los troncos adicionales definidos en el generador de topologías. Tenga en cuenta que si ya se ha creado una configuración de tronco para un tronco específico, el tronco no se mostrará en **Seleccionar un servicio**.
    
    <div>
    

    > [!NOTE]  
    > Una vez seleccionado el ámbito de la configuración de tronco, no se podrá cambiar.<BR>El campo <STRONG>Nombre</STRONG> está rellenado previamente con el nombre del sitio o servicio asociado a la configuración del tronco y no se puede cambiar.

    
    </div>

5.  Seleccione una de las opciones de **Nivel admitido de cifrado** siguientes:
    
      - **Obligatorio:** Se debe usar el cifrado de protocolo de transporte seguro en tiempo real (SRTP) para ayudar a proteger el tráfico entre el servidor de mediación y la puerta de enlace o central de conmutación (PBX).
    
      - **Opcional:** Se usará el cifrado SRTP si el proveedor de servicios o el fabricante del equipo lo admiten.
    
      - **No se admite:** El cifrado de SRTP no es compatible con el proveedor de servicios o el fabricante del equipo y, por lo tanto, no se usará.

6.  Asegúrese de que esté desactivada la casilla **Habilitar desvío de medios**.

7.  Active la casilla de verificación **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace de red telefónica conmutada [RTC] donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios conocido, desactive esta casilla.

8.  Si el tronco del mismo nivel admite la recepción de solicitudes SIP REFER del servidor de mediación, active la casilla de verificación **Habilitar la referencia de envío a la puerta de enlace** .

9.  (Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure los registros de uso de RTC a esta configuración de tronco. Los usos de RTC asociados a esta configuración de tronco se aplicarán a todas las llamadas entrantes al tronco que no tenga su origen en un extremo de Lync. Para administrar los registros de uso de RTC asociados a una configuración de tronco, use uno de los métodos siguientes:
    
      - Para seleccionar uno o más registros de una lista de todos los registros de uso de RTC disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.
    
      - Para quitar un registro de uso de RTC de esta configuración de tronco, resalte el registro y haga clic en **Quitar**.
    
      - Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco:
        
        1.  Haga clic en  **Nuevo **.
        
        2.  En el campo **Nombre**, especifique un nombre descriptivo único para el registro.
            
            <div>
            

            > [!NOTE]  
            > El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.

            
            </div>
        
        3.  Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de la telefonía IP empresarial, haga clic en **seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y haga clic en **Aceptar**.
            
              - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            
              - Para definir una ruta nueva y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta ya asociada a este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Haga clic en **Aceptar**.
    
      - Para editar un registro de uso de RTC ya asociado a esta configuración de tronco, lleve a cabo lo siguiente:
        
        1.  Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.
        
        2.  Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            
              - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de la telefonía IP empresarial, haga clic en **seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y haga clic en **Aceptar**.
            
              - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            
              - Para definir una ruta nueva y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar una ruta ya asociada a este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Haga clic en **Aceptar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Es importante asociar los registros de uso de RTC de acuerdo con el servidor de mediación del mismo nivel que está asociado al tronco que se está configurando. Si el servidor de mediación del mismo nivel es una puerta de enlace RTC o un controlador de borde de sesión (SBC), se recomienda encarecidamente que la configuración del tronco no esté asociada a un registro de uso de RTC que se enrute a un destino de RTC o a cualquier otro sistema descendente conectado a través de Lync. Server.

    
    </div>

10. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, seleccione el registro de uso de RTC y haga clic en la flecha arriba o abajo.
    
    <div>
    

    > [!IMPORTANT]  
    > Es importante el orden en el que aparecen en la lista de la configuración de tronco los registros de uso de RTC. Lync Server recorre la lista de arriba a abajo.

    
    </div>

11. **Habilitar cierre de RTP** debe seleccionarse para habilitar el desvío de medios para los clientes que se encuentren detrás de un firewall o NAT y para los SBC que admitan el cierre.

12. **Habilite el historial de llamadas reenviadas** para habilitar el envío de información de historial de llamadas a la puerta de enlace del servidor de mediación.

13. **Habilitar reenvío de datos P-Asserted-Identity** debe seleccionarse para habilitar el reenvío de la información del autor de la llamada de PAI entre el lado del servidor de mediación y la puerta de enlace (y viceversa), cuando esté presente.

14. **Habilitar temporizador de conmutación por error de enrutamiento saliente** debe seleccionarse para habilitar la conmutación por error rápida. La puerta de enlace asociada a este tronco puede proporcionar información cada 10 segundos durante el procesamiento de una llamada saliente. Si el servidor de mediación no recibe esta notificación, se producirá el redireccionamiento a otro tronco. Es necesario deshabilitar la conmutación por error rápida en las redes en las que la latencia puede retrasar el tiempo de respuesta o si la puerta de enlace tarda más de 10 segundos en responder.

15. (Opcional) Asocie y configure las **Reglas de traducción de números de llamada** para el tronco. Estas reglas de traducción se aplican a los números de llamadas salientes.
    
      - Para elegir una o más reglas de una lista de todas las reglas de conversión que están disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    
      - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener más información sobre cómo definir una regla nueva, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.
    
      - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**. Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.
    
      - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar**y, a continuación, en **Pegar**. Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" />Nota de seguridad:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. (Opcional) Asocie y configure las **Reglas de traducción de números llamados** para el tronco. Estas reglas de traducción se aplican a los números de llamadas salientes.
    
      - Para elegir una o más reglas de una lista de todas las reglas de conversión que están disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    
      - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener más información sobre cómo definir una regla nueva, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.
    
      - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**. Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.
    
      - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar**y, a continuación, en **Pegar**. Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.
    
    <div>
    

    > [!WARNING]  
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto.

    
    </div>

17. Asegúrese de que las reglas de conversión del tronco estén organizadas en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server recorre la lista de reglas de conversión de arriba abajo y usa la primera regla que coincide con el número marcado. Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida solamente con números de 11 dígitos que comiencen por -1425, asegúrese de que la regla que coincida con cualquier número de 11 dígitos se haya colocado <EM>debajo</EM> de la regla más restrictiva.

    
    </div>

18. Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.

19. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Siempre que cree o modifique una configuración de tronco, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar un tronco con la omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Definición de reglas de conversión en Lync Server 2013](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

