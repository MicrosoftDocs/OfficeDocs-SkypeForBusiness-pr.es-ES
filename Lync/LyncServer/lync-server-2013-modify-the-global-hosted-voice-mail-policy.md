---
title: 'Lync Server 2013: modificar la Directiva de correo de voz hospedado global'
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
ms.openlocfilehash: e930e0b1f9a6e2d246a8011c59e2c92c75ba138d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="5dcdc-102">Modificar la Directiva de correo de voz hospedado global en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5dcdc-102">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dcdc-103">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="5dcdc-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="5dcdc-104">La Directiva de correo de voz hospedado *global* se instala con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-104">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="5dcdc-105">Puede modificarla para satisfacer sus necesidades, pero no puede cambiarle el nombre ni eliminarla.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-105">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="5dcdc-106">Para modificar la directiva global, use el cmdlet Set-CsHostedVoicemailPolicy para establecer los parámetros en los valores adecuados para su implementación específica.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-106">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="5dcdc-107">Para obtener más información sobre el cmdlet [set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-107">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="5dcdc-108">Para modificar la Directiva de correo de voz hospedado global</span><span class="sxs-lookup"><span data-stu-id="5dcdc-108">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="5dcdc-109">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5dcdc-110">Ejecute el cmdlet Set-CsHostedVoicemailPolicy para establecer los parámetros de directiva global de su entorno.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-110">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="5dcdc-111">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5dcdc-111">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="5dcdc-112">Debido a que este comando no especifica el parámetro de identidad de la Directiva, la interfaz de línea de comandos de Windows PowerShell establece los siguientes valores en la Directiva de correo de voz hospedado global:</span><span class="sxs-lookup"><span data-stu-id="5dcdc-112">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="5dcdc-113">**Destino** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-113">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="5dcdc-114">Este parámetro es opcional, pero si intenta habilitar un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene un valor de destino, se producirá un error de habilitar.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-114">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="5dcdc-115">**Organización** especifica una lista separada por comas de los inquilinos de Exchange que alojan usuarios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-115">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="5dcdc-116">Cada inquilino debe especificarse como el FQDN de ese inquilino en el servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-116">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5dcdc-117">En el cmdlet de ejemplo anterior, el valor "corp1.litwareinc.com" reemplaza cualquier valor que ya pudiera estar presente en el parámetro de organización.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-117">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter.</span></span> <span data-ttu-id="5dcdc-118">Por ejemplo, si la directiva ya contiene una lista de organizaciones separadas por comas, se reemplazaría la lista completa.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-118">For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced.</span></span> <span data-ttu-id="5dcdc-119">Si desea agregar una organización a la lista en lugar de reemplazar toda la lista, ejecute un comando similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="5dcdc-119">If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
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

