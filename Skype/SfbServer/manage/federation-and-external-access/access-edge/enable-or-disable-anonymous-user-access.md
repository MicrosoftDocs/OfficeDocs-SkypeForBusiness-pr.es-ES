---
title: Habilitar o deshabilitar el acceso de usuarios anónimos
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: cc0d779e2728fd2a82547b52bda57c05c7a983a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006005"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Habilitar o deshabilitar el acceso de usuarios anónimos en Skype empresarial Server

Los usuarios anónimos son usuarios que no tienen una cuenta de usuario en los servicios de dominio de Active Directory de la organización o en un dominio federado admitido, pero que pueden ser invitados a participar remotamente en una conferencia local. Al permitir la participación anónima en las reuniones, se habilitan los usuarios anónimos (es decir, los usuarios cuya identidad se comprueba sólo a través de la reunión o la clave de conferencia) para unirse a las reuniones. Para permitir la participación anónima, es necesario habilitarla para su organización.

Si más adelante desea evitar temporalmente o permanentemente el acceso de usuarios anónimos, puede deshabilitarlo para su organización. Use el procedimiento descrito en esta sección para habilitar o deshabilitar el acceso de usuarios anónimos para su organización.

> [!NOTE]  
> Al habilitar el acceso de usuarios anónimos para su organización, solo está especificando que los servidores que ejecutan el servicio perimetral de acceso admitan el acceso por parte de usuarios anónimos. Los usuarios anónimos no pueden participar en ninguna reunión de su organización hasta que también configure al menos una directiva de conferencia y la aplique a uno o varios usuarios o grupos de usuarios. Los únicos usuarios que pueden invitar a usuarios anónimos a las reuniones son aquellos a los que se les asigna una directiva de conferencia configurada para admitir usuarios anónimos. Para obtener más información sobre cómo configurar directivas de conferencia para admitir la invitación a usuarios anónimos, consulte [Manage Conferencing Policies](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios anónimos para la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:
    
      - Para habilitar el acceso de usuarios anónimos para su organización, active la casilla de verificación **Habilitar comunicaciones con usuarios anónimos** .
    
      - Para deshabilitar el acceso de usuarios anónimos para la organización, desactive la casilla de verificación **Habilitar comunicaciones con usuarios anónimos** .

6.  Haga clic en **Confirmar**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Habilitación o deshabilitación del acceso de usuarios anónimos mediante cmdlets de Windows PowerShell

Puede administrar el acceso de usuarios anónimos mediante Windows PowerShell y el cmdlet **set-CsAccessEdgeConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Para habilitar el acceso de usuarios anónimos

  - Para habilitar el acceso de usuarios anónimos, establezca el valor de la propiedad **AllowAnonymousUsers** en True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Para deshabilitar el acceso de usuarios anónimos

  - Para deshabilitar el acceso de usuarios anónimos, establezca el valor de la propiedad **AllowAnonymousUsers** en False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Vea también

[Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
