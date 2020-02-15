---
title: 'Lync Server 2013: configurar la directiva global para chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4131bca64c8faab6f1b616a02994fbccd9b435dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="4315b-102">Configure la directiva global para chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4315b-102">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4315b-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="4315b-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="4315b-104">Puede usar la directiva global predeterminada solo para habilitar la configuración de chat persistente para todos los usuarios de la implementación.</span><span class="sxs-lookup"><span data-stu-id="4315b-104">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="4315b-105">También puede especificar directivas adicionales para sitios y usuarios para controlar si el chat persistente está habilitado o deshabilitado para determinados usuarios y sitios.</span><span class="sxs-lookup"><span data-stu-id="4315b-105">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="4315b-106">No puede eliminar la directiva global.</span><span class="sxs-lookup"><span data-stu-id="4315b-106">You cannot delete the global policy.</span></span> <span data-ttu-id="4315b-107">Si intenta eliminarla, la configuración se restablecerá con los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="4315b-107">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4315b-108">Para configurar y usar el servidor de chat persistente, primero debe usar el generador de topologías para agregar compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="4315b-108">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="4315b-109">Para obtener más información, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="4315b-109">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="4315b-110">Para configurar las opciones de configuración del servidor de chat persistente, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure persistent chat Server Options Globally or for persistent chat Server Pool in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="4315b-110">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="4315b-111">Para configurar la directiva global para chat persistente</span><span class="sxs-lookup"><span data-stu-id="4315b-111">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="4315b-112">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4315b-112">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4315b-113">En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="4315b-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="4315b-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="4315b-114">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4315b-115">También puede usar cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4315b-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4315b-116">Para obtener más información, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent chat Server by Using Windows PowerShell cmdlets</A> in Deployment Documentation.</span><span class="sxs-lookup"><span data-stu-id="4315b-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="4315b-117">En el panel de control de Lync Server, haga clic en **chat persistente**y, a continuación, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="4315b-117">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="4315b-118">Haga clic en **Global** en la lista de directivas, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="4315b-118">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4315b-119">In **Editar directiva de chat persistente - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4315b-119">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="4315b-120">En \*\*Nombre \*\*, especifique un nombre nuevo para la directiva global, si no desea usar el nombre predeterminado (Global).</span><span class="sxs-lookup"><span data-stu-id="4315b-120">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="4315b-121">En **Descripción**, proporcione información detallada sobre la función de la Directiva de usuario (por ejemplo, directiva global para centralSiteName).</span><span class="sxs-lookup"><span data-stu-id="4315b-121">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="4315b-122">Para controlar el chat persistente para todos los sitios y usuarios que no se controlan específicamente mediante una directiva de sitio o de usuario, Active o desactive la casilla **Habilitar chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="4315b-122">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="4315b-123">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4315b-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

