---
title: 'Lync Server 2013: administrar la Directiva de acceso externo para la organización'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a7a3d612de9cf530e512031b7009a83ad9c391c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>Administrar la Directiva de acceso externo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

Después de implementar uno o varios servidores perimetrales, debe habilitar los tipos de acceso externo que serán compatibles con la organización.

De forma predeterminada, no hay ninguna directiva configurada para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos, el acceso de usuarios federados, incluso si ya ha habilitado la compatibilidad con el acceso de usuarios externos para su organización. Para controlar el uso del acceso de usuarios externos, debe configurar una o más directivas, especificando el tipo de acceso de usuarios externos que es compatible con cada directiva. Para la creación y configuración están disponibles los siguientes ámbitos de directivas. De forma predeterminada, se crea la directiva global, pero no se puede eliminar.

  - **Directiva global:**   la directiva global se crea al implementar los servidores perimetrales. De forma predeterminada, no hay habilitadas opciones de acceso de usuarios externos en la directiva global. Para admitir el acceso de usuarios externos en el nivel global, debe configurar la directiva global para que admita uno o más tipos de opciones de acceso de usuarios externos. La directiva global se aplica a todos los usuarios de su organización, pero las directivas de sitio y usuario invalidan la directiva global. Eliminar la directiva global no hará que desaparezca. En lugar de eso, se restablece la configuración predeterminada.

  - **Directiva de sitio**   puede crear y configurar una o varias directivas de sitio para limitar la compatibilidad con el acceso de usuarios externos a sitios específicos. La configuración de la directiva de sitio invalida la directiva global, pero solo en el caso del sitio específico que determina la directiva. Por ejemplo, si activa el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos para un sitio específico. De forma predeterminada, una directiva de sitio se aplica a todos los usuarios de dicho sitio, aunque puede asignar una directiva de usuario a un usuario determinado para invalidar dicho parámetro de la directiva de sitio.

  - **Directiva de usuario**   puede crear y configurar una o más directivas de usuario para limitar la compatibilidad del acceso de usuarios remotos a usuarios específicos. La configuración de la directiva de usuario invalida la directiva global y la directiva de sitio, pero solo para los usuarios concretos a los que se ha asignado la directiva de usuario. Por ejemplo, si deshabilita el acceso de usuarios remotos en la directiva global y a la directiva de sitio, puede especificar una directiva de usuario para deshabilitar el acceso de usuarios remotos y, a continuación, asignar dicha directiva de usuario a usuarios específicos. Si crea una directiva de sitio, debe aplicarla a uno o más usuarios antes de que se haga efectiva.

<div>


> [!IMPORTANT]  
> La configuración de la Directiva de Lync Server que se aplica en un nivel de Directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más cerca esté la configuración de la Directiva, el objeto al que afecta la Directiva, más influencia tendrá en el objeto.



</div>

Estas opciones incluyen los siguientes tipos de acceso externo:

  - **Habilitar comunicaciones con usuarios federados**   habilite esta funcionalidad si desea admitir el acceso de los usuarios a dominios de socios federados. Esta opción configura la posibilidad de que los usuarios se comuniquen con otros dominios federados SIP, así como proveedores hospedados como Microsoft Office 365. La selección de esta opción le permite seleccionar la opción de permitir la comunicación con dominios XMPP federados.
    
    Como opción, puede activar **Habilitar comunicaciones con socios XMPP federados** si primero activa **Habilitar comunicaciones con usuarios federados**. La federación XMPP es una federación con las organizaciones que usan el protocolo de mensajería extensible y presencia (XMPP).
    
    <div>
    

    > [!NOTE]  
    > Si habilita la Federación de XMPP, también debe seleccionar implementar la <STRONG>Federación XMPP</STRONG> en la sección configuración de grupos de servidores perimetrales del generador de topologías. La configuración para la Federación XMPP implementa un proxy XMPP en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end.

    
    </div>

  - **Habilitar comunicaciones con usuarios**   remotos habilite esta opción si desea que los usuarios de la organización que están fuera del firewall, como los teletrabajadores y los usuarios que viajan, puedan conectarse a Lync Server a través de Internet.

  - **Habilitar comunicaciones con usuarios**   públicos habilite esta opción si desea que los usuarios internos puedan comunicarse con los contactos de proveedores de mi públicos, como los proporcionados por Windows Live,\!Yahoo y America Online (AOL).
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
    > <LI>
    > <P>La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo! Service. La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</P>
    > <LI>
    > <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard. La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> Además de habilitar la compatibilidad de acceso de usuarios externos, también debe configurar directivas para controlar el uso del acceso de usuarios externos en su organización antes de que los usuarios obtengan cualquier tipo de acceso para usuarios externos. Para obtener más información sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A>.



</div>

**Para ver las directivas de acceso externo con los cmdlets de Windows PowerShell**

  - Puede ver las directivas de acceso externo mediante el shell de administración de Lync Server y el cmdlet **Get-CsExternalAccessPolicy** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.
    
    Para ver información sobre todas las directivas de acceso externo, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsExternalAccessPolicy
    
    Este comando devuelve información similar a la siguiente:
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Configurar directivas para controlar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Restablecimiento o eliminación de directivas de acceso de usuarios externos en Lync Server 2013](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

