---
title: 'Lync Server 2013: asignar directivas a un teléfono de área común'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dfe908f2bb4ca66714d3eef756a0c53c7334fd7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="22158-102">Asignar directivas en Lync Server 2013 a un teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="22158-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22158-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="22158-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="22158-104">Después de crear la Directiva para teléfonos de área común (para obtener más información, consulte [Create a Voice Policy and configure RTC Usage Records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), puede asignar la Directiva a un teléfono de área común con Windows PowerShell y el cmdlet **Grant-CS** correspondiente.</span><span class="sxs-lookup"><span data-stu-id="22158-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="22158-105">Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22158-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="22158-106">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="22158-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="22158-107">Asignar una directiva a un solo teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="22158-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="22158-108">El comando siguiente asigna la Directiva de voz por usuario RedmondVoice al teléfono de área común que tiene la firma de compilación 14 de Identity.</span><span class="sxs-lookup"><span data-stu-id="22158-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="22158-109">Asignación de una directiva a varios teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="22158-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="22158-110">En este ejemplo, la Directiva de voz por usuario RedmondVoice se asigna a todos los teléfonos de área común configurados para su uso en la organización.</span><span class="sxs-lookup"><span data-stu-id="22158-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="22158-111">Para obtener más información, consulte los temas de ayuda de [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="22158-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="22158-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="22158-112">See Also</span></span>


[<span data-ttu-id="22158-113">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="22158-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

