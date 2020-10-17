---
title: 'Lync Server 2013: configurar un servicio de información de ubicación secundaria'
description: 'Lync Server 2013: configurar un servicio de información de ubicación secundaria.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1721299a0c70535dff8dd05e31712ee6a8d93691
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551716"
---
# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="a9aae-103">Configurar un servicio de información de ubicación secundaria en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9aae-103">Configure a secondary Location Information service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9aae-104">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="a9aae-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="a9aae-105">Lync Server 2013 proporciona una interfaz de servicio Web que puede usar para apuntar el servicio de información de ubicaciones a una base de datos de origen de ubicación secundario (SLS).</span><span class="sxs-lookup"><span data-stu-id="a9aae-105">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="a9aae-106">La interfaz de servicio Web que se conecta a la base de datos de SLS debe cumplir con el servicio de información de ubicación WSDL.</span><span class="sxs-lookup"><span data-stu-id="a9aae-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="a9aae-107">Si se configuran una base de datos de ubicación y una base de datos de ubicación secundaria, el servicio de información de ubicación primero consulta la base de datos de ubicaciones y, si no se encuentra ninguna coincidencia, envía la solicitud de ubicación desde el cliente a la base de datos de SLS.</span><span class="sxs-lookup"><span data-stu-id="a9aae-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="a9aae-108">Si la ubicación existe en SLS, el servicio de información de ubicación entonces devuelve la ubicación de vuelta al cliente.</span><span class="sxs-lookup"><span data-stu-id="a9aae-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="a9aae-109">Para obtener más información, consulte la documentación del shell de administración de Lync Server para el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a9aae-109">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="a9aae-110">**Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="a9aae-110">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="a9aae-111">Para configurar la base de datos de ubicación secundaria</span><span class="sxs-lookup"><span data-stu-id="a9aae-111">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="a9aae-112">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a9aae-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a9aae-113">Ejecute el siguiente cmdlet para configurar la URL para la ubicación de la base de datos de ubicación secundaria.</span><span class="sxs-lookup"><span data-stu-id="a9aae-113">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

