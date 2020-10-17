---
title: 'Lync Server 2013: asegurarse de que los planes de marcado tienen regiones asignadas'
description: 'Lync Server 2013: Asegúrese de que los planes de marcado tienen regiones asignadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c055eda221bc03de449631ba38483165a8621773
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563506"
---
# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>Asegurarse de que los planes de marcado Lync Server 2013 tienen regiones asignadas

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2010-11-02_

Debe haberse especificado una **Región de conferencias de acceso telefónico local** para los planes de marcado que se utilicen para conferencias de acceso telefónico para poder asociar los números de acceso a conferencias de acceso telefónico local con el plan de marcado adecuado. Cuando se configura un plan de marcado, se especifica la región de conferencias de acceso telefónico local que se aplica a dicho plan de marcado. A continuación, cuando se crea el número de acceso telefónico local, se seleccionan las regiones que asocian el número de acceso con los planes de marcado adecuados.

Como es importante especificar una región para todos los planes de marcado, se recomienda usar este procedimiento para comprobar que todos los planes de marcado tienen regiones. Este paso es opcional.

Use el cmdlet **Get-CsDialPlan** para comprobar si se ha establecido la región en todos los planes de marcado de conferencia de acceso telefónico local. Si falta la región en los planes de marcado, puede usar el cmdlet **Set-CsDialPlan** para establecerla. También puede usar el panel de control de Lync Server para actualizar la región en los planes de marcado existentes. Para obtener más información sobre el uso del panel de control de Lync Server, consulte [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Para comprobar si se ha establecido la propiedad Región en los planes de marcado

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Ejecute los siguientes comandos en símbolo del sistema:
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Por ejemplo:
    
        Get-CsDialPlan
    
    En este ejemplo, se devuelven todos los planes de marcado configurados para la organización.

4.  Revise los planes de marcado devueltos para identificar si a alguno le falta la región de conferencias de acceso telefónico local. Para obtener más información, vea la documentación referente a Lync Server Management Shell.

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>Para establecer la propiedad Región en un plan de marcado

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Para los planes de marcado a los que les falte la región de conferencias de acceso telefónico local, ejecute:
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Por ejemplo:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    En este ejemplo, el plan de marcado con la identidad de Redmond se modifica para establecer la propiedad DialinConferencingRegion en "US West Coast". Para obtener más información, vea la documentación referente a Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

