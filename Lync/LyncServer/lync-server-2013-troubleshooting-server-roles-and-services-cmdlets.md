---
title: 'Lync Server 2013: solución de problemas de roles de servidor y cmdlets de servicios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting server roles and services cmdlets
ms:assetid: 03be4cae-bf35-40b2-8e02-477b64afa4c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415628(v=OCS.15)
ms:contentKeyID: 48183268
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb8c4504674e5459fbbb0e7529ea4e6c4ad7a8f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-server-roles-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="4a5a2-102">Solución de problemas de roles de servidor y cmdlets de servicios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a5a2-102">Troubleshooting server roles and services cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a5a2-103">_**Última modificación del tema:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="4a5a2-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="4a5a2-104">Los cmdlets de solución de problemas proporcionan distintas maneras de comprobar que Microsoft Lync Server 2013 funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="4a5a2-104">The troubleshooting cmdlets provide different ways to verify that Microsoft Lync Server 2013 is working as expected.</span></span> <span data-ttu-id="4a5a2-105">Por ejemplo, los cmdlets CsHealthMonitoringConfiguration le permiten configurar cuentas de prueba para los grupos de registradores y directores.</span><span class="sxs-lookup"><span data-stu-id="4a5a2-105">For example, the CsHealthMonitoringConfiguration cmdlets enable you to set up test accounts for Registrar and Director pools.</span></span> <span data-ttu-id="4a5a2-106">A su vez, puede usar estas cuentas de prueba para comprobar que los usuarios pueden completar correctamente tareas comunes como iniciar sesión en el sistema, intercambiar mensajes instantáneos o hacer llamadas a un teléfono que se encuentra en la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="4a5a2-106">In turn, you can then use those test accounts to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4a5a2-107">Para obtener más información sobre los cmdlets, vea el&nbsp;blog de Windows PowerShell <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>de Lync Server en.</span><span class="sxs-lookup"><span data-stu-id="4a5a2-107">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="4a5a2-108">El contenido de los blogs y sus URL están sujetos a cambios sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="4a5a2-108">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="server-roles-and-services-cmdlets"></a><span data-ttu-id="4a5a2-109">Cmdlets de servicios y roles de servidor</span><span class="sxs-lookup"><span data-stu-id="4a5a2-109">Server Roles and Services Cmdlets</span></span>

<span data-ttu-id="4a5a2-110">A continuación se muestra una lista de cmdlets que se relacionan directamente con la solución de problemas de roles y servicios del servidor:</span><span class="sxs-lookup"><span data-stu-id="4a5a2-110">The following is a list of cmdlets that relate directly to troubleshooting server roles and services:</span></span>

<span data-ttu-id="4a5a2-111">**Solución de problemas de roles y servicios de servidor**</span><span class="sxs-lookup"><span data-stu-id="4a5a2-111">**Troubleshooting Server Roles and Services**</span></span>

  - <span></span>  
    <span data-ttu-id="4a5a2-112">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-112">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a5a2-113">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-113">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4a5a2-114">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-114">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a5a2-115">[Nuevo: CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-115">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a5a2-116">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-116">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a5a2-117">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-117">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4a5a2-118">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-118">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a5a2-119">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-119">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a5a2-120">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-120">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a5a2-121">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-121">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4a5a2-122">[Nuevo: CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-122">[New-CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4a5a2-123">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-123">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a5a2-124">[Nuevo: CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-124">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a5a2-125">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-125">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4a5a2-126">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5a2-126">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

