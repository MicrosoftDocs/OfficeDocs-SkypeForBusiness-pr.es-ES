---
title: 'Lync Server 2013: (opcional) definir conjuntos de días festivos para grupos de respuesta'
description: 'Lync Server 2013: (opcional) definir conjuntos de días festivos para grupos de respuesta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group holiday sets
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49733657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7ba735cc62efb9d5553c8bd6aad1aa9484f70f4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565766"
---
# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a>Opcional Definir conjuntos de días festivos para grupos de respuesta en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-07_

La configuración de festivos define los días que un grupo de respuesta está cerrado para negocios y especifica la acción que se va a realizar en esos días. Un conjunto de festivos es la colección de festivos que se aplican a un grupo de respuesta.

<div>


> [!NOTE]  
> Si un flujo de trabajo se define como un flujo de trabajo administrado, cualquier usuario al que se le asigne el rol CsResponseGroupManager puede establecer y modificar festivos para los flujos de trabajo que administra.



</div>

<div>

## <a name="to-create-a-holiday-set"></a>Para crear un conjunto de días festivos

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Para cada día festivo que quiera definir, ejecute el comando siguiente:
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    Para crear un conjunto de días festivos que contenga los días definidos, ejecute el comando siguiente:
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    El ejemplo siguiente muestra un conjunto de días festivos que incluye dos periodos de vacaciones:
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a>Consulte también


[Crear o modificar un flujo de trabajo de grupo de búsqueda en Lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Crear o modificar un flujo de trabajo interactivo en Lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[New-CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

