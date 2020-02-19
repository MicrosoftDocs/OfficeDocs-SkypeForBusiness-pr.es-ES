---
title: 'Lync Server 2013: habilitar o deshabilitar el acceso de usuarios anónimos'
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
ms.openlocfilehash: 5c873953b16004f514871c0cf4b4708ad41c0117
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>Habilitar o deshabilitar el acceso de usuarios anónimos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Los usuarios anónimos son usuarios que no tienen una cuenta de usuario en los servicios de dominio de Active Directory de la organización o en un dominio federado admitido, pero que pueden ser invitados a participar remotamente en una conferencia local. Al permitir la participación anónima en las reuniones, se habilitan los usuarios anónimos (es decir, los usuarios cuya identidad se comprueba sólo a través de la reunión o la clave de conferencia) para unirse a las reuniones. Para permitir la participación anónima, es necesario habilitarla para su organización.

Si más adelante desea evitar temporalmente o permanentemente el acceso de usuarios anónimos, puede deshabilitarlo para su organización. Use el procedimiento descrito en esta sección para habilitar o deshabilitar el acceso de usuarios anónimos para su organización.

<div>


> [!NOTE]  
> Al habilitar el acceso de usuarios anónimos para su organización, solo está especificando que los servidores que ejecutan el servicio perimetral de acceso admitan el acceso por parte de usuarios anónimos. Los usuarios anónimos no pueden participar en ninguna reunión de su organización hasta que también configure al menos una directiva de conferencia y la aplique a uno o varios usuarios o grupos de usuarios. Los únicos usuarios que pueden invitar a usuarios anónimos a las reuniones son aquellos a los que se les asigna una directiva de conferencia configurada para admitir usuarios anónimos. Para obtener más información sobre cómo configurar directivas de conferencia para admitir la invitación a usuarios anónimos, consulte <A href="lync-server-2013-conferencing-policies.md">directivas de conferencia en Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios anónimos para la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:
    
      - Para habilitar el acceso de usuarios anónimos para su organización, active la casilla de verificación **Habilitar comunicaciones con usuarios anónimos** .
    
      - Para deshabilitar el acceso de usuarios anónimos para la organización, desactive la casilla de verificación **Habilitar comunicaciones con usuarios anónimos** .

6.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Habilitación o deshabilitación del acceso de usuarios anónimos mediante cmdlets de Windows PowerShell

Puede administrar el acceso de usuarios anónimos mediante Windows PowerShell y el cmdlet **set-CsAccessEdgeConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-enable-anonymous-user-access"></a>Para habilitar el acceso de usuarios anónimos

  - Para habilitar el acceso de usuarios anónimos, establezca el valor de la propiedad **AllowAnonymousUsers** en True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>Para deshabilitar el acceso de usuarios anónimos

  - Para deshabilitar el acceso de usuarios anónimos, establezca el valor de la propiedad **AllowAnonymousUsers** en False ($false):
    
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

