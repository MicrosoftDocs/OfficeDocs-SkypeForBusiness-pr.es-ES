---
title: Comprobar la conectividad entre servidores internos y servidores perimetrales
description: Compruebe la conectividad entre servidores internos y servidores perimetrales.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f86f87428d7eaf91b8f70422cfee712584252fad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547136"
---
# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="3aaa5-103">Comprobar la conectividad entre servidores internos y servidores perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3aaa5-103">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3aaa5-104">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="3aaa5-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="3aaa5-105">En Lync Server 2013, había disponible un asistente de validación independiente para ayudar a validar la conectividad entre los servidores perimetrales y los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="3aaa5-105">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="3aaa5-106">En Lync Server 2013 la validación de la conectividad se realiza automáticamente al instalar los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="3aaa5-106">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="3aaa5-107">Para validar la replicación de la información de configuración en el servidor perimetral, ejecute el cmdlet **Get-CsManagementStoreReplicationStatus** de Windows PowerShell en el equipo interno en el que se encuentra el almacén de administración central (o en cualquier equipo unido al dominio en el que se hayan instalado los componentes principales de Lync Server 2013 (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="3aaa5-107">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="3aaa5-108">Los resultados iniciales pueden indicar el estado como "False" en lugar de "True" para la replicación.</span><span class="sxs-lookup"><span data-stu-id="3aaa5-108">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="3aaa5-109">Si así es, ejecute el cmdlet **Invoke-CsManagementStoreReplication** y deje que la replicación termine antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus**.</span><span class="sxs-lookup"><span data-stu-id="3aaa5-109">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="3aaa5-110">La conectividad de los usuarios externos se puede comprobar por separado, además de usar el Analizador de conectividad remota de Office Communications Server para comprobar la conectividad remota de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3aaa5-110">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="3aaa5-111">Para obtener más información, consulte [Verify Connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span><span class="sxs-lookup"><span data-stu-id="3aaa5-111">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

