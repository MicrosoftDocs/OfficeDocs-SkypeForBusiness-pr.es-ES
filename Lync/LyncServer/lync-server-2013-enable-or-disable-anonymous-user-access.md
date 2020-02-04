---
title: 'Lync Server 2013: Habilitar y deshabilitar el acceso anónimo de usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d38d0d9f50ff06b2f7eb95944d9214c2c4c64a5c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>Habilitar y deshabilitar el acceso anónimo de usuarios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Los usuarios anónimos son usuarios que no tienen una cuenta de usuario en los servicios de dominio de Active Directory de su organización o en un dominio federado admitido, pero se les puede invitar a participar de forma remota en una conferencia local. Al permitir la participación anónima en las reuniones, habilita los usuarios anónimos (es decir, los usuarios cuya identidad se comprueba a través de la reunión o de la clave de conferencia) para unirse a las reuniones. Permitir la participación anónima requiere habilitarlo para su organización.

Si posteriormente desea impedir de forma temporal o permanente el acceso de usuarios anónimos, puede deshabilitarlo para su organización. Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios anónimos a su organización.

<div>


> [!NOTE]  
> Al permitir el acceso de usuarios anónimos a su organización, solo se especifica que los servidores que ejecutan el servicio perimetral de acceso admiten el acceso de usuarios anónimos. Los usuarios anónimos no pueden participar en ninguna reunión de su organización hasta que también configure al menos una directiva de conferencia y la aplique a uno o más usuarios o grupos de usuarios. Los únicos usuarios que pueden invitar a usuarios anónimos a las reuniones son aquellos a los que se les ha asignado una directiva de conferencia que está configurada para admitir usuarios anónimos. Para obtener más información sobre cómo configurar directivas de conferencia para admitir la invitación a usuarios anónimos, consulte <A href="lync-server-2013-conferencing-policies.md">directivas de conferencia en Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios anónimos para su organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **configuración del borde de Access**.

4.  En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración del límite de acceso**, realice una de las siguientes acciones:
    
      - Para habilitar el acceso de usuarios anónimos para su organización, seleccione la casilla de verificación **habilitar las comunicaciones con usuarios anónimos** .
    
      - Para deshabilitar el acceso de usuarios anónimos para su organización, desactive la casilla **habilitar las comunicaciones con usuarios anónimos** .

6.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar el acceso de usuarios anónimos mediante cmdlets de Windows PowerShell

Puede administrar el acceso de usuarios anónimos mediante Windows PowerShell y el cmdlet **set-CsAccessEdgeConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-enable-anonymous-user-access"></a>Para habilitar el acceso de usuarios anónimos

  - Para habilitar el acceso de usuarios anónimos, establece el valor de la propiedad **AllowAnonymousUsers** en True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>Para deshabilitar el acceso de usuarios anónimos

  - Para deshabilitar el acceso de usuarios anónimos, establece el valor de la propiedad **AllowAnonymousUsers** en False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Referencia de configuración de directiva de conferencia para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

