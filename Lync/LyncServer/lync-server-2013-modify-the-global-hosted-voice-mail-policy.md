---
title: 'Lync Server 2013: modificar la Directiva de correo de voz hospedado global'
description: 'Lync Server 2013: modificar la Directiva de correo de voz hospedado global.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd5e16c78049ce79abd936a79b2025a14e45943
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566866"
---
# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="c9421-103">Modifique la directiva global de correo de voz hospedado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9421-103">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9421-104">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="c9421-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="c9421-105">La Directiva de correo de voz hospedado *global* se instala con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9421-105">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="c9421-106">Modifíquela para adaptarla a sus necesidades, aunque no puede cambiarle el nombre ni eliminarla.</span><span class="sxs-lookup"><span data-stu-id="c9421-106">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="c9421-107">Para modificar la directiva global, use el cmdlet Set-CsHostedVoicemailPolicy para establecer los parámetros en los valores apropiados para su implementación específica.</span><span class="sxs-lookup"><span data-stu-id="c9421-107">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="c9421-108">Para obtener más información sobre el cmdlet [set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9421-108">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="c9421-109">Para modificar la directiva global de correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="c9421-109">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="c9421-110">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c9421-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c9421-111">Ejecute el cmdlet Set-CsHostedVoicemailPolicy para establecer los parámetros de directiva global para su entorno.</span><span class="sxs-lookup"><span data-stu-id="c9421-111">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="c9421-112">Por ejemplo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c9421-112">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="c9421-113">Debido a que este comando no especifica el parámetro Identity de la Directiva, la interfaz de línea de comandos de Windows PowerShell establece los valores siguientes en la Directiva de correo de voz hospedado global:</span><span class="sxs-lookup"><span data-stu-id="c9421-113">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="c9421-p103">**Destination** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este parámetro es opcional pero, si trata de habilitar a un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene ningún valor de Destination, no podrá habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="c9421-p103">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="c9421-116">**Organization** especifica una lista separada por comas de los inquilinos de Exchange que alojan a los usuarios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9421-116">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="c9421-117">Cada arrendatario se debe especificar como el FQDN del arrendatario en cuestión en el servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="c9421-117">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c9421-118">En el cmdlet de ejemplo anterior, el valor "corp1.litwareinc.com" reemplaza cualquier valor que ya esté presente en el parámetro Organization.</span><span class="sxs-lookup"><span data-stu-id="c9421-118">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter.</span></span> <span data-ttu-id="c9421-119">Por ejemplo, si la directiva ya contiene una lista separada por comas de organizaciones, se reemplazará la lista completa.</span><span class="sxs-lookup"><span data-stu-id="c9421-119">For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced.</span></span> <span data-ttu-id="c9421-120">Si desea agregar una organización a la lista en lugar de reemplazar la lista completa, ejecute un comando similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="c9421-120">If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

