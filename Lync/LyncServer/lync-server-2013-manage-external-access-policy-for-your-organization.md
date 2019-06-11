---
title: 'Lync Server 2013: Administrar la directiva de acceso de la organización'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a08e096d517d2ac53866df763ab2f553480da5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>Administrar la directiva de acceso de la organización en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

Después de implementar uno o varios servidores perimetrales, debe habilitar los tipos de acceso externo que será compatible con su organización.

De forma predeterminada, no hay ninguna directiva configurada para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos, acceso de usuarios federados, incluso si ya ha habilitado la compatibilidad de acceso de usuarios externos para su organización. Para controlar el uso del acceso de usuarios externos, debe configurar una o más directivas, especificando el tipo de acceso de usuarios externos admitido para cada Directiva. Los siguientes ámbitos de directivas están disponibles para la creación y la configuración. De forma predeterminada, se crea la directiva global, pero no se puede eliminar.

  - **Directiva global se**   crea la directiva global al implementar los servidores perimetrales. De forma predeterminada, no hay ninguna opción de acceso de usuario externo habilitada en la directiva global. Para admitir el acceso de usuarios externos en el nivel global, configure la directiva global para que admita uno o varios tipos de opciones de acceso de usuarios externos. La directiva global se aplica a todos los usuarios de la organización, pero las directivas del sitio y las directivas de usuario invalidan la directiva global. Si elimina la directiva global, no la quitará. En su lugar, lo restablecerá a la configuración predeterminada.

  - **Directiva de sitio**   puede crear y configurar una o varias directivas de sitio para limitar la compatibilidad con el acceso de usuarios externos a sitios específicos. La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio. Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos para un sitio específico. De forma predeterminada, se aplica una directiva de sitio a todos los usuarios de ese sitio, pero puede asignar una directiva de usuario a un usuario para que anule la configuración de directiva de sitio.

  - **Directiva de usuario**   puede crear y configurar una o más directivas de usuario para limitar la compatibilidad del acceso de usuarios remotos a usuarios específicos. La configuración de la Directiva de usuario reemplaza la directiva global y la de sitio, pero solo para los usuarios específicos a los que se asigna la Directiva de usuario. Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global y la Directiva de sitio, puede especificar una directiva de usuario que deshabilite el acceso de usuarios remotos y, a continuación, asignar esa Directiva de usuario a usuarios específicos. Si crea una directiva de usuario, debe aplicarla a uno o más usuarios para que tenga efecto.

<div>


> [!IMPORTANT]  
> La configuración de directiva de Lync Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.



</div>

Estas opciones incluyen los siguientes tipos de acceso externo:

  - **Habilitar comunicaciones con usuarios**   federados: habilite esta opción si desea permitir el acceso de usuarios a dominios federados de socios federados. Esta opción configura la posibilidad de que los usuarios se comuniquen con otros dominios federados SIP, así como con proveedores hospedados como Microsoft Office 365. Si selecciona esta opción, podrá seleccionar la opción para permitir la comunicación con dominios federados de XMPP.
    
    Como opción, puede seleccionar **Habilitar comunicaciones con los socios de XMPP federados** si, en primer lugar, selecciona **habilitar las comunicaciones con usuarios federados**. La Federación XMPP es una federación con organizaciones que usan el protocolo de presencia y mensajería extensible (XMPP).
    
    <div>
    

    > [!NOTE]  
    > Si habilita la Federación XMPP, también debe seleccionar implementar la <STRONG>Federación XMPP</STRONG> en la sección configuración de grupos perimetrales del generador de topologías. La configuración para la Federación XMPP implementa un proxy XMPP en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end.

    
    </div>

  - **Habilitar las comunicaciones con usuarios**   remotos habilite esta opción si desea que los usuarios de su organización que estén fuera del firewall, como los teletrabajadores y los usuarios que viajan, puedan conectarse a Lync Server a través de Internet.

  - **Habilitar las comunicaciones con usuarios**   públicos habilite esta opción si quiere que los usuarios internos puedan comunicarse con los contactos del proveedor de mensajería instantánea pública, como los que proporcionan Windows Live\!, Yahoo y America Online (AOL).
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de fin de vida de junio de 2014 para AOL y Yahoo! ha sido anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
    > <LI>
    > <P>El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo! Mensajería. La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</P>
    > <LI>
    > <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard. La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> Además de habilitar la compatibilidad de acceso de usuarios externos, también debe configurar directivas para controlar el uso del acceso de usuarios externos de su organización antes de que los usuarios tengan acceso a cualquier tipo de acceso de usuario externo. Para obtener detalles sobre la creación, la configuración y la aplicación de directivas para el acceso de usuarios externos, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A>.



</div>

**Para ver las directivas de acceso externas mediante cmdlets de Windows PowerShell**

  - Puede ver las directivas de acceso externas mediante el shell de administración de Lync Server y el cmdlet **Get-CsExternalAccessPolicy** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.
    
    Para ver información sobre todas las directivas de acceso externo, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsExternalAccessPolicy
    
    Este comando devolverá información similar a la siguiente:
    
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

  - [Configurar directivas para el control del acceso de usuarios remotos en Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Restablecer o eliminar las directivas de acceso de usuarios externos en Lync Server 2013](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

