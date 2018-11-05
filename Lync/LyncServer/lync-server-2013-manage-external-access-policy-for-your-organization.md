---
title: 'Lync Server 2013: Administrar la directiva de acceso de la organización'
TOCTitle: Administrar la directiva de acceso de la organización
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48275289
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar la directiva de acceso de la organización en Lync Server 2013

 

_**Última modificación del tema:** 2013-10-07_

Después de implementar uno o varios Servidores perimetrales, debe habilitar los tipos de acceso externo que se permitirán en la organización.

De forma predeterminada, no hay ninguna directiva configurada para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos, el acceso de usuarios federados, incluso si ya ha habilitado la compatibilidad con el acceso de usuarios externos para su organización. Para controlar el uso del acceso de usuarios externos, debe configurar una o más directivas, especificando el tipo de acceso de usuarios externos que es compatible con cada directiva. Para la creación y configuración están disponibles los siguientes ámbitos de directivas. De forma predeterminada, se crea la directiva global, pero no se puede eliminar.

  - **Directiva global**   La directiva global se crea al implementar los servidores perimetrales. De forma predeterminada, no hay opciones de acceso de usuarios externos habilitadas en la directiva global. Para admitir el acceso de usuarios externos a nivel global, configure la directiva global para admitir uno o más tipos de opciones de acceso de usuarios externos. La directiva global se aplica a todos los usuarios de la organización, pero las directivas de sitio y las directivas de usuario reemplazan a la directiva global. Si elimina la directiva global, no se quita. En su lugar, se restablece la configuración predeterminada.

  - **Directiva de sitio**   Puede crear y configurar uno o varias directivas de sitio para limitar la compatibilidad de acceso de usuarios externos a sitios específicos. La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio. Por ejemplo, si se habilita el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos a un sitio específico. De forma predeterminada, una directiva de sitio se aplica a todos los usuarios de dicho sitio, aunque puede asignar una directiva de usuario a un usuario determinado para cambiar dicho parámetro de la directiva de sitio.

  - **Directiva de usuario**   Puede crear y configurar uno o varias directivas de sitio para limitar la compatibilidad de acceso de usuarios remotos a sitios específicos. La configuración de la directiva de usuario reemplaza la directiva global y la directiva de sitio, pero solo para los usuarios específicos a quienes se le asigna la directiva de sitio. Por ejemplo, si se habilita el acceso de usuarios remotos en la directiva global y en la directiva de sitio, puede especificar una directiva de usuario que deshabilite el acceso de usuarios remotos y luego asigne esa directiva de usuario a un usuario específico. Si crea una directiva de sitio, debe aplicarla a uno o más usuarios antes de que se haga efectiva.

> [!IMPORTANT]  
> La configuración de directiva de Lync Server que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva de Lync Server es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.



Estas opciones incluyen los siguientes tipos de acceso externo:

  - **Habilitar comunicaciones con usuarios federados**    Habilite esta opción si desea admitir el acceso de usuarios a los dominios de socios federados. Este parámetro configura la capacidad de los usuarios de comunicarse con otros dominios SIP federados, y también con proveedores alojados como Microsoft Office 365. La selección de esta opción le permite seleccionar la opción de permitir la comunicación con dominios XMPP federados.
    
    Como opción, puede activar **Habilitar comunicaciones con socios XMPP federados** si primero activa **Habilitar comunicaciones con usuarios federados** . La federación XMPP es una federación con las organizaciones que usan el protocolo de mensajería extensible y presencia (XMPP).
    

    > [!NOTE]
    > Si habilita la federación XMPP, también debe seleccionar la implementación de <STRONG>Federación XMPP</STRONG> en la sección de configuración de Grupos de servidores perimetralesde Generador de topologías. La configuración de la federación XMPP implementa un proxy XMPP en el Servidor perimetral y una puerta de enlace XMPP en el Servidor front-end.



  - **Habilitar comunicaciones con usuarios remotos**    Habilite esta opción si desea que los usuarios de su organización que queden fuera del firewall como, por ejemplo, teletrabajadores y usuarios que estén de viaje, se puedan conectar a Lync Server en Internet.

  - **Habilitar comunicaciones con usuarios públicos**    Habilite esta opción si desea que los usuarios internos puedan comunicarse con los contactos de proveedores de MI públicos, tales como los proporcionados por Windows Live, Yahoo\! y America Online (AOL).
    
    > [!IMPORTANT]  
	> <ul>
    > <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
    > <li><p>PIC USL es una licencia de suscripción por usuario/por mes requerida por Lync Server u Office Communications Server para la federación con Yahoo! Messenger. La posibilidad de Microsoft de proporcionar este servicio depende de la compatibilidad con Yahoo!, cuyo contrato subyacente está llegando a su fin.</p></li>
    > <li><p>Hoy más que nunca, Lync es una herramienta eficaz para conectarse dentro de una organización y con individuos de todo el mundo. La federación con Windows Live Messenger no requiere ninguna licencia de usuario o dispositivo adicional aparte de la CAL estándar de Lync. La federación con Skype se agregará a esta lista, lo que permitirá a los usuarios de Lync conectarse con cientos de millones de personas a través de mensajería instantánea y voz.</p></li>
    > </ul>



> [!NOTE]
> Además de habilitar la compatibilidad de acceso de usuarios externos, también debe configurar directivas para controlar el uso del acceso de usuarios externos en su organización antes de que los usuarios obtengan cualquier tipo de acceso para usuarios externos. Para detalles sobre cómo crear, configurar y aplicar directivas para acceso de usuarios externos, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013</A>.



**Para ver las directivas de acceso externo mediante cmdlets de Windows PowerShell**

  - Puede ver las directivas de acceso externo con Shell de administración de Lync Server y el cmdlet **Get-CsExternalAccessPolicy**. Puede ejecutar este cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Para ver información sobre todas las directivas de acceso externas, escriba el comando siguiente en el Shell de administración de Lync Server y luego presione ENTRAR:
    
        Get-CsExternalAccessPolicy
    
    Este comando devolverá información similar a la siguiente:
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

## En esta sección

  - [Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Configurar directivas para el control del acceso de usuarios remotos en Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Restablecer o eliminar las directivas de acceso de usuarios externos en Lync Server 2013](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

