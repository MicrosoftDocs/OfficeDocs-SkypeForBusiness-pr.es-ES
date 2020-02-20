---
title: 'Lync Server 2013: seleccionar el servidor de administración central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Select the Central Management Server
ms:assetid: 1ca6b7d0-125c-4727-aac4-2d683d23394d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204726(v=OCS.15)
ms:contentKeyID: 48183561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 944730f811bf4196234c1a0cd8619ad30e976251
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="select-the-central-management-server-in-lync-server-2013"></a><span data-ttu-id="4cd3f-102">Seleccione el servidor de administración central en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cd3f-102">Select the Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cd3f-103">_**Última modificación del tema:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="4cd3f-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="4cd3f-104">Para poder definir y configurar la topología, primero debe definir la ubicación para instalar el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="4cd3f-104">Before you can define and configure your topology, you must first define the location to install the Central Management Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4cd3f-105">Esto no tendrá efecto hasta que haya publicado una topología en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="4cd3f-105">This will not take effect until you have published a topology in Topology Builder.</span></span> <span data-ttu-id="4cd3f-106">Para establecer el servidor de administración central antes de que se cree y publique la topología, ejecute <STRONG>set-CSConfigurationStoreLocation</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4cd3f-106">To set the Central Management Server before the topology is created and published, run <STRONG>Set-CSConfigurationStoreLocation</STRONG>.</span></span>



</div>

<div>

## <a name="to-select-the-central-management-server"></a><span data-ttu-id="4cd3f-107">Para seleccionar el servidor de administración central</span><span class="sxs-lookup"><span data-stu-id="4cd3f-107">To select the Central Management Server</span></span>

1.  <span data-ttu-id="4cd3f-108">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4cd3f-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4cd3f-109">Haga clic con el botón secundario en el nodo Lync Server 2013 y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4cd3f-109">Right-click the Lync Server 2013 node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4cd3f-110">En el panel servidor de administración central, seleccione el servidor front-end en el que se va a instalar el servidor de administración central y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4cd3f-110">In the Central Management Server pane, select the Front End Server to install the Central Management Server on and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

