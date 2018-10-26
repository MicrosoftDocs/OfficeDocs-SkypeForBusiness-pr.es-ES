---
title: "Lync Server 2013 : (Facul.) Déf. des heures ouvrées des gr. Response Group"
TOCTitle: (Opcional) Definir horarios laborales de grupos de respuesta
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48276813
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Opcional) Definir horarios laborales de grupos de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

## Definir el horario comercial

La configuración del horario comercial define cuándo el flujo de trabajo está disponible para responder a las llamadas y especifica las acciones que deben efectuarse para responder a llamadas fuera del horario comercial. Los administradores de los grupos de respuesta usan el cmdlet **New-CsRgsHoursOfBusiness** para crear programaciones predefinidas que se pueden usar para cualquier cantidad de grupos de respuesta.

> [!TIP]  
> Cuando cree o modifique un flujo de trabajo, especifique un programa personalizado que se aplique solo a ese flujo de trabajo. Para más información, vea <a href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Crear o modificar el flujo de trabajo de un grupo de búsqueda en Lync Server 2013</a> o <a href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Crear o modificar un flujo de trabajo interactivo en Lync Server 2013</a>.




> [!NOTE]
> Si un flujo de trabajo se ha definido como flujo de trabajo administrado, cualquier usuario que tenga asignado el rol CsResponseGroupManager puede establecer y modificar el horario comercial de los flujos de trabajo que administra.



> [!IMPORTANT]  
> En los parámetros de estos cmdlets, el tiempo debe expresarse en el formato de 24 horas (por ejemplo, las 20:00 equivaldría a las 8:00 p.m.).



## Para crear una colección de horarios comerciales predefinidos

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Para cada intervalo único de horas que desee definir, ejecute el comando siguiente:
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    Para crear la colección de horarios comerciales que usa los intervalos definidos, ejecute el comando siguiente:
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    El ejemplo siguiente especifica el horario comercial de 9:00 a 17:00 de lunes a viernes, de 8:00 a 10:00 y de 14:00 a 16:00 los sábados y ninguna hora los domingos:
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

## Vea también

#### Conceptos

[Crear o modificar el flujo de trabajo de un grupo de búsqueda en Lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Crear o modificar un flujo de trabajo interactivo en Lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  

#### Otros recursos

[New-CsRgsTimeRange](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsTimeRange)  
[New-CsRgsHoursOfBusiness](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHoursOfBusiness)

