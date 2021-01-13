---
title: (Opcional) Definir el horario comercial del grupo de respuesta en Skype Empresarial
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
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Cree o modifique el horario comercial del grupo de respuesta en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: dcd2f7174a75eb68ef8d35759a1e454ede976bde
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831000"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>(Opcional) Definir el horario comercial del grupo de respuesta en Skype Empresarial 
 
Cree o modifique el horario comercial del grupo de respuesta en Skype Empresarial Server Telefonía IP empresarial.
  
## <a name="defining-business-hours"></a>Definir el horario comercial

La configuración del horario comercial define cuándo el flujo de trabajo está disponible para responder a las llamadas y especifica las acciones que deben efectuarse para responder a llamadas fuera del horario comercial. Los administradores de los grupos de respuesta usan el cmdlet **New-CsRgsHoursOfBusiness** para crear programaciones predefinidas que se pueden usar para cualquier cantidad de grupos de respuesta.
  
> [!TIP]
> Cuando cree o modifique un flujo de trabajo, especifique un programa personalizado que se aplique solo a ese flujo de trabajo. Para obtener más información, consulte Diseño y creación de flujos de trabajo [de grupo de respuesta en Skype Empresarial.](designing-and-creating-response-group-workflows.md) 
  
> [!NOTE]
> Si un flujo de trabajo se ha definido como flujo de trabajo administrado, cualquier usuario que tenga asignado el rol CsResponseGroupManager puede establecer y modificar el horario comercial de los flujos de trabajo que administra. 
  
> [!IMPORTANT]
> En los parámetros de estos cmdlets, el tiempo debe expresarse en el formato de 24 horas (por ejemplo, las 20:00 equivaldría a las 8:00 p.m.). 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>Para crear una colección de horarios comerciales predefinidos

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.
    
2. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
3. Para cada intervalo único de horas que desee definir, ejecute el comando siguiente:
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    Para crear la recopilación de horas de oficina que usa los intervalos definidos, ejecute el comando siguiente:
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    El ejemplo siguiente especifica el horario de oficina de 9:00 a 17:00 de lunes a viernes, de 8:00 a 10:00 y de 14:00 a 16:00 los sábados y ninguna hora los domingos:
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>Ver también

[New-CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[New-CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
