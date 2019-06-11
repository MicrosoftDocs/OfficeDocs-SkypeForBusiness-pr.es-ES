---
title: Comprobar la conectividad entre servidores internos y servidores perimetrales
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3868462036312be97484e41c69b51ae022b57c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="89edb-102">Comprobar la conectividad entre servidores internos y servidores perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89edb-102">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89edb-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="89edb-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="89edb-104">En Lync Server 2013, había disponible un asistente de validación independiente para ayudar a validar la conectividad entre los servidores perimetrales y los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="89edb-104">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="89edb-105">En Lync Server 2013 la validación de conectividad se realiza automáticamente cuando se instalan los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="89edb-105">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="89edb-106">Puede validar la replicación de la información de configuración en el extremo ejecutando el cmdlet **Get-CsManagementStoreReplicationStatus** de Windows PowerShell en el equipo interno en el que se encuentra el almacén de administración central (o en cualquier dominio Unido equipo en el que está instalado el componente principal de Lync Server 2013 (OcsCore. msi).</span><span class="sxs-lookup"><span data-stu-id="89edb-106">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="89edb-107">Los resultados iniciales pueden indicar que el estado es "false" en lugar de "true" para la replicación.</span><span class="sxs-lookup"><span data-stu-id="89edb-107">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="89edb-108">En ese caso, ejecuta el cmdlet **Invoke-CsManagementStoreReplication** y deja tiempo para que se complete la replicación antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus** .</span><span class="sxs-lookup"><span data-stu-id="89edb-108">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="89edb-109">Puede comprobar la conectividad de usuarios externos por separado, incluyendo el analizador de conectividad remota de Office Communications Server para comprobar la conectividad de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="89edb-109">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="89edb-110">Para obtener más información, vea [comprobar la conectividad de los usuarios externos en Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span><span class="sxs-lookup"><span data-stu-id="89edb-110">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

