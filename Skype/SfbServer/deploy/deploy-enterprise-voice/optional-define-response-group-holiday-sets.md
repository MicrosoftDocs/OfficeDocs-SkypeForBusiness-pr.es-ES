---
title: (Opcional) Definir conjuntos de días festivos para grupos de respuesta en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Crear o modificar conjuntos de días festivos de grupo de respuesta, en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 0ee6ffa0afdff32096845d7450fa92ff6e720022
ms.sourcegitcommit: 68e68c96c18d854afc0158920e6d9d738f276d91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business-2015"></a>(Opcional) Definir conjuntos de días festivos para grupos de respuesta en Skype Empresarial 2015
 
Crear o modificar conjuntos de días festivos de grupo de respuesta, en Skype para Business Server Enterprise Voice.
  
La configuración de festivos define los días que un grupo de respuesta está cerrado para negocios y especifica la acción que se va a realizar en esos días. Un conjunto de festivos es la colección de festivos que se aplican a un grupo de respuesta.
  
> [!NOTE]
> Si un flujo de trabajo se define como un flujo de trabajo administrado, cualquier usuario al que se le asigne el rol CsResponseGroupManager puede establecer y modificar festivos para los flujos de trabajo que administra. 
  
### <a name="to-create-a-holiday-set"></a>Para crear un conjunto de días festivos

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Para cada día festivo que quiera definir, ejecute el comando siguiente:
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    Para crear un conjunto de días festivos que contenga los días definidos, ejecute el comando siguiente:
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    El ejemplo siguiente muestra un conjunto de días festivos que incluye dos períodos de vacaciones:
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>Vea también

[Diseñar y crear flujos de trabajo de grupo de respuesta en Skype para profesionales de 2015](designing-and-creating-response-group-workflows.md)

[New-CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
