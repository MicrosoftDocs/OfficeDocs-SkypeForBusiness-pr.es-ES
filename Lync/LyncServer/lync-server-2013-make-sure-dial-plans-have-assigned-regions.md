---
title: "Lync Server 2013: Asegurarse de que los planes de marcado tienen regiones asignadas"
TOCTitle: Asegurarse de que los planes de marcado tienen regiones asignadas
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48275055
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asegurarse de que los planes de marcado de Lync Server 2013 tienen regiones asignadas

 

_**Última modificación del tema:** 2010-11-02_

Debe haberse especificado una **Región de conferencias de acceso telefónico local** para los planes de marcado que se utilicen para conferencias de acceso telefónico para poder asociar los números de acceso a conferencias de acceso telefónico local con el plan de marcado adecuado. Cuando se configura un plan de marcado, se especifica la región de conferencias de acceso telefónico local que se aplica a dicho plan de marcado. A continuación, cuando se crea el número de acceso telefónico local, se seleccionan las regiones que asocian el número de acceso con los planes de marcado adecuados.

Como es importante especificar una región para todos los planes de marcado, se recomienda usar este procedimiento para comprobar que todos los planes de marcado tienen regiones. Este paso es opcional.

Use el cmdlet **Get-CsDialPlan** para comprobar si se ha establecido la región en todos los planes de marcado de conferencia de acceso telefónico local. Si falta la región en los planes de marcado, puede usar el cmdlet **Set-CsDialPlan** para establecerla. También puede usar el Panel de control de Lync Server para actualizar la región en planes de marcado existentes. Para más información sobre el uso del Panel de control de Lync Server, consulte [Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

## Para comprobar si se ha establecido la propiedad Región en los planes de marcado

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute los siguientes comandos en símbolo del sistema:
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Por ejemplo:
    
        Get-CsDialPlan
    
    En este ejemplo, se devuelven todos los planes de marcado configurados para la organización.

4.  Revise los planes de marcado devueltos para identificar si a alguno le falta la región de conferencias de acceso telefónico local. Para obtener información detallada, consulte la documentación del Shell de administración de Lync Server.

## Para establecer la propiedad Región en un plan de marcado

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Para los planes de marcado a los que les falte la región de conferencias de acceso telefónico local, ejecute:
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Por ejemplo:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    En este ejemplo, se modifica el plan de marcado con la Identity de Redmond para establecer la propiedad DialinConferencingRegion en "Costa oeste de EE. UU.". Para obtener información detallada, consulte la documentación del Shell de administración de Lync Server.

