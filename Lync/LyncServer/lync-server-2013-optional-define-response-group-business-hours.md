---
title: 'Lync Server 2013: (opcional) definir horario comercial de grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group business hours
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48185504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b02ce8434d7912d81855725aa86a11fa377ce44
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a><span data-ttu-id="a1a2a-102">Opcional Definir el horario comercial del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1a2a-102">(Optional) Define Response Group business hours in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1a2a-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a1a2a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<div>

## <a name="defining-business-hours"></a><span data-ttu-id="a1a2a-104">Definir el horario comercial</span><span class="sxs-lookup"><span data-stu-id="a1a2a-104">Defining Business Hours</span></span>

<span data-ttu-id="a1a2a-105">La configuración del horario comercial define cuándo el flujo de trabajo está disponible para responder a las llamadas y especifica las acciones que deben efectuarse para responder a llamadas fuera del horario comercial.</span><span class="sxs-lookup"><span data-stu-id="a1a2a-105">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="a1a2a-106">Los administradores de los grupos de respuesta usan el cmdlet **New-CsRgsHoursOfBusiness** para crear programaciones predefinidas que se pueden usar para cualquier cantidad de grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="a1a2a-106">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="a1a2a-107">Cuando cree o modifique un flujo de trabajo, especifique un programa personalizado que se aplique solo a ese flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a1a2a-107">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="a1a2a-108">Para obtener más información, consulte <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">crear o modificar un flujo de trabajo de grupo de búsqueda en Lync server 2013</A> o <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">crear o modificar un flujo de trabajo interactivo en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a1a2a-108">For details, see <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Create or modify a hunt group workflow in Lync Server 2013</A> or <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Create or modify an interactive workflow in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a1a2a-109">Si un flujo de trabajo se ha definido como flujo de trabajo administrado, cualquier usuario que tenga asignado el rol CsResponseGroupManager puede establecer y modificar el horario comercial de los flujos de trabajo que administra.</span><span class="sxs-lookup"><span data-stu-id="a1a2a-109">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a1a2a-110">En los parámetros de estos cmdlets, el tiempo debe expresarse en el formato de 24 horas (por ejemplo, las 20:00 equivaldría a las 8:00 p.m.).</span><span class="sxs-lookup"><span data-stu-id="a1a2a-110">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span>



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="a1a2a-111">Para crear una colección de horarios comerciales predefinidos</span><span class="sxs-lookup"><span data-stu-id="a1a2a-111">To create a predefined business hours collection</span></span>

1.  <span data-ttu-id="a1a2a-112">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="a1a2a-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a1a2a-113">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a1a2a-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a1a2a-114">Para cada intervalo único de horas que desee definir, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1a2a-114">For each unique range of hours you want to define, run:</span></span>
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    <span data-ttu-id="a1a2a-115">Para crear la recopilación de horas de oficina que usa los intervalos definidos, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1a2a-115">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    <span data-ttu-id="a1a2a-p103">El ejemplo siguiente especifica el horario de oficina de 9:00 a 17:00 de lunes a viernes, de 8:00 a 10:00 y de 14:00 a 16:00 los sábados y ninguna hora los domingos:</span><span class="sxs-lookup"><span data-stu-id="a1a2a-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1a2a-123">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a1a2a-123">See Also</span></span>


[<span data-ttu-id="a1a2a-124">Crear o modificar un flujo de trabajo de grupo de búsqueda en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1a2a-124">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="a1a2a-125">Crear o modificar un flujo de trabajo interactivo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1a2a-125">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="a1a2a-126">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="a1a2a-126">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[<span data-ttu-id="a1a2a-127">New-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="a1a2a-127">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

