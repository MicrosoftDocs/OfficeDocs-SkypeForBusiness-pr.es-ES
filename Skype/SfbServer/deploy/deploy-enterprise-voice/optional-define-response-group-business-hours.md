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
# <a name="optional-define-response-group-business-hours-in-skype-for-business-2015"></a>(Opcional) Definir horarios laborales de grupos de respuesta en Skype Empresarial 2015
 
Crear o modificar el grupo de respuesta horario en Skype para Telefonía IP empresarial de Business Server.
  
## <a name="defining-business-hours"></a>Definir el horario comercial

La configuración del horario comercial define cuándo está disponible el flujo de trabajo para responder a las llamadas y especifica las acciones que deben efectuarse para responder a llamadas fuera del horario comercial. Los administradores de grupos de respuesta pueden usar el cmdlet **New-CsRgsHoursOfBusiness** para crear programaciones predefinidas que puede utilizar para cualquier número de grupos de respuesta.
  
> [!TIP]
> Cuando cree o modifique un flujo de trabajo, especifique un programa personalizado que se aplique solo a ese flujo de trabajo. Para obtener más información, vea [diseñar y crear flujos de trabajo de grupo de respuesta en Skype para negocios 2015](designing-and-creating-response-group-workflows.md). 
  
> [!NOTE]
> Si un flujo de trabajo se ha definido como flujo de trabajo administrado, cualquier usuario que tenga asignado el rol CsResponseGroupManager puede establecer y modificar el horario comercial de los flujos de trabajo que administra. 
  
> [!IMPORTANT]
> En los parámetros de estos cmdlets, el tiempo debe expresarse en el formato de 24 horas (por ejemplo, las 20:00 equivaldría a las 8:00 p.m.). 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>Para crear una colección de horarios comerciales predefinidos

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Para cada intervalo único de horas que desee definir, ejecute el comando siguiente:
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    Para crear la colección de horarios comerciales que usa los intervalos definidos, ejecute el comando siguiente:
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    El ejemplo siguiente especifica el horario comercial de 9:00 a 17:00 de lunes a viernes, de 8:00 a 10:00 y de 14:00 a 16:00 los sábados y ninguna hora los domingos:
    
   ```
   $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>Vea también

#### 

[Nueva CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[Nueva CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)

