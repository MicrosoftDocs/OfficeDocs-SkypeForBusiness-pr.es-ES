---
title: 'Lync Server 2013: publicar la base de datos de ubicaciones'
description: 'Lync Server 2013: publicar la base de datos de ubicaciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26892429c7bf5fd9cbfebd0d7ac62482767a541e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565446"
---
# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="6f81a-103">Publicar la base de datos de ubicaciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f81a-103">Publish the location database from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f81a-104">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="6f81a-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="6f81a-105">Las nuevas ubicaciones agregadas a la base de datos de ubicaciones no estarán disponibles para el cliente mientras no se hayan publicado.</span><span class="sxs-lookup"><span data-stu-id="6f81a-105">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="6f81a-106">Para obtener más información, consulte la documentación del shell de administración de Lync Server para el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6f81a-106">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="6f81a-107">**Publish-CsLisConfiguration**</span><span class="sxs-lookup"><span data-stu-id="6f81a-107">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="6f81a-108">Si usa puertas de enlace de número de identificación de ubicación de emergencia (ELIN), cargue también los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="6f81a-108">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="6f81a-109">Probablemente el proveedor de RTC le solicite que use un formato específico para los registros de ELIN.</span><span class="sxs-lookup"><span data-stu-id="6f81a-109">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="6f81a-110">Póngase en contacto con el proveedor de RTC para más información.</span><span class="sxs-lookup"><span data-stu-id="6f81a-110">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="6f81a-111">Puede exportar los registros de la base de datos del servicio de información de ubicación y darles formato según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6f81a-111">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="6f81a-112">Para publicar la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="6f81a-112">To publish the location database</span></span>

  - <span data-ttu-id="6f81a-113">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6f81a-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="6f81a-114">Ejecute el cmdlet siguiente para publicar la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="6f81a-114">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

