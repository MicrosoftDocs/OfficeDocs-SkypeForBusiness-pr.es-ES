---
title: 'Lync Server 2013: (opcional) definir conjuntos de días festivos de grupos de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Define Response Group holiday sets
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49733657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ca58b3e2c17ea70e9af7a9eba48df8582b1485c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a><span data-ttu-id="f6da9-102">Faculta Definir conjuntos de días festivos de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6da9-102">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6da9-103">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="f6da9-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="f6da9-p101">La configuración de festivos define los días que un grupo de respuesta está cerrado para negocios y especifica la acción que se va a realizar en esos días. Un conjunto de festivos es la colección de festivos que se aplican a un grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f6da9-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6da9-106">Si un flujo de trabajo se define como un flujo de trabajo administrado, cualquier usuario al que se le asigne el rol CsResponseGroupManager puede establecer y modificar festivos para los flujos de trabajo que administra.</span><span class="sxs-lookup"><span data-stu-id="f6da9-106">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span>



</div>

<div>

## <a name="to-create-a-holiday-set"></a><span data-ttu-id="f6da9-107">Para crear un conjunto de días festivos</span><span class="sxs-lookup"><span data-stu-id="f6da9-107">To create a holiday set</span></span>

1.  <span data-ttu-id="f6da9-108">Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f6da9-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="f6da9-109">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f6da9-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f6da9-110">Para cada día festivo que quiera definir, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6da9-110">For each holiday you want to define, run:</span></span>
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    <span data-ttu-id="f6da9-111">Para crear un conjunto de días festivos que contenga los días definidos, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6da9-111">To create the holiday set that contains the holidays you defined, run:</span></span>
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    <span data-ttu-id="f6da9-112">El ejemplo siguiente muestra un conjunto de días festivos que incluye dos períodos de vacaciones:</span><span class="sxs-lookup"><span data-stu-id="f6da9-112">The following example shows a holiday set that includes two holidays:</span></span>
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f6da9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6da9-113">See Also</span></span>


[<span data-ttu-id="f6da9-114">Crear o modificar un flujo de trabajo de grupo de captura en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6da9-114">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="f6da9-115">Crear o modificar un flujo de trabajo interactivo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6da9-115">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="f6da9-116">Nuevo: CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="f6da9-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[<span data-ttu-id="f6da9-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="f6da9-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

