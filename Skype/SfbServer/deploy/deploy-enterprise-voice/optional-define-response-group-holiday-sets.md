---
title: Faculta Definir conjuntos de días festivos de grupos de respuesta en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Crear o modificar conjuntos de días festivos de grupos de respuesta en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 9dd9467a40f45d7252e92d9628d8678adbce3184
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003100"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a><span data-ttu-id="30e87-103">Faculta Definir conjuntos de días festivos de grupos de respuesta en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="30e87-103">(Optional) Define Response Group holiday sets in Skype for Business</span></span>
 
<span data-ttu-id="30e87-104">Crear o modificar conjuntos de días festivos de grupos de respuesta en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="30e87-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="30e87-p101">La configuración de festivos define los días que un grupo de respuesta está cerrado para negocios y especifica la acción que se va a realizar en esos días. Un conjunto de festivos es la colección de festivos que se aplican a un grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="30e87-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="30e87-107">Si un flujo de trabajo se define como un flujo de trabajo administrado, cualquier usuario al que se le asigne el rol CsResponseGroupManager puede establecer y modificar festivos para los flujos de trabajo que administra.</span><span class="sxs-lookup"><span data-stu-id="30e87-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="30e87-108">Para crear un conjunto de días festivos</span><span class="sxs-lookup"><span data-stu-id="30e87-108">To create a holiday set</span></span>

1. <span data-ttu-id="30e87-109">Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="30e87-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="30e87-110">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="30e87-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="30e87-111">Para cada día festivo que quiera definir, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="30e87-111">For each holiday you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="30e87-112">Para crear un conjunto de días festivos que contenga los días definidos, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="30e87-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="30e87-113">El ejemplo siguiente muestra un conjunto de días festivos que incluye dos períodos de vacaciones:</span><span class="sxs-lookup"><span data-stu-id="30e87-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="30e87-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="30e87-114">See also</span></span>

[<span data-ttu-id="30e87-115">Diseñar y crear flujos de trabajo de grupos de respuesta en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="30e87-115">Designing and creating response group workflows in Skype for Business</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="30e87-116">Nuevo: CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="30e87-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="30e87-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="30e87-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
