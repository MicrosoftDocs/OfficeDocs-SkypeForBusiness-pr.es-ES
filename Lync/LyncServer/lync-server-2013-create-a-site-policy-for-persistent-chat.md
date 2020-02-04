---
title: 'Lync Server 2013: Crear una directiva de sitio para chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4feb77aa99e1fe3018a469e61e9688a87cf81760
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="6f705-102">Crear una directiva de sitio para chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f705-102">Create a site policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f705-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="6f705-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="6f705-104">Para cada sitio que haya implementado, puede crear una directiva de chat persistente específica de un sitio.</span><span class="sxs-lookup"><span data-stu-id="6f705-104">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>

<span data-ttu-id="6f705-105">La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="6f705-105">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6f705-106">Para configurar y usar el servidor de chat persistente, primero debe usar topología Builder para agregar la compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="6f705-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="6f705-107">Para obtener más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a su implementación en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="6f705-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="6f705-108">Para configurar las opciones de configuración del servidor de chat persistentes, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurar las opciones del servidor de chat persistente globalmente o para el grupo de servidores de chat persistente en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="6f705-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="6f705-109">Para crear una directiva de chat persistente para un sitio</span><span class="sxs-lookup"><span data-stu-id="6f705-109">To create a Persistent Chat policy for a site</span></span>

1.  <span data-ttu-id="6f705-110">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6f705-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6f705-111">En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="6f705-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="6f705-112">Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6f705-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6f705-113">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="6f705-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6f705-114">También puede usar los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f705-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="6f705-115">Para obtener más información, vea <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuración del servidor de chat persistente mediante cmdlets de Windows PowerShell</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="6f705-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

4.  <span data-ttu-id="6f705-116">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="6f705-116">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="6f705-117">En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="6f705-117">In **Select a Site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="6f705-118">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f705-118">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="6f705-119">En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="6f705-119">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
      - <span data-ttu-id="6f705-120">En **Descripción**, dé detalles sobre lo que es la directiva del sitio (por ejemplo, directiva de salón de chat de Redmond).</span><span class="sxs-lookup"><span data-stu-id="6f705-120">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
      - <span data-ttu-id="6f705-121">Para controlar el chat persistente para todos los sitios no controlados específicamente con una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="6f705-121">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>

7.  <span data-ttu-id="6f705-122">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6f705-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

