---
title: Ejecutar compatibilidad con versiones anteriores para servidor de chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b512d18449c881efd856674477a727cec137b64c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>Ejecutar compatibilidad con versiones anteriores para servidor de chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Lync Server 2013, extremo del servidor de chat persistente proporciona una forma de crear una dirección URL simple que apunta a un grupo de servidores de chat persistente. Esto es útil para clientes heredados (servidor de chat grupal de Microsoft Office Communications Server 2007 R2 o Lync Server 2010, chat grupal) porque los usuarios pueden escribir una dirección URL simple en la configuración manual al intentar apuntar el cliente heredado a un equipo que ejecute Lync 2013. Chat persistente. Este punto de conexión no lo usa el chat persistente y es necesario solo para los clientes heredados. Esto es útil para el período provisional en el que se pueden migrar las salas, pero los clientes de Lync 2013 no se han implementado en toda la organización. Los usuarios que ejecutan Lync 2010 chat de grupo pueden seguir conectándose con el servidor de servicios de chat persistente.

No es necesario crear varios puntos de conexión del servidor de chat persistente; solo necesita una por cada grupo de servidores de chat persistente. Los administradores pueden crear varios puntos de conexión (uno por grupo), pero los clientes heredados se pueden configurar para que solo se conecten a un grupo a la vez. En el escenario normal o estándar, la implementación heredada solo es de un grupo. Generalmente, una nueva implementación migra ese grupo a un nuevo Lync Server 2013 y puede agregar nuevos grupos de servidores de chat persistentes adicionales.

Este escenario estándar generalmente sigue este patrón:

  - Los usuarios se administran con un servidor de Lync Server 2010, un grupo de chats grupales y los clientes de chat grupal de Lync 2010 se conectan a ese grupo mediante algún usuario\<conocido\>(SIP predeterminado: ocschat @ domainname. com o uno similar). Los usuarios son servicios de dominio de Active Directory habilitados para SIP y el servicio de búsqueda se registra con ellos para recibir solicitudes entrantes.

  - Después, instale un servidor de chat persistente de Lync Server 2013 y un grupo de servidores de chat persistente.

  - En el caso de que los usuarios estén generalmente desconectados (por ejemplo, un fin de semana):
    
      - Desactive Lync Server 2010, conversación grupal.
    
      - Migre los datos desde el servidor de Lync 2010, el grupo de chats grupales al grupo de servidores de chat persistente de Lync Server 2013.
    
      - Elimine el usuario conocido de los servicios de dominio de Active Directory.
    
      - Cree un nuevo *extremo heredado* con el mismo URI de SIP que el usuario conocido previamente eliminado.
    
      - Inicie Lync Server 2013, servidores de chat persistentes.

  - Los usuarios inician sesión de nuevo con su chat de grupo de Lync 2010 (cliente) y se conectan a sus datos sin necesidad de cambiar ninguna configuración.

  - En un momento posterior, puede dar de baja el Lync Server 2010, una conversación grupal. Después, puede implementar Lync Server 2013, servidor de chat persistente e instalar nuevos grupos de servidores de chat persistentes de Lync Server 2013.

Para obtener más información sobre cómo migrar desde Lync Server 2010, chatear en grupo a Lync Server 2013, servidor de chat persistente, consulte [migración desde Lync server 2010, chat grupal u Office Communications server 2007 R2 conversación grupal a Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Para ejecutar la compatibilidad con versiones anteriores (para crear un extremo de servidor de chat persistente que apunta a un grupo de servidores de chat persistente, que pueden usar los clientes heredados del grupo de chats):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

A continuación, configure los clientes de chat persistentes para que usen esa dirección SIP como su objeto de contacto. La dirección SIP se crea con el cmdlet **New-CsPersistentChatEndpoint** para un grupo de servidores de chat persistente específico.

Para agregar el extremo del servidor de chat persistente con la interfaz de línea de comandos de Windows PowerShell, considere el siguiente ejemplo. En este caso, está configurando el objeto de contacto para que se llame "persistentchat" en la topología "contoso.com", donde el nombre de dominio completo (FQDN) es "pcpool.contoso.com":

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>Vea también


[Migración del chat de grupo de Lync Server 2010 o el chat de grupo de Office Communications Server 2007 R2 al servidor de chat persistente de Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

