---
title: 'Lync Server 2013: Crear una directiva de usuario para chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a9bd88dd84b8b5056adf19ebc098daac54cb005
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="f3cd7-102">Crear una directiva de usuario para chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3cd7-102">Create a user policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3cd7-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f3cd7-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f3cd7-104">En el panel de control de Lync Server, se definen directivas de usuario que se pueden asignar a los usuarios en **los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-104">In the Lync Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>

<span data-ttu-id="f3cd7-105">La directiva de usuario reemplaza la directiva global y las directivas de sitio, pero solo para los usuarios específicos que tienen asignada dicha directiva.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-105">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3cd7-106">Para configurar y usar el servidor de chat persistente, primero debe usar topología Builder para agregar la compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="f3cd7-107">Para obtener más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a su implementación en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="f3cd7-108">Para configurar las opciones de configuración del servidor de chat persistentes, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurar las opciones del servidor de chat persistente globalmente o para el grupo de servidores de chat persistente en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="f3cd7-109">Para crear una directiva de usuario para el chat persistente</span><span class="sxs-lookup"><span data-stu-id="f3cd7-109">To create a user policy for Persistent Chat</span></span>

1.  <span data-ttu-id="f3cd7-110">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3cd7-111">En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="f3cd7-112">Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f3cd7-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f3cd7-113">También puede usar los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-113">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="f3cd7-114">Para ver la <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuración del servidor de chat persistente, use los cmdlets de Windows PowerShell</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-114">See <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="f3cd7-115">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-115">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="f3cd7-116">Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="f3cd7-117">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3cd7-117">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="f3cd7-118">En **Nombre**, especifique un nombre para la nueva directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-118">In **Name**, specify a name for the new user policy.</span></span>
    
      - <span data-ttu-id="f3cd7-119">En **Descripción**, proporcione detalles sobre qué es la Directiva de usuario (por ejemplo, la Directiva de chat persistente para un usuario específico).</span><span class="sxs-lookup"><span data-stu-id="f3cd7-119">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
      - <span data-ttu-id="f3cd7-120">Para controlar el chat persistente para todos los usuarios que no se controlan específicamente mediante una directiva de usuario, Active o desactive la casilla de verificación **Habilitar conversación persistente** .</span><span class="sxs-lookup"><span data-stu-id="f3cd7-120">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="f3cd7-121">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f3cd7-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

