---
title: 'Lync Server 2013: solución de problemas de cmdlets de telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Enterprise Voice cmdlets
ms:assetid: 28ec32d2-6d1e-40e6-b2a8-065803288e8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415638(v=OCS.15)
ms:contentKeyID: 48183697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 499da8c727237a581af55e56aec3517a7a427e44
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="f0b76-102">Solución de problemas de cmdlets de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0b76-102">Troubleshooting Enterprise Voice cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0b76-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="f0b76-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="f0b76-104">Configurar la voz de empresa como parte de la implementación de Microsoft Lync Server 2013 implica la creación de rutas, directivas y reglas que deben funcionar conjuntamente para garantizar que las llamadas entrantes y salientes se completen de la forma esperada.</span><span class="sxs-lookup"><span data-stu-id="f0b76-104">Setting up Enterprise Voice as part of your Microsoft Lync Server 2013 implementation involves creating routes, policies and rules that must all work together to ensure incoming and outgoing calls are completed as expected.</span></span> <span data-ttu-id="f0b76-105">El shell de administración de Lync Server incluye cmdlets que se pueden usar para probar conexiones y rutas y para solucionar problemas que puedan surgir durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="f0b76-105">Lync Server Management Shell includes cmdlets that can be used to test connections and paths and to troubleshoot issues that may arise during implementation.</span></span>

<div>

## <a name="troubleshooting-enterprise-voice-cmdlets"></a><span data-ttu-id="f0b76-106">Solución de problemas de cmdlets de telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="f0b76-106">Troubleshooting Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="f0b76-107">Los cmdlets siguientes se pueden usar para probar y solucionar problemas de las conexiones de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="f0b76-107">The following cmdlets can be used to test and troubleshoot Enterprise Voice connections.</span></span>

<span data-ttu-id="f0b76-108">**Solución de problemas de cmdlets de telefonía IP empresarial**</span><span class="sxs-lookup"><span data-stu-id="f0b76-108">**Troubleshooting Enterprise Voice Cmdlets**</span></span>

  - <span></span>  
    <span data-ttu-id="f0b76-109">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-109">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0b76-110">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-110">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0b76-111">[Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-111">[Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0b76-112">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-112">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0b76-113">[Nuevo: CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-113">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0b76-114">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-114">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0b76-115">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-115">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0b76-116">[Prueba-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-116">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0b76-117">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-117">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0b76-118">[Prueba-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-118">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0b76-119">[Prueba-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-119">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0b76-120">[Prueba-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-120">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0b76-121">[Prueba-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0b76-121">[Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0b76-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0b76-122">See Also</span></span>


[<span data-ttu-id="f0b76-123">Cmdlets de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0b76-123">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="f0b76-124">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0b76-124">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

