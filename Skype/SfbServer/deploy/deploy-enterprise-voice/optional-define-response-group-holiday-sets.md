---
title: (Opcional) Definir conjuntos de días festivos de grupo de respuesta Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Cree o modifique conjuntos de días festivos del grupo de respuesta en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: a265f1c8a09133dec6a9f88a705ca6041b1a09a167b5a24252a540e8152deca8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298700"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a>(Opcional) Definir conjuntos de días festivos de grupo de respuesta Skype Empresarial
 
Cree o modifique conjuntos de días festivos del grupo de respuesta en Skype Empresarial Server Telefonía IP empresarial.
  
La configuración de festivos define los días que un grupo de respuesta está cerrado para negocios y especifica la acción que se va a realizar en esos días. Un conjunto de festivos es la colección de festivos que se aplican a un grupo de respuesta.
  
> [!NOTE]
> Si un flujo de trabajo se define como un flujo de trabajo administrado, cualquier usuario al que se le asigne el rol CsResponseGroupManager puede establecer y modificar festivos para los flujos de trabajo que administra. 
  
### <a name="to-create-a-holiday-set"></a>Para crear un conjunto de días festivos

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.
    
2. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
3. Para cada día festivo que quiera definir, ejecute el comando siguiente:
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    Para crear un conjunto de días festivos que contenga los días definidos, ejecute el comando siguiente:
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    El ejemplo siguiente muestra un conjunto de días festivos que incluye dos periodos de vacaciones:
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>Consulte también

[Diseño y creación de flujos de trabajo de grupo de respuesta en Skype Empresarial](designing-and-creating-response-group-workflows.md)

[New-CsRgsHoliday](/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](/powershell/module/skype/new-csrgsholidayset?view=skype-ps)