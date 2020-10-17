---
title: 'Lync Server 2013: crear una directiva de sitio para chat persistente'
description: 'Lync Server 2013: crear una directiva de sitio para chat persistente.'
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
ms.openlocfilehash: 0f1cfbcffd98e7bdb813a4113345abf17f5b37e5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553226"
---
# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="e5f05-103">Crear una directiva de sitio para chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5f05-103">Create a site policy for Persistent Chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5f05-104">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e5f05-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e5f05-105">Para cada sitio que haya implementado, puede crear una directiva de chat persistente específica del sitio.</span><span class="sxs-lookup"><span data-stu-id="e5f05-105">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>

<span data-ttu-id="e5f05-106">La configuración de la directiva de sitio invalida la directiva global, pero solo en el caso del sitio específico que determina la directiva.</span><span class="sxs-lookup"><span data-stu-id="e5f05-106">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5f05-107">Para configurar y usar el servidor de chat persistente, primero debe usar el generador de topologías para agregar compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="e5f05-107">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="e5f05-108">Para obtener más información, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="e5f05-108">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="e5f05-109">Para configurar las opciones de configuración del servidor de chat persistente, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure persistent chat Server Options Globally or for persistent chat Server Pool in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="e5f05-109">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="e5f05-110">Para crear una directiva de chat persistente para un sitio</span><span class="sxs-lookup"><span data-stu-id="e5f05-110">To create a Persistent Chat policy for a site</span></span>

1.  <span data-ttu-id="e5f05-111">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e5f05-111">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5f05-112">En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="e5f05-112">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="e5f05-113">Para obtener más información acerca de los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e5f05-113">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e5f05-114">En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="e5f05-114">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e5f05-115">También puede usar cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5f05-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e5f05-116">Para obtener más información, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent chat Server by Using Windows PowerShell cmdlets</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="e5f05-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

4.  <span data-ttu-id="e5f05-117">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="e5f05-117">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="e5f05-118">En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="e5f05-118">In **Select a Site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="e5f05-119">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5f05-119">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="e5f05-120">En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="e5f05-120">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
      - <span data-ttu-id="e5f05-121">En **Descripción**, proporcione información detallada sobre la directiva de sitio (por ejemplo, directiva de salón de chat para Redmond).</span><span class="sxs-lookup"><span data-stu-id="e5f05-121">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
      - <span data-ttu-id="e5f05-122">Para controlar el chat persistente para todos los sitios no controlados específicamente mediante una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="e5f05-122">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>

7.  <span data-ttu-id="e5f05-123">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e5f05-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

