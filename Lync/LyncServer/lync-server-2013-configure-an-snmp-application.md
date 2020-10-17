---
title: 'Lync Server 2013: configurar una aplicación SNMP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48ef29fdf87dd25365a5aae69cb4c8115e410025
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522997"
---
# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="3b814-102">Configurar una aplicación SNMP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b814-102">Configure an SNMP application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b814-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="3b814-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="3b814-104">Lync Server 2013 incluye una interfaz de servicio web estándar que puede usar para conectar el servicio de información de ubicaciones con aplicaciones de Protocolo simple de administración de redes (SNMP) que coinciden con direcciones MAC con información de puertos y conmutadores.</span><span class="sxs-lookup"><span data-stu-id="3b814-104">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="3b814-105">Si se instala una aplicación SNMP y el servicio de información de ubicación no encuentra ninguna coincidencia en la base de datos de ubicaciones, el servicio de información de ubicaciones consulta automáticamente la aplicación mediante la dirección MAC proporcionada por el cliente.</span><span class="sxs-lookup"><span data-stu-id="3b814-105">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="3b814-106">A continuación, el servicio de información de ubicación usa la información de conmutadores y puertos devuelta por la aplicación SNMP para consultar la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="3b814-106">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="3b814-107">Para obtener más información, consulte [set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span><span class="sxs-lookup"><span data-stu-id="3b814-107">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3b814-108">Las direcciones MAC no están disponibles en los equipos que ejecutan Windows 8.</span><span class="sxs-lookup"><span data-stu-id="3b814-108">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="3b814-109">Para configurar la dirección URL de la aplicación SNMP:</span><span class="sxs-lookup"><span data-stu-id="3b814-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="3b814-110">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3b814-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3b814-111">Ejecute el cmdlet siguiente para configurar la dirección URL para la aplicación SNMP.</span><span class="sxs-lookup"><span data-stu-id="3b814-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

