---
title: (Opcional) Definir horarios laborales de grupos de respuesta en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Crear o modificar el grupo de respuesta horario en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 1fc5705a141d056993c26250f4e11b90a9b37419
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business-2015"></a><span data-ttu-id="f645d-103">(Opcional) Definir horarios laborales de grupos de respuesta en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="f645d-103">(Optional) Define Response Group business hours in Skype for Business 2015</span></span>
 
<span data-ttu-id="f645d-104">Crear o modificar el grupo de respuesta horario en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="f645d-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="f645d-105">Definir el horario comercial</span><span class="sxs-lookup"><span data-stu-id="f645d-105">Defining Business Hours</span></span>

<span data-ttu-id="f645d-106">La configuración del horario comercial define cuándo está disponible el flujo de trabajo para responder a las llamadas y especifica las acciones que deben efectuarse para responder a llamadas fuera del horario comercial.</span><span class="sxs-lookup"><span data-stu-id="f645d-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="f645d-107">Los administradores de grupos de respuesta pueden usar el cmdlet **New-CsRgsHoursOfBusiness** para crear programaciones predefinidas que puede utilizar para cualquier número de grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f645d-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="f645d-108">Cuando cree o modifique un flujo de trabajo, especifique un programa personalizado que se aplique solo a ese flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f645d-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="f645d-109">Para obtener más información, vea [diseñar y crear flujos de trabajo de grupo de respuesta en Skype para negocios 2015](designing-and-creating-response-group-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="f645d-109">For details, see [Designing and creating response group workflows in Skype for Business 2015](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f645d-110">Si un flujo de trabajo se ha definido como flujo de trabajo administrado, cualquier usuario que tenga asignado el rol CsResponseGroupManager puede establecer y modificar el horario comercial de los flujos de trabajo que administra.</span><span class="sxs-lookup"><span data-stu-id="f645d-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f645d-111">En los parámetros de estos cmdlets, el tiempo debe expresarse en el formato de 24 horas (por ejemplo, las 20:00 equivaldría a las 8:00 p.m.).</span><span class="sxs-lookup"><span data-stu-id="f645d-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="f645d-112">Para crear una colección de horarios comerciales predefinidos</span><span class="sxs-lookup"><span data-stu-id="f645d-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="f645d-113">Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f645d-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="f645d-114">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f645d-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f645d-115">Para cada intervalo único de horas que desee definir, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="f645d-115">For each unique range of hours you want to define, run:</span></span>
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="f645d-116">Para crear la colección de horarios comerciales que usa los intervalos definidos, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="f645d-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="f645d-p103">El ejemplo siguiente especifica el horario comercial de 9:00 a 17:00 de lunes a viernes, de 8:00 a 10:00 y de 14:00 a 16:00 los sábados y ninguna hora los domingos:</span><span class="sxs-lookup"><span data-stu-id="f645d-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
   ```
   $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="f645d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f645d-124">See also</span></span>

#### 

[<span data-ttu-id="f645d-125">Nueva CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="f645d-125">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="f645d-126">Nueva CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="f645d-126">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)

