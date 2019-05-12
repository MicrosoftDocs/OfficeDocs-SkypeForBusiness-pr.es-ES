---
title: (Opcional) Días festivos de definir grupo de respuesta se establecen en Skype para la empresa
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Crear o modificar conjuntos de días festivos de grupo de respuesta, en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: d78eaeee9b447dfd0c9f4f7250b6f34aee298594
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894708"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a>(Opcional) Días festivos de definir grupo de respuesta se establecen en Skype para la empresa
 
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

[Diseñar y crear flujos de trabajo de grupo de respuesta en Skype para la empresa](designing-and-creating-response-group-workflows.md)

[New-CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
