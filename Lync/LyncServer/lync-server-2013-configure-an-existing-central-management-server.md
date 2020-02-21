---
title: 'Lync Server 2013: configurar un servidor de administración central existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c4102008eca37d79d2862a3ede8b1498899511
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a><span data-ttu-id="53171-102">Configurar un servidor de administración central existente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53171-102">Configure an existing Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53171-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="53171-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="53171-104">Si vuelve a usar un servidor de administración central desde una implementación existente de Lync Server 2013, debe ejecutar el procedimiento que se describe a continuación para asegurarse de que el panel de control de Lync Server y Windows PowerShell funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="53171-104">If you reuse a Central Management Server from an existing Lync Server 2013 deployment, you must run the procedure described below to make sure that Lync Server Control Panel and Windows PowerShell function correctly.</span></span>

<div>

## <a name="to-configure-an-existing-central-management-server"></a><span data-ttu-id="53171-105">Para configurar un servidor de administración central existente</span><span class="sxs-lookup"><span data-stu-id="53171-105">To configure an existing Central Management Server</span></span>

1.  <span data-ttu-id="53171-106">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="53171-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="53171-107">Use el cmdlet **Update-CsAdminRole** para actualizar los roles de control de acceso basado en roles (RBAC) almacenados en el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="53171-107">Use the **Update-CsAdminRole** cmdlet to update the role-based access control (RBAC) roles stored in the Central Management Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53171-108">No se espera ningún resultado a no ser que ocurra un error.</span><span class="sxs-lookup"><span data-stu-id="53171-108">No output is expected unless there is an error.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

