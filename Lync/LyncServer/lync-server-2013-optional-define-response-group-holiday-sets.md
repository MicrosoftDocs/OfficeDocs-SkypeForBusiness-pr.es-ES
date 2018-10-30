﻿---
title: "(Opcional) Definición de días festivos para grupos de respuesta en Lync Server 2013"
TOCTitle: "(Facul.) Déf. des gr. de congés des gr. Response Group dans Lync Server 2013"
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49889192
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Opcional) Definición de conjuntos de días festivos para grupos de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-07_

La configuración de festivos define los días que un grupo de respuesta está cerrado para negocios y especifica la acción que se va a realizar en esos días. Un conjunto de festivos es la colección de festivos que se aplican a un grupo de respuesta.


> [!NOTE]
> Si un flujo de trabajo se define como un flujo de trabajo administrado, cualquier usuario al que se le asigne el rol CsResponseGroupManager puede establecer y modificar festivos para los flujos de trabajo que administra.



## Para crear un conjunto de días festivos

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Para cada día festivo que quiera definir, ejecute el comando siguiente:
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    Para crear un conjunto de días festivos que contenga los días definidos, ejecute el comando siguiente:
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    El ejemplo siguiente muestra un conjunto de días festivos que incluye dos períodos de vacaciones:
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

## Vea también

#### Conceptos

[Crear o modificar el flujo de trabajo de un grupo de búsqueda en Lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Crear o modificar un flujo de trabajo interactivo en Lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  

#### Otros recursos

[New-CsRgsHoliday](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHoliday)  
[New-CsRgsHolidaySet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHolidaySet)

