---
title: Ejecutar compatibilidad con versiones anteriores para el servidor de chat persistente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c96b2ad99ce403df32cc224d854c34160bd6c613
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518097"
---
# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="983c3-102">Ejecutar compatibilidad con versiones anteriores para el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="983c3-102">Run backward compatibility for Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="983c3-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="983c3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="983c3-104">El punto de conexión del servidor de chat persistente de Lync Server 2013 proporciona una forma de crear una dirección URL sencilla que apunta a un grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="983c3-104">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="983c3-105">Esto es útil para los clientes heredados (servidor de chat en grupo de Microsoft Office Communications Server 2007 R2 o Lync Server 2010, chat en grupo), ya que los usuarios pueden escribir una dirección URL sencilla en la configuración manual al intentar apuntar el cliente heredado a un equipo que ejecute Lync 2013, chat persistente.</span><span class="sxs-lookup"><span data-stu-id="983c3-105">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="983c3-106">El chat persistente no usa este extremo y solo es necesario para los clientes heredados.</span><span class="sxs-lookup"><span data-stu-id="983c3-106">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="983c3-107">Esto es útil para el período intermedio en el que se pueden migrar los salones, pero los clientes de Lync 2013 no se han implementado en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="983c3-107">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="983c3-108">Los usuarios que ejecutan Lync 2010 Group chat (Client) pueden seguir conectándose al servidor back-end del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="983c3-108">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="983c3-109">No es necesario crear varios extremos del servidor de chat persistente; solo necesita uno para cada grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="983c3-109">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="983c3-110">Los administradores pueden crear varios extremos (uno por cada grupo), pero los clientes heredados solo pueden configurarse para conectarse a un grupo de servidores a la vez.</span><span class="sxs-lookup"><span data-stu-id="983c3-110">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="983c3-111">En el escenario habitual o estándar, la implementación heredada es un grupo solamente.</span><span class="sxs-lookup"><span data-stu-id="983c3-111">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="983c3-112">Una nueva implementación suele migrar ese grupo a un nuevo Lync Server 2013 y puede agregar nuevos grupos de servidores de chat persistente adicionales.</span><span class="sxs-lookup"><span data-stu-id="983c3-112">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="983c3-113">Este escenario estándar generalmente sigue este patrón:</span><span class="sxs-lookup"><span data-stu-id="983c3-113">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="983c3-114">Los usuarios se administran con un servidor de Lync Server 2010, un grupo de servidores de chat de grupo y los clientes de chat de grupo de Lync 2010 se conectan a ese grupo de servidores mediante algún usuario conocido (SIP predeterminado: ocschat@ \<domainName\> . com o uno similar).</span><span class="sxs-lookup"><span data-stu-id="983c3-114">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="983c3-115">Los usuarios son servicios de dominio de Active Directory habilitados para SIP y el servicio de búsqueda se registra con ellos para recibir solicitudes entrantes.</span><span class="sxs-lookup"><span data-stu-id="983c3-115">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="983c3-116">Posteriormente, se instala un servidor de chat persistente de Lync Server 2013 y un grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="983c3-116">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="983c3-117">Durante un momento en el que los usuarios suelen estar desconectados (por ejemplo, un fin de semana):</span><span class="sxs-lookup"><span data-stu-id="983c3-117">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="983c3-118">Desactive Lync Server 2010, chat en grupo.</span><span class="sxs-lookup"><span data-stu-id="983c3-118">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="983c3-119">Migre datos del grupo de servidores de chats de Lync Server 2010, al grupo de servidores de chat persistente de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="983c3-119">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="983c3-120">Elimine el usuario conocido de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="983c3-120">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="983c3-121">Cree un nuevo *extremo heredado* con el mismo URI de SIP que el usuario conocido eliminado previamente.</span><span class="sxs-lookup"><span data-stu-id="983c3-121">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="983c3-122">Inicie los servidores de chat persistente de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="983c3-122">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="983c3-123">Los usuarios vuelven a iniciar sesión con su chat en grupo de Lync 2010 (cliente) y se conectan a sus datos sin necesidad de cambiar ninguna configuración.</span><span class="sxs-lookup"><span data-stu-id="983c3-123">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="983c3-124">En un momento posterior, puede retirar el chat en grupo de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="983c3-124">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="983c3-125">A continuación, puede implementar Lync Server 2013, servidor de chat persistente e instalar nuevos grupos de servidores de chat persistente de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="983c3-125">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="983c3-126">Para obtener información detallada sobre cómo migrar desde Lync Server 2010, chat en grupo a Lync Server 2013, servidor de chat persistente, vea [Migration from Lync server 2010, Group chat u Office Communications server 2007 R2 Group chat a Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="983c3-126">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="983c3-127">Para ejecutar la compatibilidad con versiones anteriores (para crear un extremo de servidor de chat persistente que apunte a un grupo de servidores de chat persistente, que pueden usar los clientes del grupo de chat de grupo heredado):</span><span class="sxs-lookup"><span data-stu-id="983c3-127">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="983c3-128">A continuación, configure los clientes de chat persistentes para usar esa dirección SIP como su objeto de contacto.</span><span class="sxs-lookup"><span data-stu-id="983c3-128">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="983c3-129">La dirección SIP se crea con el cmdlet **New-CsPersistentChatEndpoint** para un grupo de servidores de chat persistente específico.</span><span class="sxs-lookup"><span data-stu-id="983c3-129">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="983c3-130">Para agregar el extremo del servidor de chat persistente mediante la interfaz de línea de comandos de Windows PowerShell, considere el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="983c3-130">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="983c3-131">En este caso, va a configurar el objeto de contacto para que se denomine "persistentchat" en la topología "constoso.com" donde el nombre de dominio completo (FQDN) del grupo de servidores es "pcpool.contoso.com":</span><span class="sxs-lookup"><span data-stu-id="983c3-131">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="983c3-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="983c3-132">See Also</span></span>


[<span data-ttu-id="983c3-133">Migración desde Lync Server 2010, chat grupal o grupo de Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="983c3-133">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

