---
title: Configuración de los clientes para la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84205c75da4c52aa6c90f3a501c74dd849933d9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a><span data-ttu-id="19d02-102">Configuración de los clientes para la migración</span><span class="sxs-lookup"><span data-stu-id="19d02-102">Configure clients for migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19d02-103">_**Última modificación del tema:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="19d02-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="19d02-104">Este tema contiene los pasos de implementación de cliente recomendados que debe realizar antes de migrar a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="19d02-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="19d02-105">Estos cambios de configuración deberían hacerse en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="19d02-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="19d02-106">Es muy importante que realice estos pasos antes de migrar.</span><span class="sxs-lookup"><span data-stu-id="19d02-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="19d02-107">Para obtener más información, consulte [planificación de clientes y dispositivos en Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="19d02-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="19d02-108">Para configurar clientes antes de la migración</span><span class="sxs-lookup"><span data-stu-id="19d02-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="19d02-109">Implemente las actualizaciones de servidor, cliente y dispositivo de Office Communications Server 2007 R2 más recientes (hotfixes):</span><span class="sxs-lookup"><span data-stu-id="19d02-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="19d02-110">Aplicar las actualizaciones de Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="19d02-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="19d02-111">Descripción del paquete de actualización acumulativa para Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="19d02-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="19d02-112">Obtener actualizaciones de software para dispositivos</span><span class="sxs-lookup"><span data-stu-id="19d02-112">Obtaining Software Updates for Devices</span></span>](http://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="19d02-113">En Office Communications Server 2007 R2, use el filtrado de versiones de cliente para permitir solo a los clientes de Office Communications Server 2007 R2 que tengan instaladas las actualizaciones más recientes para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="19d02-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="19d02-114">En Office Communications Server 2007 R2, use el filtrado de versiones de cliente para bloquear el inicio de sesión de clientes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="19d02-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="19d02-115">Siga los pasos descritos en configurar el filtrado de [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) versión de **cliente** en para agregar los filtros de versión que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="19d02-115">Follow the steps described in **Configuring Client Version Filtering** at [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="19d02-116">Para cada filtro de versión, asigne el **bloque**de acción.</span><span class="sxs-lookup"><span data-stu-id="19d02-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="19d02-117">Cliente</span><span class="sxs-lookup"><span data-stu-id="19d02-117">Client</span></span></th>
    <th><span data-ttu-id="19d02-118">Encabezado de agente de usuario</span><span class="sxs-lookup"><span data-stu-id="19d02-118">User agent header</span></span></th>
    <th><span data-ttu-id="19d02-119">Versión</span><span class="sxs-lookup"><span data-stu-id="19d02-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="19d02-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="19d02-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="19d02-121">OC</span><span class="sxs-lookup"><span data-stu-id="19d02-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="19d02-122">15.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="19d02-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="19d02-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="19d02-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="19d02-124">CWA</span><span class="sxs-lookup"><span data-stu-id="19d02-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="19d02-125">5.*..* \*</span><span class="sxs-lookup"><span data-stu-id="19d02-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="19d02-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="19d02-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="19d02-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="19d02-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="19d02-128">4.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="19d02-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

