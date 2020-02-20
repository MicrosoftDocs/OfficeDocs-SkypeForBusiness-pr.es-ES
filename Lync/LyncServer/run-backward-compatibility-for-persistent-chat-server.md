---
title: Ejecutar compatibilidad con versiones anteriores para el servidor de chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad689dace5e302cad8d41dff77dd575637b99ae6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>Ejecutar compatibilidad con versiones anteriores para el servidor de chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

El punto de conexión del servidor de chat persistente de Lync Server 2013 proporciona una forma de crear una dirección URL sencilla que apunta a un grupo de servidores de chat persistente. Esto es útil para los clientes heredados (servidor de chat en grupo de Microsoft Office Communications Server 2007 R2 o Lync Server 2010, chat en grupo), ya que los usuarios pueden escribir una dirección URL sencilla en la configuración manual al intentar apuntar el cliente heredado a un equipo que ejecute Lync 2013. Chat persistente. El chat persistente no usa este extremo y solo es necesario para los clientes heredados. Esto es útil para el período intermedio en el que se pueden migrar los salones, pero los clientes de Lync 2013 no se han implementado en toda la organización. Los usuarios que ejecutan Lync 2010 Group chat (Client) pueden seguir conectándose al servidor back-end del servidor de chat persistente.

No es necesario crear varios extremos del servidor de chat persistente; solo necesita uno para cada grupo de servidores de chat persistente. Los administradores pueden crear varios extremos (uno por cada grupo), pero los clientes heredados solo pueden configurarse para conectarse a un grupo de servidores a la vez. En el escenario habitual o estándar, la implementación heredada es un grupo solamente. Una nueva implementación suele migrar ese grupo a un nuevo Lync Server 2013 y puede agregar nuevos grupos de servidores de chat persistente adicionales.

Este escenario estándar generalmente sigue este patrón:

  - Los usuarios se administran con un servidor de Lync Server 2010, un grupo de servidores de chat en grupo y los clientes de chat de grupo de Lync 2010 se conectan a ese grupo\<de\>servidores mediante algún usuario conocido (SIP predeterminado: ocschat@ nombredominio. com o uno similar). Los usuarios son servicios de dominio de Active Directory habilitados para SIP y el servicio de búsqueda se registra con ellos para recibir solicitudes entrantes.

  - Posteriormente, se instala un servidor de chat persistente de Lync Server 2013 y un grupo de servidores de chat persistente.

  - Durante un momento en el que los usuarios suelen estar desconectados (por ejemplo, un fin de semana):
    
      - Desactive Lync Server 2010, chat en grupo.
    
      - Migre datos del grupo de servidores de chats de Lync Server 2010, al grupo de servidores de chat persistente de Lync Server 2013.
    
      - Elimine el usuario conocido de los servicios de dominio de Active Directory.
    
      - Cree un nuevo *extremo heredado* con el mismo URI de SIP que el usuario conocido eliminado previamente.
    
      - Inicie los servidores de chat persistente de Lync Server 2013.

  - Los usuarios vuelven a iniciar sesión con su chat en grupo de Lync 2010 (cliente) y se conectan a sus datos sin necesidad de cambiar ninguna configuración.

  - En un momento posterior, puede retirar el chat en grupo de Lync Server 2010. A continuación, puede implementar Lync Server 2013, servidor de chat persistente e instalar nuevos grupos de servidores de chat persistente de Lync Server 2013.

Para obtener información detallada sobre cómo migrar desde Lync Server 2010, chat en grupo a Lync Server 2013, servidor de chat persistente, vea [Migration from Lync server 2010, Group chat u Office Communications server 2007 R2 Group chat a Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Para ejecutar la compatibilidad con versiones anteriores (para crear un extremo de servidor de chat persistente que apunte a un grupo de servidores de chat persistente, que pueden usar los clientes del grupo de chat de grupo heredado):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

A continuación, configure los clientes de chat persistentes para usar esa dirección SIP como su objeto de contacto. La dirección SIP se crea con el cmdlet **New-CsPersistentChatEndpoint** para un grupo de servidores de chat persistente específico.

Para agregar el extremo del servidor de chat persistente mediante la interfaz de línea de comandos de Windows PowerShell, considere el siguiente ejemplo. En este caso, va a configurar el objeto de contacto para que se denomine "persistentchat" en la topología "constoso.com" donde el nombre de dominio completo (FQDN) del grupo de servidores es "pcpool.contoso.com":

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>Vea también


[Migración desde Lync Server 2010, chat grupal o grupo de Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

