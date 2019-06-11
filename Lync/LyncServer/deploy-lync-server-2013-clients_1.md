---
title: Implementar clientes de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 659ec7be51358e73824c322461a3e27a163dc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="ffe32-102">Implementar clientes de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffe32-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffe32-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ffe32-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ffe32-104">Después de migrar usuarios a Lync Server 2013, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ffe32-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="ffe32-105">Use el filtro de versión del cliente en el nuevo servidor de Lync Server 2013 para permitir que los clientes con las actualizaciones más recientes estén instalados para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="ffe32-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="ffe32-106">Si es necesario, establezca la configuración de directiva de grupo que se requiere para el inicio del cliente.</span><span class="sxs-lookup"><span data-stu-id="ffe32-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="ffe32-107">Para obtener información detallada, consulte [configuración de directivas de inicio de cliente en Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="ffe32-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="ffe32-108">La configuración de esta configuración solo es necesaria si desea cambiar las directivas de inicio del cliente existentes o si desea establecer nuevas directivas de inicio del cliente.</span><span class="sxs-lookup"><span data-stu-id="ffe32-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="ffe32-109">Si no tiene previsto configurar directivas de inicio del cliente o desea que las directivas de inicio del cliente heredadas permanezcan efectivas, no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="ffe32-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="ffe32-110">Configure otras directivas de usuario y cliente para usuarios específicos o grupos de usuarios mediante el panel de control de Lync Server 2013, el shell de administración de Lync Server 2013 o ambos.</span><span class="sxs-lookup"><span data-stu-id="ffe32-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="ffe32-111">Para obtener más información, vea [configuración nueva y modificada de Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="ffe32-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="ffe32-112">Implemente la versión más reciente de los clientes de Lync Server 2013 junto con las actualizaciones acumulativas más recientes.</span><span class="sxs-lookup"><span data-stu-id="ffe32-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="ffe32-113">Para obtener más información, vea [implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="ffe32-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="ffe32-114">Faculta Si su organización requiere Lync Server 2013 modo de privacidad de presencia mejorado, una vez completada la migración, defina una regla de directiva de versión de cliente para evitar que las versiones de cliente anteriores inicien sesión.</span><span class="sxs-lookup"><span data-stu-id="ffe32-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="ffe32-115">A continuación, habilitar el modo de privacidad de presencia mejorado.</span><span class="sxs-lookup"><span data-stu-id="ffe32-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ffe32-116">No habilite el modo de privacidad de presencia mejorada de Lync 2013 hasta que todos los usuarios de un grupo de servidores determinado tengan instaladas las versiones más recientes de los clientes.</span><span class="sxs-lookup"><span data-stu-id="ffe32-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

