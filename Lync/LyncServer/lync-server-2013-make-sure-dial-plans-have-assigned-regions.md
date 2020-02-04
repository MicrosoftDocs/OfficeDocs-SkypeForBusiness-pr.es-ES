---
title: 'Lync Server 2013: Asegurarse de que los planes de marcado tienen regiones asignadas'
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
ms.openlocfilehash: cd8790671157b823464a3b4b594ea8428a888f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>Asegúrese de que los planes de marcado de Lync Server 2013 tienen regiones asignadas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2010-11-02_

Los planes de marcado que se usan para las conferencias de acceso telefónico local necesitan tener una **región de conferencia de acceso telefónico local** especificada para asociar los números de acceso de las conferencias de acceso telefónico local con el plan de marcado adecuado. Al configurar un plan de marcado, especifica la región de conferencia de acceso telefónico local que se aplica a ese plan de marcado. Después, cuando cree el número de acceso telefónico local, seleccione las regiones que asocian el número de acceso con los planes de marcado adecuados.

Como es importante especificar una región para todos los planes de marcado, le recomendamos que use este procedimiento para comprobar que todos los planes de marcado tienen regiones. Este paso es opcional.

Use el cmdlet **Get-CsDialPlan** para comprobar si la región está configurada para todos los planes de marcado de conferencias de acceso telefónico local. Si a los planes de marcado les falta la región, puede usar el cmdlet **Set-CsDialPlan** para establecer la región. También puede usar el panel de control de Lync Server para actualizar la región en los planes de marcado existentes. Para obtener más información sobre el uso del panel de control de Lync Server, vea [modificar un plan de marcado en Lync server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Para comprobar si se ha establecido la propiedad Región en los planes de marcado

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute los siguientes comandos en símbolo del sistema:
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Por ejemplo:
    
        Get-CsDialPlan
    
    En este ejemplo, se devuelven todos los planes de marcado configurados para la organización.

4.  Revise los planes de marcado devueltos para identificar si a alguno le falta la región de conferencias de acceso telefónico local. Para obtener más información, consulte la documentación del shell de administración de Lync Server.

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>Para establecer la propiedad Región en un plan de marcado

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Para los planes de marcado a los que les falte la región de conferencias de acceso telefónico local, ejecute:
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Por ejemplo:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    En este ejemplo, se modifica el plan de marcado con la Identity de Redmond para establecer la propiedad DialinConferencingRegion en "Costa oeste de EE. UU.". Para obtener más información, consulte la documentación del shell de administración de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

